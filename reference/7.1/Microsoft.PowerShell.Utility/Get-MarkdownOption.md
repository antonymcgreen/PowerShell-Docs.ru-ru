---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: 52c0a94304156a7c1cf89bbc5ae98a0668789bd2
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "93208969"
---
# <span data-ttu-id="8f08f-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="8f08f-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="8f08f-102">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8f08f-102">SYNOPSIS</span></span>
<span data-ttu-id="8f08f-103">Возвращает текущие цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="8f08f-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="8f08f-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f08f-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="8f08f-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f08f-105">DESCRIPTION</span></span>

<span data-ttu-id="8f08f-106">Возвращает текущие цвета и стили, используемые для отрисовки содержимого Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="8f08f-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="8f08f-107">Строки, отображаемые в выходных данных этого командлета, содержат Escape-коды ANSI, используемые для изменения цвета и стиля отображаемого текста Markdown.</span><span class="sxs-lookup"><span data-stu-id="8f08f-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="8f08f-108">Дополнительные сведения о Markdown см. на веб-сайте [коммонмарк](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="8f08f-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="8f08f-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f08f-109">EXAMPLES</span></span>

### <span data-ttu-id="8f08f-110">Пример 1. Получение текущих цветов и стилей</span><span class="sxs-lookup"><span data-stu-id="8f08f-110">Example 1 - Get the current colors and style</span></span>

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
> <span data-ttu-id="8f08f-111">Строковые значения, приведенные в выходных данных, — это символы, которые следуют за **escape** -символом ( `[char]0x1B` ) для escape – последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="8f08f-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="8f08f-112">Дополнительные сведения о работе с управляющими escape-кодами ANSI см. в разделе [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="8f08f-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="8f08f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f08f-113">PARAMETERS</span></span>

### <span data-ttu-id="8f08f-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8f08f-114">CommonParameters</span></span>

<span data-ttu-id="8f08f-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f08f-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f08f-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f08f-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f08f-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8f08f-117">INPUTS</span></span>

### <span data-ttu-id="8f08f-118">Нет</span><span class="sxs-lookup"><span data-stu-id="8f08f-118">None</span></span>

## <span data-ttu-id="8f08f-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8f08f-119">OUTPUTS</span></span>

### <span data-ttu-id="8f08f-120">Microsoft. PowerShell. Маркдовнрендер. Псмаркдовноптионинфо</span><span class="sxs-lookup"><span data-stu-id="8f08f-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="8f08f-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8f08f-121">NOTES</span></span>

## <span data-ttu-id="8f08f-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8f08f-122">RELATED LINKS</span></span>

[<span data-ttu-id="8f08f-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="8f08f-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="8f08f-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="8f08f-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="8f08f-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="8f08f-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="8f08f-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="8f08f-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="8f08f-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="8f08f-127">CommonMark</span></span>](https://commonmark.org/)

