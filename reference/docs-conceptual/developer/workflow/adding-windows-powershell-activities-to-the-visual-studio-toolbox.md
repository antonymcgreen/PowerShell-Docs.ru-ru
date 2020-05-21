---
title: Добавление действий Windows PowerShell в панель элементов Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: ecd23d3eb722137bdda0498fc71e0e966c57a589
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561195"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a>Добавление действий Windows PowerShell в инструментарий Visual Studio

Прежде чем создавать рабочий процесс PowerShell с помощью конструктор рабочих процессов, необходимо сначала добавить действия PowerShell в область элементов в проекте консольного приложения рабочего процесса Visual Studio. В следующей процедуре показано, как добавить действия из сборки Microsoft. PowerShell. Core. Activitys в панель элементов Visual Studio.

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a>Добавление действий Windows PowerShell на панель элементов

1. Создайте новый проект консольного приложения рабочего процесса в Visual Studio.

2. В меню **Вид** выберите пункт **Область элементов**.

3. Добавьте новую вкладку на панели элементов, щелкнув правой кнопкой мыши внутри области элементов и выбрав пункт **Добавить вкладку**, а затем присвойте новой вкладке Имя, например "действия PowerShell".

   Добавление вкладки позволяет группировать действия PowerShell отдельно от других инструментов на панели элементов.

4. На новой вкладке панели элементов нажмите кнопку **выбрать элементы...**. Откроется диалоговое окно **Выбор элементов панели элементов** .

5. В диалоговом окне **Выбор элементов панели элементов** перейдите на вкладку **System. activitys** .

6. Нажмите кнопку **Обзор**.

7. Перейдите в папку%Виндир%\микрософт.нет\ассембли\ GAC_MSIL \Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e и дважды щелкните файл Microsoft. PowerShell. Core. Activitys. dll.

8. Нажмите кнопку **ОК**. Действия, определенные сборкой Microsoft. PowerShell. Core. Activitys, теперь доступны на панели элементов.

## <a name="see-also"></a>См. также:

[Запись рабочего процесса Windows PowerShell](./writing-a-windows-powershell-workflow.md)

[Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)
