---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: a1a8c6fcc16bcddc3bfcdade56cd75aadd179b74
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601493"
---
# <span data-ttu-id="3c81a-102">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="3c81a-102">Exit-PSHostProcess</span></span>

## <span data-ttu-id="3c81a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3c81a-103">SYNOPSIS</span></span>
<span data-ttu-id="3c81a-104">Закрывает интерактивный сеанс с локальным процессом.</span><span class="sxs-lookup"><span data-stu-id="3c81a-104">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="3c81a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c81a-105">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="3c81a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c81a-106">DESCRIPTION</span></span>

<span data-ttu-id="3c81a-107">`Exit-PSHostProcess`Командлет закрывает интерактивный сеанс с локальным процессом, который был открыт путем запуска `Enter-PSHostProcess` командлета.</span><span class="sxs-lookup"><span data-stu-id="3c81a-107">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="3c81a-108">`Exit-PSHostProcess`Командлет запускается из процесса, когда завершается Отладка или устранение неполадок в скрипте, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="3c81a-108">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="3c81a-109">Начиная с PowerShell 6,2 Этот командлет поддерживается на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="3c81a-109">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="3c81a-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c81a-110">EXAMPLES</span></span>

### <span data-ttu-id="3c81a-111">Пример 1. выход из процесса</span><span class="sxs-lookup"><span data-stu-id="3c81a-111">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="3c81a-112">В этом примере вы работали в активном процессе для отладки сценария, выполняющегося в пространстве выполнения процесса, как описано в разделе `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="3c81a-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="3c81a-113">После ввода `exit` команды для выхода из отладчика выполните `Exit-PSHostProcess` командлет, чтобы закрыть интерактивный сеанс с процессом.</span><span class="sxs-lookup"><span data-stu-id="3c81a-113">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="3c81a-114">Командлет закрывает сеанс в процессе и возвращает вас в `PS C:\>` командную строку.</span><span class="sxs-lookup"><span data-stu-id="3c81a-114">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="3c81a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c81a-115">PARAMETERS</span></span>

### <span data-ttu-id="3c81a-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3c81a-116">CommonParameters</span></span>

<span data-ttu-id="3c81a-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c81a-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c81a-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c81a-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c81a-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3c81a-119">INPUTS</span></span>

## <span data-ttu-id="3c81a-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3c81a-120">OUTPUTS</span></span>

## <span data-ttu-id="3c81a-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3c81a-121">NOTES</span></span>

## <span data-ttu-id="3c81a-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3c81a-122">RELATED LINKS</span></span>

[<span data-ttu-id="3c81a-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="3c81a-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)

