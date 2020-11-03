---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 29a72bac55dd4aabca52673a192b13f75b88f308
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209033"
---
# <span data-ttu-id="ae523-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ae523-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="ae523-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ae523-104">SYNOPSIS</span></span>
<span data-ttu-id="ae523-105">Закрывает интерактивный сеанс с локальным процессом.</span><span class="sxs-lookup"><span data-stu-id="ae523-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="ae523-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae523-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="ae523-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae523-107">DESCRIPTION</span></span>
<span data-ttu-id="ae523-108">Командлет **Exit-PSHostProcess** закрывает интерактивный сеанс с локальным процессом, который был открыт, выполняя командлет Enter-PSHostProcess.</span><span class="sxs-lookup"><span data-stu-id="ae523-108">The **Exit-PSHostProcess** cmdlet closes an interactive session with a local process that you have opened by running the Enter-PSHostProcess cmdlet.</span></span>
<span data-ttu-id="ae523-109">При завершении отладки или устранении неполадок скрипта, выполняемого в процессе, запускается командлет **Exit-PSHostProcess** из процесса.</span><span class="sxs-lookup"><span data-stu-id="ae523-109">You run the **Exit-PSHostProcess** cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span>

## <span data-ttu-id="ae523-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ae523-110">EXAMPLES</span></span>

### <span data-ttu-id="ae523-111">Пример 1. выход из процесса</span><span class="sxs-lookup"><span data-stu-id="ae523-111">Example 1: Exit a process</span></span>

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

<span data-ttu-id="ae523-112">В этом примере вы работали в активном процессе для отладки сценария, выполняющегося в пространстве выполнения процесса, как описано в разделе Ввод-PSHostProcess.</span><span class="sxs-lookup"><span data-stu-id="ae523-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in Enter-PSHostProcess.</span></span>
<span data-ttu-id="ae523-113">После ввода команды **Exit** для выхода из отладчика выполните командлет **Exit-PSHostProcess** , чтобы закрыть интерактивный сеанс с процессом.</span><span class="sxs-lookup"><span data-stu-id="ae523-113">After you type the **exit** command to exit the debugger, run the **Exit-PSHostProcess** cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="ae523-114">Командлет закрывает сеанс в процессе и возвращает вас в строку PS C: \\ \> Prompt.</span><span class="sxs-lookup"><span data-stu-id="ae523-114">The cmdlet closes your session in the process, and returns you to the PS C:\\\> prompt.</span></span>

## <span data-ttu-id="ae523-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae523-115">PARAMETERS</span></span>

### <span data-ttu-id="ae523-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ae523-116">CommonParameters</span></span>
<span data-ttu-id="ae523-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ae523-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae523-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ae523-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ae523-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ae523-119">INPUTS</span></span>

## <span data-ttu-id="ae523-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ae523-120">OUTPUTS</span></span>

## <span data-ttu-id="ae523-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ae523-121">NOTES</span></span>

## <span data-ttu-id="ae523-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ae523-122">RELATED LINKS</span></span>

[<span data-ttu-id="ae523-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ae523-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
