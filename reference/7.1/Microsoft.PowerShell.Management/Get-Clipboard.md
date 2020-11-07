---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 5fce0c872871006dd760ee8df2fb692faaa1aab9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342371"
---
# <span data-ttu-id="d3496-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d3496-103">Get-Clipboard</span></span>

## <span data-ttu-id="d3496-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d3496-104">SYNOPSIS</span></span>
<span data-ttu-id="d3496-105">Возвращает содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="d3496-105">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="d3496-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3496-106">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="d3496-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3496-107">DESCRIPTION</span></span>

<span data-ttu-id="d3496-108">`Get-Clipboard`Командлет получает содержимое буфера обмена в виде текста.</span><span class="sxs-lookup"><span data-stu-id="d3496-108">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="d3496-109">Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="d3496-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="d3496-110">В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.</span><span class="sxs-lookup"><span data-stu-id="d3496-110">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span> <span data-ttu-id="d3496-111">Этот командлет не поддерживается в macOS.</span><span class="sxs-lookup"><span data-stu-id="d3496-111">This cmdlet is not supported on macOS.</span></span>

## <span data-ttu-id="d3496-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="d3496-112">EXAMPLES</span></span>

### <span data-ttu-id="d3496-113">Пример 1. получение содержимого буфера обмена и его отображение в командной строке</span><span class="sxs-lookup"><span data-stu-id="d3496-113">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="d3496-114">В этом примере мы скопировали текст "Hello" в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d3496-114">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="d3496-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3496-115">PARAMETERS</span></span>

### <span data-ttu-id="d3496-116">-RAW</span><span class="sxs-lookup"><span data-stu-id="d3496-116">-Raw</span></span>

<span data-ttu-id="d3496-117">Возвращает все содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="d3496-117">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="d3496-118">Многострочный текст возвращается в виде одной многострочной строки, а не массива строк.</span><span class="sxs-lookup"><span data-stu-id="d3496-118">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="d3496-119">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d3496-119">CommonParameters</span></span>

<span data-ttu-id="d3496-120">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3496-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3496-121">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3496-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3496-122">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d3496-122">INPUTS</span></span>

## <span data-ttu-id="d3496-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d3496-123">OUTPUTS</span></span>

### <span data-ttu-id="d3496-124">System.String</span><span class="sxs-lookup"><span data-stu-id="d3496-124">System.String</span></span>

## <span data-ttu-id="d3496-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d3496-125">NOTES</span></span>

## <span data-ttu-id="d3496-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d3496-126">RELATED LINKS</span></span>

[<span data-ttu-id="d3496-127">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d3496-127">Set-Clipboard</span></span>](Set-Clipboard.md)
