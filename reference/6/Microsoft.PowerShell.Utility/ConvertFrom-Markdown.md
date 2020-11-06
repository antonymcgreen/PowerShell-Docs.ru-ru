---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, командлет, Markdown
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: efa5e65566e3b80f12f3de5ebd1277bf68c03ff0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229082"
---
# <span data-ttu-id="96f80-103">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="96f80-103">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="96f80-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="96f80-104">SYNOPSIS</span></span>
<span data-ttu-id="96f80-105">Преобразование содержимого строки или файла в объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-105">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="96f80-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96f80-106">SYNTAX</span></span>

### <span data-ttu-id="96f80-107">Паспарамсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="96f80-107">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="96f80-108">литералпарамсет</span><span class="sxs-lookup"><span data-stu-id="96f80-108">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="96f80-109">инпутобжпарамсет</span><span class="sxs-lookup"><span data-stu-id="96f80-109">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="96f80-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96f80-110">DESCRIPTION</span></span>

<span data-ttu-id="96f80-111">Этот командлет Преобразует указанное содержимое в **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-111">This cmdlet converts the specified content into a **MarkdownInfo** .</span></span> <span data-ttu-id="96f80-112">При указании пути к файлу для параметра **path** содержимое файла преобразуется.</span><span class="sxs-lookup"><span data-stu-id="96f80-112">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="96f80-113">Выходной объект имеет три свойства:</span><span class="sxs-lookup"><span data-stu-id="96f80-113">The output object has three properties:</span></span>

- <span data-ttu-id="96f80-114">Свойство **Token** имеет дерево абстрактного синтаксиса (AST) преобразованного объекта</span><span class="sxs-lookup"><span data-stu-id="96f80-114">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="96f80-115">Свойство **HTML** имеет преобразование HTML для указанных входных данных</span><span class="sxs-lookup"><span data-stu-id="96f80-115">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="96f80-116">Свойство **VT100EncodedString** имеет преобразованную строку с escape-последовательностями ANSI (VT100), если был указан параметр **AsVT100EncodedString**</span><span class="sxs-lookup"><span data-stu-id="96f80-116">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="96f80-117">Этот командлет появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="96f80-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="96f80-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="96f80-118">EXAMPLES</span></span>

### <span data-ttu-id="96f80-119">Пример 1. Преобразование файла, содержащего Markdown-содержимое, в HTML</span><span class="sxs-lookup"><span data-stu-id="96f80-119">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="96f80-120">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-120">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="96f80-121">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-121">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="96f80-122">Свойство **HTML** имеет преобразованное в HTML содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-122">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="96f80-123">Пример 2. Преобразование файла, содержащего содержимое Markdown, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="96f80-123">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="96f80-124">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-124">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="96f80-125">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-125">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="96f80-126">Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-126">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="96f80-127">Пример 3. преобразование входного объекта, содержащего Markdown содержимое, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="96f80-127">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="96f80-128">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-128">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="96f80-129">Объект **FileInfo** из `Get-Item` преобразуется в строку в кодировке VT100.</span><span class="sxs-lookup"><span data-stu-id="96f80-129">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="96f80-130">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-130">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="96f80-131">Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="96f80-131">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="96f80-132">Пример 4. Преобразование строки, содержащей содержимое Markdown, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="96f80-132">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="96f80-133">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="96f80-133">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="96f80-134">Указанная строка `**Bold text**` преобразуется в строку в кодировке VT100 и доступна в свойстве **VT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="96f80-134">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="96f80-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96f80-135">PARAMETERS</span></span>

### <span data-ttu-id="96f80-136">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="96f80-136">-AsVT100EncodedString</span></span>

<span data-ttu-id="96f80-137">Указывает, следует ли кодировать выходные данные как строку с escape-кодами VT100.</span><span class="sxs-lookup"><span data-stu-id="96f80-137">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="96f80-138">-InputObject</span><span class="sxs-lookup"><span data-stu-id="96f80-138">-InputObject</span></span>

<span data-ttu-id="96f80-139">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="96f80-139">Specifies the object to be converted.</span></span> <span data-ttu-id="96f80-140">Если объект типа **System. String** указан, строка преобразуется.</span><span class="sxs-lookup"><span data-stu-id="96f80-140">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="96f80-141">При указании объекта типа **System. IO. FileInfo** содержимое файла, указанного в объекте, преобразуется.</span><span class="sxs-lookup"><span data-stu-id="96f80-141">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="96f80-142">Объекты любого другого типа приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="96f80-142">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="96f80-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="96f80-143">-LiteralPath</span></span>

<span data-ttu-id="96f80-144">Указывает путь к файлу для преобразования.</span><span class="sxs-lookup"><span data-stu-id="96f80-144">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96f80-145">-Path</span><span class="sxs-lookup"><span data-stu-id="96f80-145">-Path</span></span>

<span data-ttu-id="96f80-146">Указывает путь к файлу для преобразования.</span><span class="sxs-lookup"><span data-stu-id="96f80-146">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="96f80-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="96f80-147">CommonParameters</span></span>

<span data-ttu-id="96f80-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="96f80-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="96f80-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="96f80-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="96f80-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="96f80-150">INPUTS</span></span>

### <span data-ttu-id="96f80-151">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="96f80-151">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="96f80-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="96f80-152">OUTPUTS</span></span>

### <span data-ttu-id="96f80-153">Microsoft. PowerShell. Маркдовнрендер. Маркдовнинфо</span><span class="sxs-lookup"><span data-stu-id="96f80-153">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="96f80-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="96f80-154">NOTES</span></span>

## <span data-ttu-id="96f80-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="96f80-155">RELATED LINKS</span></span>

[<span data-ttu-id="96f80-156">Средство синтаксического анализа Markdown</span><span class="sxs-lookup"><span data-stu-id="96f80-156">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="96f80-157">Escape-код ANSI</span><span class="sxs-lookup"><span data-stu-id="96f80-157">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)