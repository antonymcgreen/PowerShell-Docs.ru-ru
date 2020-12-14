---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c1cf126e41a5e918afffbc41d30f957e650efdf5
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564508"
---
# <span data-ttu-id="5b03e-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="5b03e-102">Set-Clipboard</span></span>

## <span data-ttu-id="5b03e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5b03e-103">SYNOPSIS</span></span>
<span data-ttu-id="5b03e-104">Задает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="5b03e-104">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="5b03e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b03e-105">SYNTAX</span></span>

### <span data-ttu-id="5b03e-106">Строка (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5b03e-106">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5b03e-107">Значение</span><span class="sxs-lookup"><span data-stu-id="5b03e-107">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5b03e-108">Путь</span><span class="sxs-lookup"><span data-stu-id="5b03e-108">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5b03e-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5b03e-109">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5b03e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b03e-110">DESCRIPTION</span></span>

<span data-ttu-id="5b03e-111">`Set-Clipboard`Командлет задает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="5b03e-111">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="5b03e-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="5b03e-112">EXAMPLES</span></span>

### <span data-ttu-id="5b03e-113">Пример 1. копирование текста в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="5b03e-113">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="5b03e-114">Пример 2. копирование содержимого каталога в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="5b03e-114">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="5b03e-115">В этом примере содержимое указанной папки копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-115">This example copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

### <span data-ttu-id="5b03e-116">Пример 3. копирование содержимого файла в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="5b03e-116">Example 3: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="5b03e-117">В этом примере содержимое файла переводится в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-117">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="5b03e-118">В этом примере мы получаем открытый ключ SSH, чтобы его можно было вставлять в другое приложение, например GitHub.</span><span class="sxs-lookup"><span data-stu-id="5b03e-118">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="5b03e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b03e-119">PARAMETERS</span></span>

### <span data-ttu-id="5b03e-120">— Добавление</span><span class="sxs-lookup"><span data-stu-id="5b03e-120">-Append</span></span>

<span data-ttu-id="5b03e-121">Указывает, что командлет не очищает буфер обмена и добавляет к нему содержимое.</span><span class="sxs-lookup"><span data-stu-id="5b03e-121">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="5b03e-122">-Аштмл</span><span class="sxs-lookup"><span data-stu-id="5b03e-122">-AsHtml</span></span>

<span data-ttu-id="5b03e-123">Указывает, что командлет преобразует содержимое в HTML-код в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-123">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="5b03e-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5b03e-124">-LiteralPath</span></span>

<span data-ttu-id="5b03e-125">Задает путь к элементу, который копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-125">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="5b03e-126">В отличие от параметра **Path**, значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="5b03e-126">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5b03e-127">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="5b03e-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5b03e-128">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="5b03e-128">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5b03e-129">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="5b03e-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="5b03e-130">-Path</span><span class="sxs-lookup"><span data-stu-id="5b03e-130">-Path</span></span>

<span data-ttu-id="5b03e-131">Задает путь к элементу, который копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-131">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="5b03e-132">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5b03e-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5b03e-133">-Value</span><span class="sxs-lookup"><span data-stu-id="5b03e-133">-Value</span></span>

<span data-ttu-id="5b03e-134">Указывает в виде массива строк содержимое для копирования в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-134">Specifies, as a string array, the content to copy to the clipboard.</span></span>

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

### <span data-ttu-id="5b03e-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5b03e-135">-Confirm</span></span>

<span data-ttu-id="5b03e-136">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5b03e-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5b03e-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5b03e-137">-WhatIf</span></span>

<span data-ttu-id="5b03e-138">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5b03e-138">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5b03e-139">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5b03e-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5b03e-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5b03e-140">CommonParameters</span></span>

<span data-ttu-id="5b03e-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b03e-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b03e-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5b03e-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5b03e-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5b03e-143">INPUTS</span></span>

### <span data-ttu-id="5b03e-144">System.String[]</span><span class="sxs-lookup"><span data-stu-id="5b03e-144">System.String[]</span></span>

## <span data-ttu-id="5b03e-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5b03e-145">OUTPUTS</span></span>

## <span data-ttu-id="5b03e-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5b03e-146">NOTES</span></span>

<span data-ttu-id="5b03e-147">В редких случаях при `Set-Clipboard` быстром выполнении с большим количеством значений, например в цикле, вы можете регулярно получать пустое значение из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="5b03e-147">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="5b03e-148">Это можно исправить с помощью `Start-Sleep -Milliseconds 1` в цикле.</span><span class="sxs-lookup"><span data-stu-id="5b03e-148">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="5b03e-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5b03e-149">RELATED LINKS</span></span>

[<span data-ttu-id="5b03e-150">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="5b03e-150">Get-Clipboard</span></span>](Get-Clipboard.md)
