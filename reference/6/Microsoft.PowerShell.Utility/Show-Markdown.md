---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: 2d88b24519f472f0c167dc5138450ab542a8b7cf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228774"
---
# <span data-ttu-id="b4dd7-103">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="b4dd7-103">Show-Markdown</span></span>

## <span data-ttu-id="b4dd7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b4dd7-104">SYNOPSIS</span></span>
<span data-ttu-id="b4dd7-105">Показывает Markdown файл или строку в консоли с помощью escape-последовательностей VT100 или в браузере, использующем HTML.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-105">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="b4dd7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4dd7-106">SYNTAX</span></span>

### <span data-ttu-id="b4dd7-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b4dd7-107">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="b4dd7-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="b4dd7-108">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="b4dd7-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b4dd7-109">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="b4dd7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4dd7-110">DESCRIPTION</span></span>

<span data-ttu-id="b4dd7-111">`Show-Markdown`Командлет используется для визуализации Markdown в удобном для чтения формате либо в терминале, либо в браузере.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-111">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="b4dd7-112">`Show-Markdown` может возвращать строку, включающую escape-последовательности VT100, которые отрисовывается терминалом (если он поддерживает escape-последовательности VT100).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-112">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="b4dd7-113">В основном это используется для просмотра файлов Markdown в терминале.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-113">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="b4dd7-114">Эту строку также можно получить через, `ConvertFrom-Markdown` указав параметр **AsVT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="b4dd7-114">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="b4dd7-115">`Show-Markdown` также имеет возможность открыть браузер и отобразить подготовленную версию Markdown.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-115">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="b4dd7-116">Он отображает Markdown, преобразуя его в HTML и открывая HTML-файл в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-116">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="b4dd7-117">Вы можете изменить способ `Show-Markdown` отрисовки Markdown в терминале с помощью `Set-MarkdownOption` .</span><span class="sxs-lookup"><span data-stu-id="b4dd7-117">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="b4dd7-118">Этот командлет появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-118">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="b4dd7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="b4dd7-119">EXAMPLES</span></span>

### <span data-ttu-id="b4dd7-120">Пример 1. простой пример указания пути</span><span class="sxs-lookup"><span data-stu-id="b4dd7-120">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="b4dd7-121">Пример 2. простой пример указания строки</span><span class="sxs-lookup"><span data-stu-id="b4dd7-121">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="b4dd7-122">Пример 2. Открытие Markdown в браузере</span><span class="sxs-lookup"><span data-stu-id="b4dd7-122">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="b4dd7-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4dd7-123">PARAMETERS</span></span>

### <span data-ttu-id="b4dd7-124">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b4dd7-124">-InputObject</span></span>

<span data-ttu-id="b4dd7-125">Строка Markdown, которая будет отображаться в терминале.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-125">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="b4dd7-126">Если не передать поддерживаемый формат, выдаст `Show-Markdown` ошибку.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-126">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b4dd7-127">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b4dd7-127">-LiteralPath</span></span>

<span data-ttu-id="b4dd7-128">Указывает путь к Markdown-файлу.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-128">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="b4dd7-129">В отличие от параметра Path, значение LiteralPath используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-129">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="b4dd7-130">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-130">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b4dd7-131">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-131">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b4dd7-132">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-132">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b4dd7-133">-Path</span><span class="sxs-lookup"><span data-stu-id="b4dd7-133">-Path</span></span>

<span data-ttu-id="b4dd7-134">Указывает путь к файлу Markdown для подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-134">Specifies the path to a Markdown file to be rendered.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b4dd7-135">-Усебровсер</span><span class="sxs-lookup"><span data-stu-id="b4dd7-135">-UseBrowser</span></span>

<span data-ttu-id="b4dd7-136">Компилирует входные данные Markdown в формате HTML и открывает их в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-136">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4dd7-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b4dd7-137">CommonParameters</span></span>

<span data-ttu-id="b4dd7-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4dd7-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4dd7-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b4dd7-140">INPUTS</span></span>

### <span data-ttu-id="b4dd7-141">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b4dd7-141">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="b4dd7-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b4dd7-142">System.String[]</span></span>

## <span data-ttu-id="b4dd7-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b4dd7-143">OUTPUTS</span></span>

### <span data-ttu-id="b4dd7-144">System.String</span><span class="sxs-lookup"><span data-stu-id="b4dd7-144">System.String</span></span>

## <span data-ttu-id="b4dd7-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b4dd7-145">NOTES</span></span>

## <span data-ttu-id="b4dd7-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b4dd7-146">RELATED LINKS</span></span>

[<span data-ttu-id="b4dd7-147">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="b4dd7-147">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)
