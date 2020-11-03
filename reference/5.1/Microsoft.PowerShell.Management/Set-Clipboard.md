---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227898"
---
# <span data-ttu-id="1ce1e-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="1ce1e-103">Set-Clipboard</span></span>

## <span data-ttu-id="1ce1e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1ce1e-104">SYNOPSIS</span></span>
<span data-ttu-id="1ce1e-105">Задает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-105">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="1ce1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ce1e-106">SYNTAX</span></span>

### <span data-ttu-id="1ce1e-107">Строка (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1ce1e-107">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1ce1e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="1ce1e-108">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1ce1e-109">Путь</span><span class="sxs-lookup"><span data-stu-id="1ce1e-109">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1ce1e-110">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1ce1e-110">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1ce1e-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ce1e-111">DESCRIPTION</span></span>

<span data-ttu-id="1ce1e-112">`Set-Clipboard`Командлет задает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-112">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="1ce1e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ce1e-113">EXAMPLES</span></span>

### <span data-ttu-id="1ce1e-114">Пример 1. копирование текста в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="1ce1e-114">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="1ce1e-115">Пример 2. копирование содержимого каталога в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="1ce1e-115">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="1ce1e-116">Эта команда копирует содержимое указанной папки в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-116">This command copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## <span data-ttu-id="1ce1e-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ce1e-117">PARAMETERS</span></span>

### <span data-ttu-id="1ce1e-118">— Добавление</span><span class="sxs-lookup"><span data-stu-id="1ce1e-118">-Append</span></span>

<span data-ttu-id="1ce1e-119">Указывает, что командлет не очищает буфер обмена и добавляет к нему содержимое.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-119">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-120">-Аштмл</span><span class="sxs-lookup"><span data-stu-id="1ce1e-120">-AsHtml</span></span>

<span data-ttu-id="1ce1e-121">Указывает, что командлет преобразует содержимое в HTML-код в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-121">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1ce1e-122">-LiteralPath</span></span>

<span data-ttu-id="1ce1e-123">Задает путь к элементу, который копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-123">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="1ce1e-124">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-124">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1ce1e-125">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1ce1e-126">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1ce1e-127">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-127">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-128">-Path</span><span class="sxs-lookup"><span data-stu-id="1ce1e-128">-Path</span></span>

<span data-ttu-id="1ce1e-129">Задает путь к элементу, который копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-129">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="1ce1e-130">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="1ce1e-131">-Value</span><span class="sxs-lookup"><span data-stu-id="1ce1e-131">-Value</span></span>

<span data-ttu-id="1ce1e-132">Указывает в виде массива строк содержимое для копирования в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-132">Specifies, as a string array, the content to copy to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1ce1e-133">-Confirm</span></span>

<span data-ttu-id="1ce1e-134">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-134">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1ce1e-135">-WhatIf</span></span>

<span data-ttu-id="1ce1e-136">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1ce1e-137">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-137">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ce1e-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1ce1e-138">CommonParameters</span></span>

<span data-ttu-id="1ce1e-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ce1e-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ce1e-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ce1e-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1ce1e-141">INPUTS</span></span>

### <span data-ttu-id="1ce1e-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1ce1e-142">System.String[]</span></span>

## <span data-ttu-id="1ce1e-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1ce1e-143">OUTPUTS</span></span>

## <span data-ttu-id="1ce1e-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1ce1e-144">NOTES</span></span>

<span data-ttu-id="1ce1e-145">В редких случаях при `Set-Clipboard` быстром выполнении с большим количеством значений, например в цикле, вы можете регулярно получать пустое значение из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-145">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="1ce1e-146">Это можно исправить с помощью `Start-Sleep -Milliseconds 1` в цикле.</span><span class="sxs-lookup"><span data-stu-id="1ce1e-146">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="1ce1e-147">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1ce1e-147">RELATED LINKS</span></span>

[<span data-ttu-id="1ce1e-148">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="1ce1e-148">Get-Clipboard</span></span>](Get-Clipboard.md)
