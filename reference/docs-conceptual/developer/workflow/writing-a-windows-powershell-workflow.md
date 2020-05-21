---
title: Создание рабочего процесса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 0f8a9938a1685e9abc2f1dbfb18c3b2b9008d9be
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564932"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="ca6ca-102">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6ca-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="ca6ca-103">Вы можете создать рабочий процесс XAML, добавив действия, предоставляемые сборками Windows PowerShell, в конструктор рабочих процессов в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="ca6ca-104">Следующие сборки Windows PowerShell предоставляют действия, поддерживающие рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca6ca-105">Рабочий процесс XAML должен быть упакован в модуль, если требуется предоставить справку для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="ca6ca-106">Дополнительные сведения о модулях см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="ca6ca-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="ca6ca-107">Microsoft. PowerShell. действия</span><span class="sxs-lookup"><span data-stu-id="ca6ca-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="ca6ca-108">Microsoft. PowerShell. Core. Activitys</span><span class="sxs-lookup"><span data-stu-id="ca6ca-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="ca6ca-109">Microsoft. PowerShell. Diagnostics. Activitys</span><span class="sxs-lookup"><span data-stu-id="ca6ca-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="ca6ca-110">Microsoft. PowerShell. Management. Activitys</span><span class="sxs-lookup"><span data-stu-id="ca6ca-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="ca6ca-111">Microsoft. PowerShell. Security. Activitys</span><span class="sxs-lookup"><span data-stu-id="ca6ca-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="ca6ca-112">Microsoft. PowerShell. Utility. Activitys</span><span class="sxs-lookup"><span data-stu-id="ca6ca-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="ca6ca-113">В следующих разделах описывается создание рабочего процесса с помощью действий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca6ca-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="ca6ca-114">Добавление действий Windows PowerShell в инструментарий Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ca6ca-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="ca6ca-115">Создание рабочего процесса с помощью действий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6ca-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="ca6ca-116">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6ca-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="ca6ca-117">Импорт и вызов рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6ca-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="ca6ca-118">Создание действия рабочего процесса из командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6ca-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)
