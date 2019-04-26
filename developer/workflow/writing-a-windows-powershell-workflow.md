---
title: Написание рабочего процесса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080328"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="96314-102">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96314-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="96314-103">Можно создать рабочий процесс XAML путем добавления действий, предоставляемых сборок Windows PowerShell в конструктор рабочих процессов в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96314-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="96314-104">Следующие сборки Windows PowerShell предоставляют действия с поддержкой рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="96314-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96314-105">Рабочий процесс XAML должны быть упакованы как модуль, если вы хотите предоставить справку для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="96314-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="96314-106">Сведения о модулях см. в разделе [написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="96314-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="96314-107">Microsoft.Powershell.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="96314-108">Microsoft.Powershell.Core.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="96314-109">Microsoft.Powershell.Diagnostics.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="96314-110">Microsoft.Powershell.Management.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="96314-111">Microsoft.Powershell.Security.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="96314-112">Microsoft.Powershell.Utility.Activities</span><span class="sxs-lookup"><span data-stu-id="96314-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="96314-113">Ниже описаны способы создания рабочего процесса с помощью действий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96314-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="96314-114">Добавление действия Windows PowerShell в область элементов Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96314-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="96314-115">Создание рабочего процесса с помощью действий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96314-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="96314-116">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96314-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="96314-117">Импорт и вызова рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96314-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="96314-118">Создание действия рабочего процесса из командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96314-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)