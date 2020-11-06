---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: f39add03a3b0250172cbb117a4233bb01958d9d3
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "93229641"
---
# <span data-ttu-id="7bbde-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="7bbde-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="7bbde-102">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7bbde-102">SYNOPSIS</span></span>
<span data-ttu-id="7bbde-103">Возвращает текущие цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="7bbde-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="7bbde-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7bbde-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="7bbde-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7bbde-105">DESCRIPTION</span></span>

<span data-ttu-id="7bbde-106">Возвращает текущие цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="7bbde-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="7bbde-107">Строки, отображаемые в выходных данных этого командлета, содержат Escape-коды ANSI, используемые для изменения цвета и стиля отображаемого текста Markdown.</span><span class="sxs-lookup"><span data-stu-id="7bbde-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="7bbde-108">Дополнительные сведения о Markdown см. на веб-сайте [коммонмарк](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="7bbde-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="7bbde-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="7bbde-109">EXAMPLES</span></span>

### <span data-ttu-id="7bbde-110">Пример 1. Получение текущих цветов и стилей</span><span class="sxs-lookup"><span data-stu-id="7bbde-110">Example 1 - Get the current colors and style</span></span>

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> <span data-ttu-id="7bbde-111">Строковые значения, приведенные в выходных данных, — это символы, которые следуют за **escape** -символом ( `[char]0x1B` ) для escape – последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="7bbde-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="7bbde-112">Дополнительные сведения о работе с управляющими escape-кодами ANSI см. в разделе [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="7bbde-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="7bbde-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7bbde-113">PARAMETERS</span></span>

### <span data-ttu-id="7bbde-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7bbde-114">CommonParameters</span></span>

<span data-ttu-id="7bbde-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7bbde-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7bbde-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7bbde-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7bbde-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7bbde-117">INPUTS</span></span>

### <span data-ttu-id="7bbde-118">Нет</span><span class="sxs-lookup"><span data-stu-id="7bbde-118">None</span></span>

## <span data-ttu-id="7bbde-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7bbde-119">OUTPUTS</span></span>

### <span data-ttu-id="7bbde-120">Microsoft. PowerShell. Маркдовнрендер. Псмаркдовноптионинфо</span><span class="sxs-lookup"><span data-stu-id="7bbde-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="7bbde-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7bbde-121">NOTES</span></span>

## <span data-ttu-id="7bbde-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7bbde-122">RELATED LINKS</span></span>

[<span data-ttu-id="7bbde-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="7bbde-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="7bbde-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="7bbde-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="7bbde-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="7bbde-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="7bbde-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="7bbde-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="7bbde-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="7bbde-127">CommonMark</span></span>](https://commonmark.org/)