---
title: Создание рабочего процесса с помощью действий Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359633"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a>Создание рабочего процесса с помощью действий Windows PowerShell

Вы можете создать рабочий процесс Windows PowerShell, выбрав действия из панели элементов Visual Studio и перетащив их в окно конструктор рабочих процессов. Сведения о добавлении действий Windows PowerShell в панель элементов Visual Studio см. в разделе [Добавление действий Windows PowerShell в панель элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).

В следующих процедурах описывается создание рабочего процесса, который проверяет состояние домена указанных пользователем компьютеров, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.

### <a name="setting-up-the-project"></a>Настройка проекта

1. Выполните процедуру, описанную в разделе [Добавление действий Windows PowerShell в панель элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) , чтобы создать проект рабочего процесса и добавить действия из [Microsoft. PowerShell. activitys](/dotnet/api/Microsoft.PowerShell.Activities) и [Microsoft. PowerShell. Management. activitys. ](/dotnet/api/Microsoft.PowerShell.Management.Activities)сборки на панель элементов.

2. Добавьте System. Management. Automation, Microsoft. PowerShell. Activitys, System. Management, Microsoft. PowerShell. Management. Activitys и Microsoft. PowerShell. Commands. Management как в проект в качестве эталонных сборок.

### <a name="adding-activities-to-the-workflow"></a>Добавление действий в рабочий процесс

1. Добавьте действие **Sequence** в рабочий процесс.

2. Создайте аргумент с именем `ComputerName` с типом аргумента `String[]`. Этот аргумент представляет имена компьютеров для проверки и присоединение.

3. Создайте аргумент с именем `DomainCred` типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Этот аргумент представляет учетные данные домена учетной записи домена, которая имеет право присоединить компьютер к домену.

4. Создайте аргумент с именем `MachineCred` типа [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential). Этот аргумент представляет учетные данные администратора на компьютерах, которые необходимо проверить и присоединить.

5. Добавьте действие **ParallelForEach** в действие **Sequence** . Введите `comp` и `ComputerName` в текстовые поля, чтобы цикл пробирал элементы массива `ComputerName`.

6. Добавьте действие **Sequence** в тело действия **ParallelForEach** . Задайте для свойства **DisplayName** последовательности значение `JoinDomain`.

7. Добавьте действие **жетвмиобжект** в последовательность **JoinDomain** .

8. Измените свойства действия **жетвмиобжект** следующим образом.

   |Свойство|Применение|
   |--------------|-----------|
   |**См**|"Win32_ComputerSystem"|
   |**PSComputerName**|соответствовал|
   |**PSCredential**|мачинекред|

9. Добавьте действие **аддкомпутер** в последовательность **JoinDomain** после действия **жетвмиобжект** .

10. Измените свойства действия **аддкомпутер** следующим образом.

    |Свойство|Применение|
    |--------------|-----------|
    |**ComputerName**|соответствовал|
    |**домаинкредентиал**|домаинкред|

11. Добавьте действие **рестарткомпутер** в последовательность **JoinDomain** после действия **аддкомпутер** .

12. Измените свойства действия **рестарткомпутер** следующим образом.

    |Свойство|Применение|
    |--------------|-----------|
    |**ComputerName**|соответствовал|
    |**Записям**|мачинекред|
    |**Предмет**|Microsoft. PowerShell. Commands. Ваитфорсервицетипес. PowerShell|
    |**Перевести**|True|
    |Wait|True|
    |PSComputerName|{""}|

13. Добавьте действие **жетвмиобжект** в последовательность **JoinDomain** после действия **рестарткомпутер** . Измените его свойства, чтобы они совпадали с предыдущим действием **жетвмиобжект** .

    После завершения процедур окно конструктора рабочих процессов должно выглядеть следующим образом.

    ![JoinDomain XAML в конструкторе рабочих процессов @ no__t-1![JOINDOMAIN XAML в конструкторе рабочих процессов](../media/joindomainworkflow.png "жоиндомаинворкфлов")