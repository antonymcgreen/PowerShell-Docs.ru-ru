---
title: Добавление действий Windows PowerShell на панель инструментов Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: 2a8372d937fc3c959f7d829bb52495048423d506
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863570"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a>Добавление действий Windows PowerShell в инструментарий Visual Studio

Прежде чем создавать рабочий процесс PowerShell, с помощью конструктора рабочих процессов, необходимо сначала добавить действий PowerShell в рабочий процесс Visual Studio консольное приложение на панели инструментов. Ниже показано, как для добавления действий из сборки Microsoft.PowerShell.Core.Activities на панель инструментов Visual Studio.

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a>Добавление действия в область элементов Windows PowerShell

1. Создайте новый проект консольного приложения рабочего процесса в Visual Studio.

2. На **представление** меню, щелкните **элементов**.

3. Добавить новую вкладку в панели элементов, щелкните правой кнопкой мыши внутри панели элементов и щелкните **добавить вкладку**и назовите новую вкладку, например, «PowerShell».

   Добавление вкладки позволяет группировать действия PowerShell, отдельно от других средств в области элементов.

4. На новой вкладке панели элементов, нажмите кнопку **Выбор элементов...** . **Выбор элементов панели элементов** откроется диалоговое окно.

5. В **Выбор элементов панели элементов** диалоговое окно, нажмите кнопку **System.Activities** вкладки.

6. Нажмите кнопку **Обзор**.

7. Перейдите к папке %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e и дважды щелкните Microsoft.PowerShell.Core.Activities.dll.

8. Нажмите кнопку **ОК**. Действия, определенные в сборке Microsoft.PowerShell.Core.Activities теперь доступны на панели элементов.

## <a name="see-also"></a>См. также

[Запись рабочего процесса Windows PowerShell](./writing-a-windows-powershell-workflow.md)

[Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md)