---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 78fa1c50d629484a013f7bd91bc3758e3efb141e
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233178"
---
# <span data-ttu-id="a3559-103">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="a3559-103">Get-PSReadLineOption</span></span>

## <span data-ttu-id="a3559-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a3559-104">SYNOPSIS</span></span>
<span data-ttu-id="a3559-105">Получает значения для параметров, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="a3559-105">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="a3559-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3559-106">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="a3559-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3559-107">DESCRIPTION</span></span>

<span data-ttu-id="a3559-108">`Get-PSReadLineOption`Командлет возвращает текущее состояние параметров, которые можно настроить с помощью `Set-PSReadLineOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="a3559-108">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="a3559-109">Возвращаемый объект можно использовать для изменения параметров **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="a3559-109">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="a3559-110">Это обеспечивает более простой способ, чтобы задать параметры цветовой разметки синтаксиса для нескольких типов маркеров.</span><span class="sxs-lookup"><span data-stu-id="a3559-110">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="a3559-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="a3559-111">EXAMPLES</span></span>

### <span data-ttu-id="a3559-112">Пример 1. Получение параметров и их значений</span><span class="sxs-lookup"><span data-stu-id="a3559-112">Example 1: Get options and their values</span></span>

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    : System.Func`2[System.String,System.Object]
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "`e[93m"
CommentColor                           : "`e[32m"
ContinuationPromptColor                : "`e[97m"
DefaultTokenColor                      : "`e[97m"
EmphasisColor                          : "`e[96m"
ErrorColor                             : "`e[91m"
KeywordColor                           : "`e[92m"
MemberColor                            : "`e[97m"
NumberColor                            : "`e[97m"
OperatorColor                          : "`e[90m"
ParameterColor                         : "`e[90m"
SelectionColor                         : "`e[30;107m"
StringColor                            : "`e[36m"
TypeColor                              : "`e[37m"
VariableColor                          : "`e[92m"
```

<span data-ttu-id="a3559-113">Эта команда возвращает список доступных параметров PSReadLine и их текущих значений.</span><span class="sxs-lookup"><span data-stu-id="a3559-113">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="a3559-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3559-114">PARAMETERS</span></span>

### <span data-ttu-id="a3559-115">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a3559-115">CommonParameters</span></span>

<span data-ttu-id="a3559-116">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3559-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3559-117">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3559-117">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3559-118">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a3559-118">INPUTS</span></span>

### <span data-ttu-id="a3559-119">Нет</span><span class="sxs-lookup"><span data-stu-id="a3559-119">None</span></span>

<span data-ttu-id="a3559-120">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="a3559-120">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="a3559-121">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a3559-121">OUTPUTS</span></span>

### <span data-ttu-id="a3559-122">Microsoft. PowerShell. Псконсолереадлинеоптионс</span><span class="sxs-lookup"><span data-stu-id="a3559-122">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="a3559-123">Экземпляр текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="a3559-123">An instance of the current options.</span></span> <span data-ttu-id="a3559-124">При изменении значений свойств этого объекта параметры в PSReadLine напрямую обновляются без вызова `Set-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="a3559-124">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="a3559-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a3559-125">NOTES</span></span>

## <span data-ttu-id="a3559-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a3559-126">RELATED LINKS</span></span>

[<span data-ttu-id="a3559-127">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="a3559-127">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="a3559-128">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="a3559-128">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="a3559-129">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="a3559-129">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="a3559-130">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="a3559-130">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
