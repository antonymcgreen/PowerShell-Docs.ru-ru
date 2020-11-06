---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: 54e1345e949107427f5cd042bbcc253f9ad3416b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228117"
---
# <span data-ttu-id="d3074-103">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d3074-103">Get-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="d3074-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d3074-104">SYNOPSIS</span></span>
<span data-ttu-id="d3074-105">Возвращает ключевые привязки для модуля PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d3074-105">Gets the key bindings for the PSReadLine module.</span></span>

## <span data-ttu-id="d3074-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3074-106">SYNTAX</span></span>

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

## <span data-ttu-id="d3074-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3074-107">DESCRIPTION</span></span>

<span data-ttu-id="d3074-108">Командлет **Get-PSReadLineKeyHandler** Возвращает привязки ключей, привязанные к текущему объекту.</span><span class="sxs-lookup"><span data-stu-id="d3074-108">The **Get-PSReadLineKeyHandler** cmdlet returns the currently bound key bindings.</span></span>

## <span data-ttu-id="d3074-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="d3074-109">EXAMPLES</span></span>

### <span data-ttu-id="d3074-110">Пример 1. получение всех сопоставлений ключей</span><span class="sxs-lookup"><span data-stu-id="d3074-110">Example 1: Get all key mappings</span></span>

<span data-ttu-id="d3074-111">Эта команда возвращает все сопоставления ключей, связанные и несвязанные.</span><span class="sxs-lookup"><span data-stu-id="d3074-111">This command returns all key mappings, bound and unbound.</span></span>

```powershell
Get-PSReadLineKeyHandler -Bound -Unbound
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
Shift+Tab             TabCompletePrevious     Complete the input using the previous completion
Ctrl+a                SelectAll               Select the entire line. Moves the cursor to the end of the line
Ctrl+c                CopyOrCancelLine        Either copy selected text to the clipboard, or if no text is selected, cancel editing the line with Cancel...
Ctrl+C                Copy                    Copy selected region to the system clipboard.  If no region is selected, copy the whole line
Ctrl+l                ClearScreen             Clear the screen and redraw the current line at the top of the screen
Ctrl+r                ReverseSearchHistory    Search history backwards interactively
...
```

### <span data-ttu-id="d3074-112">Пример 2. получение привязанных ключей</span><span class="sxs-lookup"><span data-stu-id="d3074-112">Example 2: Get bound keys</span></span>

<span data-ttu-id="d3074-113">Эта команда возвращает только связанные ключи и сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="d3074-113">This command returns only bound keys and key combinations.</span></span>

```powershell
Get-PSReadLineKeyHandler
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
...
```

## <span data-ttu-id="d3074-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3074-114">PARAMETERS</span></span>

### <span data-ttu-id="d3074-115">С привязкой</span><span class="sxs-lookup"><span data-stu-id="d3074-115">-Bound</span></span>

<span data-ttu-id="d3074-116">Указывает, что этот командлет возвращает функции, которые связаны.</span><span class="sxs-lookup"><span data-stu-id="d3074-116">Indicates that this cmdlet returns functions that are bound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3074-117">— Без привязки</span><span class="sxs-lookup"><span data-stu-id="d3074-117">-Unbound</span></span>

<span data-ttu-id="d3074-118">Указывает, что этот командлет возвращает функции, которые не привязаны.</span><span class="sxs-lookup"><span data-stu-id="d3074-118">Indicates that this cmdlet returns functions that are unbound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3074-119">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d3074-119">CommonParameters</span></span>

<span data-ttu-id="d3074-120">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3074-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3074-121">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3074-121">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3074-122">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d3074-122">INPUTS</span></span>

### <span data-ttu-id="d3074-123">Нет</span><span class="sxs-lookup"><span data-stu-id="d3074-123">None</span></span>

<span data-ttu-id="d3074-124">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="d3074-124">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d3074-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d3074-125">OUTPUTS</span></span>

### <span data-ttu-id="d3074-126">Microsoft. PowerShell. Кэйхандлер</span><span class="sxs-lookup"><span data-stu-id="d3074-126">Microsoft.PowerShell.KeyHandler</span></span>

## <span data-ttu-id="d3074-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d3074-127">NOTES</span></span>

## <span data-ttu-id="d3074-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d3074-128">RELATED LINKS</span></span>

[<span data-ttu-id="d3074-129">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d3074-129">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="d3074-130">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d3074-130">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="d3074-131">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d3074-131">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="d3074-132">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d3074-132">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)