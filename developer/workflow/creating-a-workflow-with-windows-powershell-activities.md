---
title: Создание рабочего процесса с помощью Windows PowerShell действий | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080440"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Создание рабочего процесса с помощью действий Windows PowerShell

Можно создать рабочий процесс Windows PowerShell, выбрав действий из панели элементов Visual Studio и перетащив их в окно конструктора рабочих процессов. Сведения о добавлении действия Windows PowerShell для панели элементов Visual Studio, см. в разделе [добавления действий Windows PowerShell для панели элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).

Следующие процедуры описывают создание рабочего процесса, который проверяет состояние домена для группы компьютеров, определяемое пользователем, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.

### <a name="setting-up-the-project"></a>Настройка проекта

1. Выполните процедуру, описанную в [добавления действий Windows PowerShell для панели элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) для создания проекта рабочего процесса и добавления действий из [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) и [ Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) сборок на панель элементов.

2. Добавьте System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities и Microsoft.PowerShell.Commands.Management относительно проекта, как базовые сборки.

### <a name="adding-activities-to-the-workflow"></a>Добавление действий в рабочий процесс

1. Добавить **последовательности** действия в рабочий процесс.

2. Создайте аргумент с именем `ComputerName` с типом аргумента `String[]`. Этот аргумент представляет имена компьютеров для проверки и join.

3. Создайте аргумент с именем `DomainCred` типа [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Этот аргумент представляет учетные данные учетной записи домена, имеющее полномочия на присоединение компьютера к домену.

4. Создайте аргумент с именем `MachineCred` типа [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Этот аргумент представляет учетные данные администратора на компьютерах, для проверки и join.

5. Добавить **ParallelForEach** действия внутри **последовательности** действия. Введите `comp` и `ComputerName` в текстовые поля, чтобы цикл выполняет итерацию по элементам `ComputerName` массива.

6. Добавить **последовательности** действия в тело **ParallelForEach** действия. Задайте **DisplayName** свойство последовательности `JoinDomain`.

7. Добавить **GetWmiObject** действие **JoinDomain** последовательности.

8. Изменение свойств **GetWmiObject** действия, как показано ниже.

   |Свойство|Значение|
   |--------------|-----------|
   |**Класс**|"Win32_ComputerSystem"|
   |**PSComputerName**|{comp}|
   |**PSCredential**|MachineCred|

9. Добавить **AddComputer** действие **JoinDomain** последовательности после **GetWmiObject** действия.

10. Изменение свойств **AddComputer** действия, как показано ниже.

    |Свойство|Значение|
    |--------------|-----------|
    |**ComputerName**|{comp}|
    |**DomainCredential**|DomainCred|

11. Добавить **RestartComputer** действие **JoinDomain** последовательности после **AddComputer** действия.

12. Изменение свойств **RestartComputer** действия, как показано ниже.

    |Свойство|Значение|
    |--------------|-----------|
    |**ComputerName**|{comp}|
    |**Учетные данные**|MachineCred|
    |**для**|Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell|
    |**Force**|True|
    |Wait|True|
    |PSComputerName|{""}|

13. Добавить **GetWmiObject** действие **JoinDomain** последовательности после **RestartComputer** действия. Изменить свойства, чтобы быть так же, как и при предыдущем **GetWmiObject** действия.

    После завершения процедуры окна конструктора рабочего процесса должен выглядеть следующим образом.

    ![JoinDomain XAML в конструкторе рабочих процессов](../media/joindomainworkflow.png)
    ![JoinDomain XAML в конструкторе рабочих процессов](../media/joindomainworkflow.png "JoinDomainWorkflow")