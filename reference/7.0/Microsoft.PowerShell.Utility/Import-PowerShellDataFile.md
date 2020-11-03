---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: f25191d27013469023b9fcfb03650a8693c6ddb4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225530"
---
# <span data-ttu-id="2d433-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="2d433-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="2d433-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2d433-104">SYNOPSIS</span></span>
<span data-ttu-id="2d433-105">Импортирует значения из `.PSD1` файла без вызова его содержимого.</span><span class="sxs-lookup"><span data-stu-id="2d433-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="2d433-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d433-106">SYNTAX</span></span>

### <span data-ttu-id="2d433-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2d433-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2d433-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="2d433-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="2d433-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d433-109">DESCRIPTION</span></span>

<span data-ttu-id="2d433-110">`Import-PowerShellDataFile`Командлет безопасно импортирует пары "ключ-значение" из таблиц хэширования, определенных в `.PSD1` файле.</span><span class="sxs-lookup"><span data-stu-id="2d433-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="2d433-111">Значения можно импортировать с помощью `Invoke-Expression` на содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="2d433-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="2d433-112">Однако `Invoke-Expression` выполняет любой код, содержащийся в файле.</span><span class="sxs-lookup"><span data-stu-id="2d433-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="2d433-113">Это может привести к нежелательным результатам или выполнению ненадежного кода.</span><span class="sxs-lookup"><span data-stu-id="2d433-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="2d433-114">`Import-PowerShellDataFile` импортирует данные без вызова кода.</span><span class="sxs-lookup"><span data-stu-id="2d433-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="2d433-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d433-115">EXAMPLES</span></span>

### <span data-ttu-id="2d433-116">Пример 1. Извлечение значений из PSD1</span><span class="sxs-lookup"><span data-stu-id="2d433-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="2d433-117">В этом примере извлекаются пары "ключ-значение", хранящиеся в таблице хэширования, хранящейся в `Configuration.psd1` файле.</span><span class="sxs-lookup"><span data-stu-id="2d433-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="2d433-118">`Get-Content` используется для отображения содержимого `Configuration.psd1` файла.</span><span class="sxs-lookup"><span data-stu-id="2d433-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## <span data-ttu-id="2d433-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d433-119">PARAMETERS</span></span>

### <span data-ttu-id="2d433-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2d433-120">-LiteralPath</span></span>

<span data-ttu-id="2d433-121">Путь к импортируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="2d433-121">The path to the file being imported.</span></span> <span data-ttu-id="2d433-122">Все символы в пути рассматриваются как литеральные значения.</span><span class="sxs-lookup"><span data-stu-id="2d433-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="2d433-123">Подстановочные знаки не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="2d433-123">Wildcard characters are not processed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d433-124">-Path</span><span class="sxs-lookup"><span data-stu-id="2d433-124">-Path</span></span>

<span data-ttu-id="2d433-125">Путь к импортируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="2d433-125">The path to the file being imported.</span></span> <span data-ttu-id="2d433-126">Подстановочные знаки допускаются, но импортируются только первый соответствующий файл.</span><span class="sxs-lookup"><span data-stu-id="2d433-126">Wildcards are allowed but only the first matching file is imported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2d433-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2d433-127">CommonParameters</span></span>

<span data-ttu-id="2d433-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d433-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d433-129">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2d433-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2d433-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2d433-130">INPUTS</span></span>

## <span data-ttu-id="2d433-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2d433-131">OUTPUTS</span></span>

### <span data-ttu-id="2d433-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="2d433-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="2d433-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2d433-133">NOTES</span></span>

## <span data-ttu-id="2d433-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2d433-134">RELATED LINKS</span></span>

[<span data-ttu-id="2d433-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="2d433-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="2d433-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="2d433-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)
