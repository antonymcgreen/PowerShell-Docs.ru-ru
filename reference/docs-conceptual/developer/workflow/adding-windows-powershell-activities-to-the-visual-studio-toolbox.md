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
ms.openlocfilehash: 2a8372d937fc3c959f7d829bb52495048423d506
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359653"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a><span data-ttu-id="a657c-102">Добавление действий Windows PowerShell в инструментарий Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a657c-102">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>

<span data-ttu-id="a657c-103">Прежде чем создавать рабочий процесс PowerShell с помощью конструктор рабочих процессов, необходимо сначала добавить действия PowerShell в область элементов в проекте консольного приложения рабочего процесса Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a657c-103">Before you author a PowerShell Workflow using Workflow Designer, you must first add the PowerShell Activities to the Toolbox in a Visual Studio Workflow console application project.</span></span> <span data-ttu-id="a657c-104">В следующей процедуре показано, как добавить действия из сборки Microsoft. PowerShell. Core. Activitys в панель элементов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a657c-104">The following procedure shows how to add the activities from the Microsoft.PowerShell.Core.Activities assembly to the Visual Studio toolbox.</span></span>

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a><span data-ttu-id="a657c-105">Добавление действий Windows PowerShell на панель элементов</span><span class="sxs-lookup"><span data-stu-id="a657c-105">Adding Windows PowerShell Activities to the Toolbox</span></span>

1. <span data-ttu-id="a657c-106">Создайте новый проект консольного приложения рабочего процесса в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a657c-106">Create a new Workflow console application project in Visual Studio.</span></span>

2. <span data-ttu-id="a657c-107">В меню **Вид** выберите пункт **Область элементов**.</span><span class="sxs-lookup"><span data-stu-id="a657c-107">On the **View** menu, click **Toolbox**.</span></span>

3. <span data-ttu-id="a657c-108">Добавьте новую вкладку на панели элементов, щелкнув правой кнопкой мыши внутри области элементов и выбрав пункт **Добавить вкладку**, а затем присвойте новой вкладке Имя, например "действия PowerShell".</span><span class="sxs-lookup"><span data-stu-id="a657c-108">Add a new tab in the Toolbox by right-clicking inside the Toolbox and clicking **Add Tab**, and give the new tab a name such as "PowerShell Activities".</span></span>

   <span data-ttu-id="a657c-109">Добавление вкладки позволяет группировать действия PowerShell отдельно от других инструментов на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="a657c-109">Adding a tab allows you to group the PowerShell Activities separate from other tools in the Toolbox.</span></span>

4. <span data-ttu-id="a657c-110">На новой вкладке панели элементов нажмите кнопку **выбрать элементы...** . Откроется диалоговое окно **Выбор элементов панели элементов** .</span><span class="sxs-lookup"><span data-stu-id="a657c-110">On the new Toolbox tab, click **Choose Items...**. The **Choose Toolbox Items** dialog appears.</span></span>

5. <span data-ttu-id="a657c-111">В диалоговом окне **Выбор элементов панели элементов** перейдите на вкладку **System. activitys** .</span><span class="sxs-lookup"><span data-stu-id="a657c-111">In the **Choose Toolbox Items** dialog, click the **System.Activities** tab.</span></span>

6. <span data-ttu-id="a657c-112">Нажмите кнопку **Browse**.</span><span class="sxs-lookup"><span data-stu-id="a657c-112">Click **Browse**.</span></span>

7. <span data-ttu-id="a657c-113">Перейдите в папку%Виндир%\микрософт.нет\ассембли\ GAC_MSIL \Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e и дважды щелкните файл Microsoft. PowerShell. Core. Activitys. dll.</span><span class="sxs-lookup"><span data-stu-id="a657c-113">Navigate to the %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e folder and double-click Microsoft.PowerShell.Core.Activities.dll.</span></span>

8. <span data-ttu-id="a657c-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a657c-114">Click **OK**.</span></span> <span data-ttu-id="a657c-115">Действия, определенные сборкой Microsoft. PowerShell. Core. Activitys, теперь доступны на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="a657c-115">The activities defined by the Microsoft.PowerShell.Core.Activities assembly are now available in the toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="a657c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="a657c-116">See Also</span></span>

[<span data-ttu-id="a657c-117">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a657c-117">Writing a Windows PowerShell Workflow</span></span>](./writing-a-windows-powershell-workflow.md)

[<span data-ttu-id="a657c-118">Создание рабочего процесса с помощью действий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a657c-118">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)