---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: c694e73e69c1e51ecf88f445684923ef5f19113f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604783"
---
# <span data-ttu-id="e5638-102">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="e5638-102">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="e5638-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e5638-103">SYNOPSIS</span></span>
<span data-ttu-id="e5638-104">Преобразование содержимого строки или файла в объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="e5638-104">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="e5638-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5638-105">SYNTAX</span></span>

### <span data-ttu-id="e5638-106">Паспарамсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e5638-106">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="e5638-107">литералпарамсет</span><span class="sxs-lookup"><span data-stu-id="e5638-107">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="e5638-108">инпутобжпарамсет</span><span class="sxs-lookup"><span data-stu-id="e5638-108">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="e5638-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5638-109">DESCRIPTION</span></span>

<span data-ttu-id="e5638-110">Этот командлет Преобразует указанное содержимое в **маркдовнинфо**.</span><span class="sxs-lookup"><span data-stu-id="e5638-110">This cmdlet converts the specified content into a **MarkdownInfo**.</span></span> <span data-ttu-id="e5638-111">При указании пути к файлу для параметра **path** содержимое файла преобразуется.</span><span class="sxs-lookup"><span data-stu-id="e5638-111">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="e5638-112">Выходной объект имеет три свойства:</span><span class="sxs-lookup"><span data-stu-id="e5638-112">The output object has three properties:</span></span>

- <span data-ttu-id="e5638-113">Свойство **Token** имеет дерево абстрактного синтаксиса (AST) преобразованного объекта</span><span class="sxs-lookup"><span data-stu-id="e5638-113">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="e5638-114">Свойство **HTML** имеет преобразование HTML для указанных входных данных</span><span class="sxs-lookup"><span data-stu-id="e5638-114">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="e5638-115">Свойство **VT100EncodedString** имеет преобразованную строку с escape-последовательностями ANSI (VT100), если был указан параметр **AsVT100EncodedString**</span><span class="sxs-lookup"><span data-stu-id="e5638-115">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="e5638-116">Этот командлет появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="e5638-116">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="e5638-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="e5638-117">EXAMPLES</span></span>

### <span data-ttu-id="e5638-118">Пример 1. Преобразование файла, содержащего Markdown-содержимое, в HTML</span><span class="sxs-lookup"><span data-stu-id="e5638-118">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="e5638-119">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="e5638-119">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="e5638-120">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-120">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="e5638-121">Свойство **HTML** имеет преобразованное в HTML содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-121">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="e5638-122">Пример 2. Преобразование файла, содержащего содержимое Markdown, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="e5638-122">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="e5638-123">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="e5638-123">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="e5638-124">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-124">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="e5638-125">Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-125">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="e5638-126">Пример 3. преобразование входного объекта, содержащего Markdown содержимое, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="e5638-126">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="e5638-127">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="e5638-127">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="e5638-128">Объект **FileInfo** из `Get-Item` преобразуется в строку в кодировке VT100.</span><span class="sxs-lookup"><span data-stu-id="e5638-128">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="e5638-129">Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-129">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="e5638-130">Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.</span><span class="sxs-lookup"><span data-stu-id="e5638-130">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="e5638-131">Пример 4. Преобразование строки, содержащей содержимое Markdown, в строку в кодировке VT100</span><span class="sxs-lookup"><span data-stu-id="e5638-131">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="e5638-132">Возвращается объект **маркдовнинфо** .</span><span class="sxs-lookup"><span data-stu-id="e5638-132">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="e5638-133">Указанная строка `**Bold text**` преобразуется в строку в кодировке VT100 и доступна в свойстве **VT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="e5638-133">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="e5638-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5638-134">PARAMETERS</span></span>

### <span data-ttu-id="e5638-135">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="e5638-135">-AsVT100EncodedString</span></span>

<span data-ttu-id="e5638-136">Указывает, следует ли кодировать выходные данные как строку с escape-кодами VT100.</span><span class="sxs-lookup"><span data-stu-id="e5638-136">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="e5638-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e5638-137">-InputObject</span></span>

<span data-ttu-id="e5638-138">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="e5638-138">Specifies the object to be converted.</span></span> <span data-ttu-id="e5638-139">Если объект типа **System. String** указан, строка преобразуется.</span><span class="sxs-lookup"><span data-stu-id="e5638-139">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="e5638-140">При указании объекта типа **System. IO. FileInfo** содержимое файла, указанного в объекте, преобразуется.</span><span class="sxs-lookup"><span data-stu-id="e5638-140">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="e5638-141">Объекты любого другого типа приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="e5638-141">Objects of any other type result in an error.</span></span>

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

### <span data-ttu-id="e5638-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e5638-142">-LiteralPath</span></span>

<span data-ttu-id="e5638-143">Указывает путь к файлу для преобразования.</span><span class="sxs-lookup"><span data-stu-id="e5638-143">Specifies a path to the file to be converted.</span></span>

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

### <span data-ttu-id="e5638-144">-Path</span><span class="sxs-lookup"><span data-stu-id="e5638-144">-Path</span></span>

<span data-ttu-id="e5638-145">Указывает путь к файлу для преобразования.</span><span class="sxs-lookup"><span data-stu-id="e5638-145">Specifies a path to the file to be converted.</span></span>

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

### <span data-ttu-id="e5638-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e5638-146">CommonParameters</span></span>

<span data-ttu-id="e5638-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5638-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5638-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e5638-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5638-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e5638-149">INPUTS</span></span>

### <span data-ttu-id="e5638-150">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="e5638-150">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="e5638-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e5638-151">OUTPUTS</span></span>

### <span data-ttu-id="e5638-152">Microsoft. PowerShell. Маркдовнрендер. Маркдовнинфо</span><span class="sxs-lookup"><span data-stu-id="e5638-152">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="e5638-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e5638-153">NOTES</span></span>

## <span data-ttu-id="e5638-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e5638-154">RELATED LINKS</span></span>

[<span data-ttu-id="e5638-155">Средство синтаксического анализа Markdown</span><span class="sxs-lookup"><span data-stu-id="e5638-155">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="e5638-156">Escape-код ANSI</span><span class="sxs-lookup"><span data-stu-id="e5638-156">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)

