---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 368d29b7cdcbe2725399da0896eed87ddb372236
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342150"
---
# <span data-ttu-id="d3322-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="d3322-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="d3322-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d3322-104">SYNOPSIS</span></span>
<span data-ttu-id="d3322-105">Закрывает интерактивный сеанс с локальным процессом.</span><span class="sxs-lookup"><span data-stu-id="d3322-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="d3322-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3322-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="d3322-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3322-107">DESCRIPTION</span></span>

<span data-ttu-id="d3322-108">`Exit-PSHostProcess`Командлет закрывает интерактивный сеанс с локальным процессом, который был открыт путем запуска `Enter-PSHostProcess` командлета.</span><span class="sxs-lookup"><span data-stu-id="d3322-108">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="d3322-109">`Exit-PSHostProcess`Командлет запускается из процесса, когда завершается Отладка или устранение неполадок в скрипте, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="d3322-109">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="d3322-110">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="d3322-110">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="d3322-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="d3322-111">EXAMPLES</span></span>

### <span data-ttu-id="d3322-112">Пример 1. выход из процесса</span><span class="sxs-lookup"><span data-stu-id="d3322-112">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="d3322-113">В этом примере вы работали в активном процессе для отладки сценария, выполняющегося в пространстве выполнения процесса, как описано в разделе `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="d3322-113">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="d3322-114">После ввода `exit` команды для выхода из отладчика выполните `Exit-PSHostProcess` командлет, чтобы закрыть интерактивный сеанс с процессом.</span><span class="sxs-lookup"><span data-stu-id="d3322-114">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="d3322-115">Командлет закрывает сеанс в процессе и возвращает вас в `PS C:\>` командную строку.</span><span class="sxs-lookup"><span data-stu-id="d3322-115">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="d3322-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3322-116">PARAMETERS</span></span>

### <span data-ttu-id="d3322-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d3322-117">CommonParameters</span></span>

<span data-ttu-id="d3322-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3322-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3322-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3322-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3322-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d3322-120">INPUTS</span></span>

## <span data-ttu-id="d3322-121">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d3322-121">OUTPUTS</span></span>

## <span data-ttu-id="d3322-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d3322-122">NOTES</span></span>

## <span data-ttu-id="d3322-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d3322-123">RELATED LINKS</span></span>

[<span data-ttu-id="d3322-124">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="d3322-124">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)

