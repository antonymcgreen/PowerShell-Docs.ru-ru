---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: d7942abff2974064c52a8a9ac086a280959b3a63
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "99602085"
---
# <span data-ttu-id="73ada-102">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="73ada-102">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="73ada-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73ada-103">SYNOPSIS</span></span>
<span data-ttu-id="73ada-104">Импортирует значения из `.PSD1` файла без вызова его содержимого.</span><span class="sxs-lookup"><span data-stu-id="73ada-104">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="73ada-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73ada-105">SYNTAX</span></span>

### <span data-ttu-id="73ada-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="73ada-106">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

### <span data-ttu-id="73ada-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="73ada-107">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

## <span data-ttu-id="73ada-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73ada-108">DESCRIPTION</span></span>

<span data-ttu-id="73ada-109">`Import-PowerShellDataFile`Командлет безопасно импортирует пары "ключ-значение" из таблиц хэширования, определенных в `.PSD1` файле.</span><span class="sxs-lookup"><span data-stu-id="73ada-109">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="73ada-110">Значения можно импортировать с помощью `Invoke-Expression` на содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="73ada-110">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="73ada-111">Однако `Invoke-Expression` выполняет любой код, содержащийся в файле.</span><span class="sxs-lookup"><span data-stu-id="73ada-111">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="73ada-112">Это может привести к нежелательным результатам или выполнению ненадежного кода.</span><span class="sxs-lookup"><span data-stu-id="73ada-112">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="73ada-113">`Import-PowerShellDataFile` импортирует данные без вызова кода.</span><span class="sxs-lookup"><span data-stu-id="73ada-113">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span> <span data-ttu-id="73ada-114">По умолчанию существует ограничение в 500 ключей, но его можно обойти с помощью параметра **скиплимитчекк** .</span><span class="sxs-lookup"><span data-stu-id="73ada-114">By default there is a 500 key limit but can be bypassed with the **SkipLimitCheck** switch.</span></span>

## <span data-ttu-id="73ada-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="73ada-115">EXAMPLES</span></span>

### <span data-ttu-id="73ada-116">Пример 1. Извлечение значений из PSD1</span><span class="sxs-lookup"><span data-stu-id="73ada-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="73ada-117">В этом примере извлекаются пары "ключ-значение", хранящиеся в таблице хэширования, хранящейся в `Configuration.psd1` файле.</span><span class="sxs-lookup"><span data-stu-id="73ada-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="73ada-118">`Get-Content` используется для отображения содержимого `Configuration.psd1` файла.</span><span class="sxs-lookup"><span data-stu-id="73ada-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

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

## <span data-ttu-id="73ada-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73ada-119">PARAMETERS</span></span>

### <span data-ttu-id="73ada-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73ada-120">-LiteralPath</span></span>

<span data-ttu-id="73ada-121">Путь к импортируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="73ada-121">The path to the file being imported.</span></span> <span data-ttu-id="73ada-122">Все символы в пути рассматриваются как литеральные значения.</span><span class="sxs-lookup"><span data-stu-id="73ada-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="73ada-123">Подстановочные знаки не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="73ada-123">Wildcard characters are not processed.</span></span>

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

### <span data-ttu-id="73ada-124">-Path</span><span class="sxs-lookup"><span data-stu-id="73ada-124">-Path</span></span>

<span data-ttu-id="73ada-125">Путь к импортируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="73ada-125">The path to the file being imported.</span></span> <span data-ttu-id="73ada-126">Подстановочные знаки допускаются, но импортируются только первый соответствующий файл.</span><span class="sxs-lookup"><span data-stu-id="73ada-126">Wildcards are allowed but only the first matching file is imported.</span></span>

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

### <span data-ttu-id="73ada-127">-Скиплимитчекк</span><span class="sxs-lookup"><span data-stu-id="73ada-127">-SkipLimitCheck</span></span>

<span data-ttu-id="73ada-128">По умолчанию `Import-PowerShellDataFile` импортирует только 500 ключей из `.psd1` файла.</span><span class="sxs-lookup"><span data-stu-id="73ada-128">By default `Import-PowerShellDataFile` imports only 500 keys from a `.psd1` file.</span></span> <span data-ttu-id="73ada-129">Используйте **скиплимитчекк** для импорта более 500 ключей.</span><span class="sxs-lookup"><span data-stu-id="73ada-129">Use **SkipLimitCheck** to import more than 500 keys.</span></span>

```yaml
Type: Switch
Parameter Sets: All
Aliases:

Required: False
Position: 0
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73ada-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="73ada-130">CommonParameters</span></span>

<span data-ttu-id="73ada-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73ada-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73ada-132">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="73ada-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="73ada-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="73ada-133">INPUTS</span></span>

## <span data-ttu-id="73ada-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="73ada-134">OUTPUTS</span></span>

### <span data-ttu-id="73ada-135">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="73ada-135">System.Collections.Hashtable</span></span>

## <span data-ttu-id="73ada-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="73ada-136">NOTES</span></span>

## <span data-ttu-id="73ada-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="73ada-137">RELATED LINKS</span></span>

[<span data-ttu-id="73ada-138">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="73ada-138">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="73ada-139">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="73ada-139">Import-LocalizedData</span></span>](Import-LocalizedData.md)
