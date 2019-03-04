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
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a><span data-ttu-id="64e7c-102">Добавление действий Windows PowerShell в инструментарий Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64e7c-102">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>

<span data-ttu-id="64e7c-103">Прежде чем создавать рабочий процесс PowerShell, с помощью конструктора рабочих процессов, необходимо сначала добавить действий PowerShell в рабочий процесс Visual Studio консольное приложение на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="64e7c-103">Before you author a PowerShell Workflow using Workflow Designer, you must first add the PowerShell Activities to the Toolbox in a Visual Studio Workflow console application project.</span></span> <span data-ttu-id="64e7c-104">Ниже показано, как для добавления действий из сборки Microsoft.PowerShell.Core.Activities на панель инструментов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="64e7c-104">The following procedure shows how to add the activities from the Microsoft.PowerShell.Core.Activities assembly to the Visual Studio toolbox.</span></span>

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a><span data-ttu-id="64e7c-105">Добавление действия в область элементов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64e7c-105">Adding Windows PowerShell Activities to the Toolbox</span></span>

1. <span data-ttu-id="64e7c-106">Создайте новый проект консольного приложения рабочего процесса в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="64e7c-106">Create a new Workflow console application project in Visual Studio.</span></span>

2. <span data-ttu-id="64e7c-107">На **представление** меню, щелкните **элементов**.</span><span class="sxs-lookup"><span data-stu-id="64e7c-107">On the **View** menu, click **Toolbox**.</span></span>

3. <span data-ttu-id="64e7c-108">Добавить новую вкладку в панели элементов, щелкните правой кнопкой мыши внутри панели элементов и щелкните **добавить вкладку**и назовите новую вкладку, например, «PowerShell».</span><span class="sxs-lookup"><span data-stu-id="64e7c-108">Add a new tab in the Toolbox by right-clicking inside the Toolbox and clicking **Add Tab**, and give the new tab a name such as "PowerShell Activities".</span></span>

   <span data-ttu-id="64e7c-109">Добавление вкладки позволяет группировать действия PowerShell, отдельно от других средств в области элементов.</span><span class="sxs-lookup"><span data-stu-id="64e7c-109">Adding a tab allows you to group the PowerShell Activities separate from other tools in the Toolbox.</span></span>

4. <span data-ttu-id="64e7c-110">На новой вкладке панели элементов, нажмите кнопку **Выбор элементов...** . **Выбор элементов панели элементов** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="64e7c-110">On the new Toolbox tab, click **Choose Items...**. The **Choose Toolbox Items** dialog appears.</span></span>

5. <span data-ttu-id="64e7c-111">В **Выбор элементов панели элементов** диалоговое окно, нажмите кнопку **System.Activities** вкладки.</span><span class="sxs-lookup"><span data-stu-id="64e7c-111">In the **Choose Toolbox Items** dialog, click the **System.Activities** tab.</span></span>

6. <span data-ttu-id="64e7c-112">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="64e7c-112">Click **Browse**.</span></span>

7. <span data-ttu-id="64e7c-113">Перейдите к папке %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e и дважды щелкните Microsoft.PowerShell.Core.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="64e7c-113">Navigate to the %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e folder and double-click Microsoft.PowerShell.Core.Activities.dll.</span></span>

8. <span data-ttu-id="64e7c-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="64e7c-114">Click **OK**.</span></span> <span data-ttu-id="64e7c-115">Действия, определенные в сборке Microsoft.PowerShell.Core.Activities теперь доступны на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="64e7c-115">The activities defined by the Microsoft.PowerShell.Core.Activities assembly are now available in the toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="64e7c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="64e7c-116">See Also</span></span>

[<span data-ttu-id="64e7c-117">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64e7c-117">Writing a Windows PowerShell Workflow</span></span>](./writing-a-windows-powershell-workflow.md)

[<span data-ttu-id="64e7c-118">Создание рабочего процесса с помощью действий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64e7c-118">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)