---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: d14e6332a2da5c86c4f8ada0d110c64e080437e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600479"
---
# <span data-ttu-id="5e237-102">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="5e237-102">Show-Markdown</span></span>

## <span data-ttu-id="5e237-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5e237-103">SYNOPSIS</span></span>
<span data-ttu-id="5e237-104">Показывает Markdown файл или строку в консоли с помощью escape-последовательностей VT100 или в браузере, использующем HTML.</span><span class="sxs-lookup"><span data-stu-id="5e237-104">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="5e237-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5e237-105">SYNTAX</span></span>

### <span data-ttu-id="5e237-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5e237-106">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="5e237-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="5e237-107">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="5e237-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5e237-108">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="5e237-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5e237-109">DESCRIPTION</span></span>

<span data-ttu-id="5e237-110">`Show-Markdown`Командлет используется для визуализации Markdown в удобном для чтения формате либо в терминале, либо в браузере.</span><span class="sxs-lookup"><span data-stu-id="5e237-110">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="5e237-111">`Show-Markdown` может возвращать строку, включающую escape-последовательности VT100, которые отрисовывается терминалом (если он поддерживает escape-последовательности VT100).</span><span class="sxs-lookup"><span data-stu-id="5e237-111">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="5e237-112">В основном это используется для просмотра файлов Markdown в терминале.</span><span class="sxs-lookup"><span data-stu-id="5e237-112">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="5e237-113">Эту строку также можно получить через, `ConvertFrom-Markdown` указав параметр **AsVT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="5e237-113">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="5e237-114">`Show-Markdown` также имеет возможность открыть браузер и отобразить подготовленную версию Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e237-114">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="5e237-115">Он отображает Markdown, преобразуя его в HTML и открывая HTML-файл в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e237-115">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="5e237-116">Вы можете изменить способ `Show-Markdown` отрисовки Markdown в терминале с помощью `Set-MarkdownOption` .</span><span class="sxs-lookup"><span data-stu-id="5e237-116">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="5e237-117">Этот командлет появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="5e237-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="5e237-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="5e237-118">EXAMPLES</span></span>

### <span data-ttu-id="5e237-119">Пример 1. простой пример указания пути</span><span class="sxs-lookup"><span data-stu-id="5e237-119">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="5e237-120">Пример 2. простой пример указания строки</span><span class="sxs-lookup"><span data-stu-id="5e237-120">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="5e237-121">Пример 2. Открытие Markdown в браузере</span><span class="sxs-lookup"><span data-stu-id="5e237-121">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="5e237-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5e237-122">PARAMETERS</span></span>

### <span data-ttu-id="5e237-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5e237-123">-InputObject</span></span>

<span data-ttu-id="5e237-124">Строка Markdown, которая будет отображаться в терминале.</span><span class="sxs-lookup"><span data-stu-id="5e237-124">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="5e237-125">Если не передать поддерживаемый формат, выдаст `Show-Markdown` ошибку.</span><span class="sxs-lookup"><span data-stu-id="5e237-125">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

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

### <span data-ttu-id="5e237-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5e237-126">-LiteralPath</span></span>

<span data-ttu-id="5e237-127">Указывает путь к Markdown-файлу.</span><span class="sxs-lookup"><span data-stu-id="5e237-127">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="5e237-128">В отличие от параметра Path, значение LiteralPath используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="5e237-128">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="5e237-129">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="5e237-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5e237-130">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="5e237-130">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5e237-131">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="5e237-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="5e237-132">-Path</span><span class="sxs-lookup"><span data-stu-id="5e237-132">-Path</span></span>

<span data-ttu-id="5e237-133">Указывает путь к файлу Markdown для подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="5e237-133">Specifies the path to a Markdown file to be rendered.</span></span>

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

### <span data-ttu-id="5e237-134">-Усебровсер</span><span class="sxs-lookup"><span data-stu-id="5e237-134">-UseBrowser</span></span>

<span data-ttu-id="5e237-135">Компилирует входные данные Markdown в формате HTML и открывает их в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e237-135">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

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

### <span data-ttu-id="5e237-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5e237-136">CommonParameters</span></span>

<span data-ttu-id="5e237-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5e237-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e237-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5e237-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e237-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5e237-139">INPUTS</span></span>

### <span data-ttu-id="5e237-140">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="5e237-140">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="5e237-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="5e237-141">System.String[]</span></span>

## <span data-ttu-id="5e237-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5e237-142">OUTPUTS</span></span>

### <span data-ttu-id="5e237-143">System.String</span><span class="sxs-lookup"><span data-stu-id="5e237-143">System.String</span></span>

## <span data-ttu-id="5e237-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5e237-144">NOTES</span></span>

## <span data-ttu-id="5e237-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5e237-145">RELATED LINKS</span></span>

[<span data-ttu-id="5e237-146">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="5e237-146">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

