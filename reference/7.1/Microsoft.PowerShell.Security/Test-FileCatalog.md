---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 4ea34f547e296567fc0ad728d9279392615836d3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346400"
---
# <span data-ttu-id="6c05f-103">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="6c05f-103">Test-FileCatalog</span></span>

## <span data-ttu-id="6c05f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6c05f-104">SYNOPSIS</span></span>
<span data-ttu-id="6c05f-105">`Test-FileCatalog` проверяет, совпадают ли хэши, содержащиеся в файле каталога (. cat), с хэшами реальных файлов, чтобы проверить их подлинность.</span><span class="sxs-lookup"><span data-stu-id="6c05f-105">`Test-FileCatalog` validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

<span data-ttu-id="6c05f-106">Этот командлет поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="6c05f-106">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="6c05f-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6c05f-107">SYNTAX</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6c05f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6c05f-108">DESCRIPTION</span></span>

<span data-ttu-id="6c05f-109">`Test-FileCatalog` проверяет подлинность файлов, сравнивая хэши файлов каталога (. cat) с хэшами фактических файлов на диске.</span><span class="sxs-lookup"><span data-stu-id="6c05f-109">`Test-FileCatalog` validates the authenticity of files by comparing the file hashes of a catalog file (.cat) with the hashes of actual files on disk.</span></span> <span data-ttu-id="6c05f-110">Если обнаруживает несоответствия, возвращается состояние ValidationFailed.</span><span class="sxs-lookup"><span data-stu-id="6c05f-110">If it detects any mismatches, it returns the status as ValidationFailed.</span></span> <span data-ttu-id="6c05f-111">Все эти данные можно получить с помощью параметра -Detailed.</span><span class="sxs-lookup"><span data-stu-id="6c05f-111">Users can retrieve all this information by using the -Detailed parameter.</span></span> <span data-ttu-id="6c05f-112">Он также отображает состояние подписывания каталога в свойстве Signature, которое эквивалентно вызову `Get-AuthenticodeSignature` командлета для файла каталога.</span><span class="sxs-lookup"><span data-stu-id="6c05f-112">It also displays signing status of catalog in Signature property which is equivalent to calling `Get-AuthenticodeSignature` cmdlet on the catalog file.</span></span> <span data-ttu-id="6c05f-113">Также можно исключить любые файлы из проверки, указав их в параметре -FilesToSkip.</span><span class="sxs-lookup"><span data-stu-id="6c05f-113">Users can also skip any file during validation by using the -FilesToSkip parameter.</span></span>

<span data-ttu-id="6c05f-114">Этот командлет поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="6c05f-114">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="6c05f-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="6c05f-115">EXAMPLES</span></span>

### <span data-ttu-id="6c05f-116">Пример 1. Создание и Проверка каталога файлов</span><span class="sxs-lookup"><span data-stu-id="6c05f-116">Example 1: Create and validate a file catalog</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### <span data-ttu-id="6c05f-117">Пример 2. Проверка каталога файлов с подробным выходом</span><span class="sxs-lookup"><span data-stu-id="6c05f-117">Example 2: Validate a file catalog with detailed output</span></span>

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## <span data-ttu-id="6c05f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6c05f-118">PARAMETERS</span></span>

### <span data-ttu-id="6c05f-119">-Каталогфилепас</span><span class="sxs-lookup"><span data-stu-id="6c05f-119">-CatalogFilePath</span></span>

<span data-ttu-id="6c05f-120">Путь к файлу каталога (. cat), который содержит хэши, используемые для проверки.</span><span class="sxs-lookup"><span data-stu-id="6c05f-120">A path to a catalog file (.cat) that contains the hashes to be used for validation.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6c05f-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6c05f-121">-Confirm</span></span>

<span data-ttu-id="6c05f-122">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6c05f-122">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c05f-123">-Detailed</span><span class="sxs-lookup"><span data-stu-id="6c05f-123">-Detailed</span></span>

<span data-ttu-id="6c05f-124">Возвращает дополнительные сведения о более подробном `CatalogInformation` объекте, содержащем проверенные файлы, ожидаемые или фактические хэши, а также подпись Authenticode файла каталога, если он подписан.</span><span class="sxs-lookup"><span data-stu-id="6c05f-124">Returns more information a more detailed `CatalogInformation` object that contains the files tested, their expected/actual hashes, and an Authenticode signature of the catalog file if it's signed.</span></span>

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

### <span data-ttu-id="6c05f-125">-FilesToSkip</span><span class="sxs-lookup"><span data-stu-id="6c05f-125">-FilesToSkip</span></span>

<span data-ttu-id="6c05f-126">Массив путей, которые не должны проверяться в ходе проверки.</span><span class="sxs-lookup"><span data-stu-id="6c05f-126">An array of paths that should not be tested as part of the validation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c05f-127">-Path</span><span class="sxs-lookup"><span data-stu-id="6c05f-127">-Path</span></span>

<span data-ttu-id="6c05f-128">Папка или массив файлов, которые должны быть проверены по отношению к файлу каталога.</span><span class="sxs-lookup"><span data-stu-id="6c05f-128">A folder or array of files that should be validated against the catalog file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6c05f-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6c05f-129">-WhatIf</span></span>

<span data-ttu-id="6c05f-130">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6c05f-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6c05f-131">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6c05f-131">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c05f-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6c05f-132">CommonParameters</span></span>

<span data-ttu-id="6c05f-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6c05f-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6c05f-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6c05f-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6c05f-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6c05f-135">INPUTS</span></span>

### <span data-ttu-id="6c05f-136">System. IO. DirectoryInfo [], System. String []</span><span class="sxs-lookup"><span data-stu-id="6c05f-136">System.IO.DirectoryInfo[], System.String[]</span></span>

<span data-ttu-id="6c05f-137">Конвейер принимает массив строк или `DirectoryInfo` объектов, представляющих пути к файлам, которые необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="6c05f-137">The pipeline accepts an array of strings or `DirectoryInfo` objects that represent paths to the files that need to be validated.</span></span>

## <span data-ttu-id="6c05f-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6c05f-138">OUTPUTS</span></span>

### <span data-ttu-id="6c05f-139">System. Management. Automation. Каталогвалидатионстатус</span><span class="sxs-lookup"><span data-stu-id="6c05f-139">System.Management.Automation.CatalogValidationStatus</span></span>

<span data-ttu-id="6c05f-140">Возвращаемый по умолчанию тип, содержащий значение `Valid` либо `ValidationFailed` .</span><span class="sxs-lookup"><span data-stu-id="6c05f-140">The default return type containing a value of either `Valid` or `ValidationFailed`.</span></span>

### <span data-ttu-id="6c05f-141">System. Management. Automation. Каталогинформатион</span><span class="sxs-lookup"><span data-stu-id="6c05f-141">System.Management.Automation.CatalogInformation</span></span>

<span data-ttu-id="6c05f-142">Более подробный объект, возвращаемый при использовании, `-Detailed` который может использоваться для анализа конкретных файлов, которые могут или не прошли проверку, какие хэши ожидались и не были найдены, а также алгоритм, используемый в каталоге.</span><span class="sxs-lookup"><span data-stu-id="6c05f-142">A more detailed object returned when using `-Detailed` which can be used to analyze specific files that may or may not have passed validation, which hashes were expected vs. found, and the algorithm used in the catalog.</span></span>

## <span data-ttu-id="6c05f-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6c05f-143">NOTES</span></span>

<span data-ttu-id="6c05f-144">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="6c05f-144">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="6c05f-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6c05f-145">RELATED LINKS</span></span>

[<span data-ttu-id="6c05f-146">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="6c05f-146">New-FileCatalog</span></span>](New-FileCatalog.md)

[<span data-ttu-id="6c05f-147">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="6c05f-147">PowerShellGet</span></span>](/powershell/module/PowerShellGet)
