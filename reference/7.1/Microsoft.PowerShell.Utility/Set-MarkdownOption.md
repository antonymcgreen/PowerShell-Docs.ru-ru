---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e7e70637afcf53f84c719b489575f5267f9048b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226573"
---
# <span data-ttu-id="610a3-101">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="610a3-101">Set-MarkdownOption</span></span>

## <span data-ttu-id="610a3-102">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="610a3-102">SYNOPSIS</span></span>
<span data-ttu-id="610a3-103">Задает цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="610a3-103">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="610a3-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="610a3-104">SYNTAX</span></span>

### <span data-ttu-id="610a3-105">Индивидуалсеттинг (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="610a3-105">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="610a3-106">Тема</span><span class="sxs-lookup"><span data-stu-id="610a3-106">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="610a3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="610a3-107">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="610a3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="610a3-108">DESCRIPTION</span></span>

<span data-ttu-id="610a3-109">Задает цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="610a3-109">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="610a3-110">Эти стили определяются с помощью escape-кодов ANSI, которые изменяют цвет и стиль отображаемого текста Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-110">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="610a3-111">Дополнительные сведения о Markdown см. на веб-сайте [коммонмарк](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="610a3-111">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="610a3-112">Строковые значения, используемые в параметрах, — это символы, которые следуют за **escape** -символом ( `[char]0x1B` ) для управляющей последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="610a3-112">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="610a3-113">Не включайте **escape** -символ в строку.</span><span class="sxs-lookup"><span data-stu-id="610a3-113">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="610a3-114">Дополнительные сведения о работе с управляющими escape-кодами ANSI см. в разделе [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="610a3-114">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="610a3-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="610a3-115">EXAMPLES</span></span>

### <span data-ttu-id="610a3-116">Пример 1. Переход к светлой теме</span><span class="sxs-lookup"><span data-stu-id="610a3-116">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="610a3-117">В этом примере выбирается **светло** -тема и отображается новая конфигурация с помощью параметра **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="610a3-117">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### <span data-ttu-id="610a3-118">Пример 2. Настройка параметров цвета и стиля</span><span class="sxs-lookup"><span data-stu-id="610a3-118">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="610a3-119">В этом примере изменяется escape-код для заголовков Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-119">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="610a3-120">Конфигурация по умолчанию для заголовков отображает их в виде подчеркнутого текста различных цветов.</span><span class="sxs-lookup"><span data-stu-id="610a3-120">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="610a3-121">Это изменение приводит к удалению стиля подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="610a3-121">This change removes the underline style.</span></span>

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## <span data-ttu-id="610a3-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="610a3-122">PARAMETERS</span></span>

### <span data-ttu-id="610a3-123">-Болдфореграундколор</span><span class="sxs-lookup"><span data-stu-id="610a3-123">-BoldForegroundColor</span></span>

<span data-ttu-id="610a3-124">Задает цвет переднего плана для отрисовки полужирного Markdown текста.</span><span class="sxs-lookup"><span data-stu-id="610a3-124">Sets the foreground color for rendering bold Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-125">-Code</span><span class="sxs-lookup"><span data-stu-id="610a3-125">-Code</span></span>

<span data-ttu-id="610a3-126">Задает цвет для отрисовки блоков кода и диапазонов в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-126">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-127">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="610a3-127">-Header1Color</span></span>

<span data-ttu-id="610a3-128">Задает цвет для отрисовки блоков Header1 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-128">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-129">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="610a3-129">-Header2Color</span></span>

<span data-ttu-id="610a3-130">Задает цвет для отрисовки блоков Header2 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-130">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-131">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="610a3-131">-Header3Color</span></span>

<span data-ttu-id="610a3-132">Задает цвет для отрисовки блоков Header3 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-132">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-133">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="610a3-133">-Header4Color</span></span>

<span data-ttu-id="610a3-134">Задает цвет для отрисовки блоков Header4 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-134">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-135">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="610a3-135">-Header5Color</span></span>

<span data-ttu-id="610a3-136">Задает цвет для отрисовки блоков Header5 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-136">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-137">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="610a3-137">-Header6Color</span></span>

<span data-ttu-id="610a3-138">Задает цвет для отрисовки блоков Header6 в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-138">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-139">-Имажеалттекстфореграундколор</span><span class="sxs-lookup"><span data-stu-id="610a3-139">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="610a3-140">Задает цвет переднего плана для отрисовки альтернативного текста элемента изображения в Markdown тексте.</span><span class="sxs-lookup"><span data-stu-id="610a3-140">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="610a3-141">-InputObject</span></span>

<span data-ttu-id="610a3-142">Объект **псмаркдовноптионинфо** , содержащий конфигурацию, которую необходимо задать.</span><span class="sxs-lookup"><span data-stu-id="610a3-142">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-143">-Италиксфореграундколор</span><span class="sxs-lookup"><span data-stu-id="610a3-143">-ItalicsForegroundColor</span></span>

<span data-ttu-id="610a3-144">Задает цвет переднего плана для отрисовки курсивного начертания в тексте Markdown.</span><span class="sxs-lookup"><span data-stu-id="610a3-144">Sets the foreground color for rendering the italics in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-145">-Линкфореграундколор</span><span class="sxs-lookup"><span data-stu-id="610a3-145">-LinkForegroundColor</span></span>

<span data-ttu-id="610a3-146">Задает цвет переднего плана для отрисовки гиперссылок в Markdown тексте.</span><span class="sxs-lookup"><span data-stu-id="610a3-146">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="610a3-147">-PassThru</span></span>

<span data-ttu-id="610a3-148">Приводит к тому, что командлет выводит объект **псмаркдовноптионинфо** , содержащий новую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="610a3-148">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

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

### <span data-ttu-id="610a3-149">-Theme</span><span class="sxs-lookup"><span data-stu-id="610a3-149">-Theme</span></span>

<span data-ttu-id="610a3-150">Выбирает тему, содержащую предопределенные параметры цвета.</span><span class="sxs-lookup"><span data-stu-id="610a3-150">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="610a3-151">Возможные значения: **темный** и **светлый**.</span><span class="sxs-lookup"><span data-stu-id="610a3-151">The possible values are **Dark** and **Light**.</span></span>

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610a3-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="610a3-152">CommonParameters</span></span>

<span data-ttu-id="610a3-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="610a3-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="610a3-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="610a3-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="610a3-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="610a3-155">INPUTS</span></span>

### <span data-ttu-id="610a3-156">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="610a3-156">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="610a3-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="610a3-157">OUTPUTS</span></span>

### <span data-ttu-id="610a3-158">Microsoft. PowerShell. Маркдовнрендер. Псмаркдовноптионинфо</span><span class="sxs-lookup"><span data-stu-id="610a3-158">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="610a3-159">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="610a3-159">NOTES</span></span>

<span data-ttu-id="610a3-160">Строковые значения, используемые для определения цвета и стиля, должны соответствовать регулярному выражению `^\[*[0-9;]*?m{1}` .</span><span class="sxs-lookup"><span data-stu-id="610a3-160">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="610a3-161">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="610a3-161">RELATED LINKS</span></span>

[<span data-ttu-id="610a3-162">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="610a3-162">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="610a3-163">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="610a3-163">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="610a3-164">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="610a3-164">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="610a3-165">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="610a3-165">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="610a3-166">CommonMark</span><span class="sxs-lookup"><span data-stu-id="610a3-166">CommonMark</span></span>](https://commonmark.org/)
