---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: da1df360d7c471d925bd2f57f5258ecb2d60e631
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239985"
---
# <span data-ttu-id="cbeba-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="cbeba-103">Get-Clipboard</span></span>

## <span data-ttu-id="cbeba-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbeba-104">SYNOPSIS</span></span>
<span data-ttu-id="cbeba-105">Возвращает содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="cbeba-105">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="cbeba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cbeba-106">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="cbeba-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cbeba-107">DESCRIPTION</span></span>

<span data-ttu-id="cbeba-108">`Get-Clipboard`Командлет получает содержимое буфера обмена в виде текста.</span><span class="sxs-lookup"><span data-stu-id="cbeba-108">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="cbeba-109">Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="cbeba-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="cbeba-110">В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.</span><span class="sxs-lookup"><span data-stu-id="cbeba-110">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="cbeba-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="cbeba-111">EXAMPLES</span></span>

### <span data-ttu-id="cbeba-112">Пример 1. получение содержимого буфера обмена и его отображение в командной строке</span><span class="sxs-lookup"><span data-stu-id="cbeba-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="cbeba-113">В этом примере мы скопировали текст "Hello" в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="cbeba-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="cbeba-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cbeba-114">PARAMETERS</span></span>

### <span data-ttu-id="cbeba-115">-RAW</span><span class="sxs-lookup"><span data-stu-id="cbeba-115">-Raw</span></span>

<span data-ttu-id="cbeba-116">Возвращает все содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="cbeba-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="cbeba-117">Многострочный текст возвращается в виде одной многострочной строки, а не массива строк.</span><span class="sxs-lookup"><span data-stu-id="cbeba-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="cbeba-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cbeba-118">CommonParameters</span></span>

<span data-ttu-id="cbeba-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cbeba-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cbeba-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cbeba-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cbeba-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cbeba-121">INPUTS</span></span>

## <span data-ttu-id="cbeba-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cbeba-122">OUTPUTS</span></span>

### <span data-ttu-id="cbeba-123">System.String</span><span class="sxs-lookup"><span data-stu-id="cbeba-123">System.String</span></span>

## <span data-ttu-id="cbeba-124">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cbeba-124">NOTES</span></span>

## <span data-ttu-id="cbeba-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cbeba-125">RELATED LINKS</span></span>

[<span data-ttu-id="cbeba-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="cbeba-126">Set-Clipboard</span></span>](Set-Clipboard.md)

