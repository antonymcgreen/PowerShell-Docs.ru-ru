---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230681"
---
# <span data-ttu-id="bf009-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="bf009-103">Get-Clipboard</span></span>

## <span data-ttu-id="bf009-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bf009-104">SYNOPSIS</span></span>
<span data-ttu-id="bf009-105">Возвращает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="bf009-105">Gets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="bf009-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bf009-106">SYNTAX</span></span>

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="bf009-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bf009-107">DESCRIPTION</span></span>

<span data-ttu-id="bf009-108">`Get-Clipboard`Командлет возвращает текущую запись в буфере обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="bf009-108">The `Get-Clipboard` cmdlet gets the current Windows clipboard entry.</span></span> <span data-ttu-id="bf009-109">Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="bf009-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="bf009-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="bf009-110">EXAMPLES</span></span>

### <span data-ttu-id="bf009-111">Пример 1. получение содержимого буфера обмена и его отображение в командной строке</span><span class="sxs-lookup"><span data-stu-id="bf009-111">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="bf009-112">В этом примере мы щелкнули правой кнопкой мыши изображение в браузере и выбрали действие **копирования** .</span><span class="sxs-lookup"><span data-stu-id="bf009-112">In this example we have right-clicked on an image in a browser and chose the **Copy** action.</span></span> <span data-ttu-id="bf009-113">Следующая команда отображает ссылку в виде URL-адреса изображения, хранящегося в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="bf009-113">The following command displays the link, as a URL, of the image that is stored in the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### <span data-ttu-id="bf009-114">Пример 2. получение содержимого буфера обмена в определенном формате</span><span class="sxs-lookup"><span data-stu-id="bf009-114">Example 2: Get the content of the clipboard in a specific format</span></span>

<span data-ttu-id="bf009-115">В этом примере мы скопировали файлы в буфер обмена в Windows Експлорерби, выбрав их и нажав клавиши <kbd>CTRL + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="bf009-115">In this example we copied files to the clipboard in Windows Explorerby selecting them and pressing <kbd>Ctrl-C</kbd>.</span></span> <span data-ttu-id="bf009-116">С помощью следующей команды можно получить доступ к содержимому буфера обмена в виде списка файлов:</span><span class="sxs-lookup"><span data-stu-id="bf009-116">Using the following command, you can access the contents of the clipboard as a list of files:</span></span>

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## <span data-ttu-id="bf009-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bf009-117">PARAMETERS</span></span>

### <span data-ttu-id="bf009-118">-Format</span><span class="sxs-lookup"><span data-stu-id="bf009-118">-Format</span></span>

<span data-ttu-id="bf009-119">Задает тип или формат буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="bf009-119">Specifies the type, or format, of the clipboard.</span></span> <span data-ttu-id="bf009-120">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bf009-120">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bf009-121">Текст</span><span class="sxs-lookup"><span data-stu-id="bf009-121">Text</span></span>
- <span data-ttu-id="bf009-122">филедроплист</span><span class="sxs-lookup"><span data-stu-id="bf009-122">FileDropList</span></span>
- <span data-ttu-id="bf009-123">Образ —</span><span class="sxs-lookup"><span data-stu-id="bf009-123">Image</span></span>
- <span data-ttu-id="bf009-124">Аудио</span><span class="sxs-lookup"><span data-stu-id="bf009-124">Audio</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf009-125">-RAW</span><span class="sxs-lookup"><span data-stu-id="bf009-125">-Raw</span></span>

<span data-ttu-id="bf009-126">Возвращает все содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="bf009-126">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="bf009-127">Многострочный текст возвращается в виде одной многострочной строки, а не массива строк.</span><span class="sxs-lookup"><span data-stu-id="bf009-127">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="bf009-128">-Текстформаттипе</span><span class="sxs-lookup"><span data-stu-id="bf009-128">-TextFormatType</span></span>

<span data-ttu-id="bf009-129">Задает тип формата текстовых данных буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="bf009-129">Specifies the text data format type of the clipboard.</span></span> <span data-ttu-id="bf009-130">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bf009-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bf009-131">Текст</span><span class="sxs-lookup"><span data-stu-id="bf009-131">Text</span></span>
- <span data-ttu-id="bf009-132">уникодетекст</span><span class="sxs-lookup"><span data-stu-id="bf009-132">UnicodeText</span></span>
- <span data-ttu-id="bf009-133">RTF</span><span class="sxs-lookup"><span data-stu-id="bf009-133">Rtf</span></span>
- <span data-ttu-id="bf009-134">Html</span><span class="sxs-lookup"><span data-stu-id="bf009-134">Html</span></span>
- <span data-ttu-id="bf009-135">коммасепаратедвалуе</span><span class="sxs-lookup"><span data-stu-id="bf009-135">CommaSeparatedValue</span></span>

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf009-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bf009-136">CommonParameters</span></span>

<span data-ttu-id="bf009-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bf009-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bf009-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bf009-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bf009-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bf009-139">INPUTS</span></span>

## <span data-ttu-id="bf009-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bf009-140">OUTPUTS</span></span>

### <span data-ttu-id="bf009-141">System. String, System. IO. FileInfo, System. IO. Stream, System. Drawing. Image</span><span class="sxs-lookup"><span data-stu-id="bf009-141">System.String, System.IO.FileInfo, System.IO.Stream, System.Drawing.Image</span></span>

## <span data-ttu-id="bf009-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bf009-142">NOTES</span></span>

## <span data-ttu-id="bf009-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bf009-143">RELATED LINKS</span></span>

[<span data-ttu-id="bf009-144">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="bf009-144">Set-Clipboard</span></span>](Set-Clipboard.md)
