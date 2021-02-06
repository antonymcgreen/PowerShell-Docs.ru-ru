---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 0a990b1c0c46cda06c5239a4c8fde55b29296376
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "99602090"
---
# <span data-ttu-id="47a2f-102">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="47a2f-102">Test-FileCatalog</span></span>

## <span data-ttu-id="47a2f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="47a2f-103">SYNOPSIS</span></span>
<span data-ttu-id="47a2f-104">`Test-FileCatalog` проверяет, совпадают ли хэши, содержащиеся в файле каталога (. cat), с хэшами реальных файлов, чтобы проверить их подлинность.</span><span class="sxs-lookup"><span data-stu-id="47a2f-104">`Test-FileCatalog` validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

<span data-ttu-id="47a2f-105">Этот командлет поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="47a2f-105">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="47a2f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47a2f-106">SYNTAX</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="47a2f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47a2f-107">DESCRIPTION</span></span>

<span data-ttu-id="47a2f-108">`Test-FileCatalog` проверяет подлинность файлов, сравнивая хэши файлов каталога (. cat) с хэшами фактических файлов на диске.</span><span class="sxs-lookup"><span data-stu-id="47a2f-108">`Test-FileCatalog` validates the authenticity of files by comparing the file hashes of a catalog file (.cat) with the hashes of actual files on disk.</span></span> <span data-ttu-id="47a2f-109">Если обнаруживает несоответствия, возвращается состояние ValidationFailed.</span><span class="sxs-lookup"><span data-stu-id="47a2f-109">If it detects any mismatches, it returns the status as ValidationFailed.</span></span> <span data-ttu-id="47a2f-110">Все эти данные можно получить с помощью параметра -Detailed.</span><span class="sxs-lookup"><span data-stu-id="47a2f-110">Users can retrieve all this information by using the -Detailed parameter.</span></span> <span data-ttu-id="47a2f-111">Он также отображает состояние подписывания каталога в свойстве Signature, которое эквивалентно вызову `Get-AuthenticodeSignature` командлета для файла каталога.</span><span class="sxs-lookup"><span data-stu-id="47a2f-111">It also displays signing status of catalog in Signature property which is equivalent to calling `Get-AuthenticodeSignature` cmdlet on the catalog file.</span></span> <span data-ttu-id="47a2f-112">Также можно исключить любые файлы из проверки, указав их в параметре -FilesToSkip.</span><span class="sxs-lookup"><span data-stu-id="47a2f-112">Users can also skip any file during validation by using the -FilesToSkip parameter.</span></span>

<span data-ttu-id="47a2f-113">Этот командлет поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="47a2f-113">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="47a2f-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="47a2f-114">EXAMPLES</span></span>

### <span data-ttu-id="47a2f-115">Пример 1. Создание и Проверка каталога файлов</span><span class="sxs-lookup"><span data-stu-id="47a2f-115">Example 1: Create and validate a file catalog</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### <span data-ttu-id="47a2f-116">Пример 2. Проверка каталога файлов с подробным выходом</span><span class="sxs-lookup"><span data-stu-id="47a2f-116">Example 2: Validate a file catalog with detailed output</span></span>

```powershell
Test-FileCatalog -Detailed -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
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

## <span data-ttu-id="47a2f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47a2f-117">PARAMETERS</span></span>

### <span data-ttu-id="47a2f-118">-Каталогфилепас</span><span class="sxs-lookup"><span data-stu-id="47a2f-118">-CatalogFilePath</span></span>

<span data-ttu-id="47a2f-119">Путь к файлу каталога (. cat), который содержит хэши, используемые для проверки.</span><span class="sxs-lookup"><span data-stu-id="47a2f-119">A path to a catalog file (.cat) that contains the hashes to be used for validation.</span></span>

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

### <span data-ttu-id="47a2f-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="47a2f-120">-Confirm</span></span>

<span data-ttu-id="47a2f-121">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="47a2f-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="47a2f-122">-Detailed</span><span class="sxs-lookup"><span data-stu-id="47a2f-122">-Detailed</span></span>

<span data-ttu-id="47a2f-123">Возвращает дополнительные сведения о более подробном `CatalogInformation` объекте, содержащем проверенные файлы, ожидаемые или фактические хэши, а также подпись Authenticode файла каталога, если он подписан.</span><span class="sxs-lookup"><span data-stu-id="47a2f-123">Returns more information a more detailed `CatalogInformation` object that contains the files tested, their expected/actual hashes, and an Authenticode signature of the catalog file if it's signed.</span></span>

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

### <span data-ttu-id="47a2f-124">-FilesToSkip</span><span class="sxs-lookup"><span data-stu-id="47a2f-124">-FilesToSkip</span></span>

<span data-ttu-id="47a2f-125">Массив путей, которые не должны проверяться в ходе проверки.</span><span class="sxs-lookup"><span data-stu-id="47a2f-125">An array of paths that should not be tested as part of the validation.</span></span>

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

### <span data-ttu-id="47a2f-126">-Path</span><span class="sxs-lookup"><span data-stu-id="47a2f-126">-Path</span></span>

<span data-ttu-id="47a2f-127">Папка или массив файлов, которые должны быть проверены по отношению к файлу каталога.</span><span class="sxs-lookup"><span data-stu-id="47a2f-127">A folder or array of files that should be validated against the catalog file.</span></span>

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

### <span data-ttu-id="47a2f-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="47a2f-128">-WhatIf</span></span>

<span data-ttu-id="47a2f-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="47a2f-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="47a2f-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="47a2f-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="47a2f-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="47a2f-131">CommonParameters</span></span>

<span data-ttu-id="47a2f-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47a2f-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47a2f-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47a2f-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47a2f-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="47a2f-134">INPUTS</span></span>

### <span data-ttu-id="47a2f-135">System. IO. DirectoryInfo [], System. String []</span><span class="sxs-lookup"><span data-stu-id="47a2f-135">System.IO.DirectoryInfo[], System.String[]</span></span>

<span data-ttu-id="47a2f-136">Конвейер принимает массив строк или `DirectoryInfo` объектов, представляющих пути к файлам, которые необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="47a2f-136">The pipeline accepts an array of strings or `DirectoryInfo` objects that represent paths to the files that need to be validated.</span></span>

## <span data-ttu-id="47a2f-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="47a2f-137">OUTPUTS</span></span>

### <span data-ttu-id="47a2f-138">System. Management. Automation. Каталогвалидатионстатус</span><span class="sxs-lookup"><span data-stu-id="47a2f-138">System.Management.Automation.CatalogValidationStatus</span></span>

<span data-ttu-id="47a2f-139">Возвращаемый по умолчанию тип, содержащий значение `Valid` либо `ValidationFailed` .</span><span class="sxs-lookup"><span data-stu-id="47a2f-139">The default return type containing a value of either `Valid` or `ValidationFailed`.</span></span>

### <span data-ttu-id="47a2f-140">System. Management. Automation. Каталогинформатион</span><span class="sxs-lookup"><span data-stu-id="47a2f-140">System.Management.Automation.CatalogInformation</span></span>

<span data-ttu-id="47a2f-141">Более подробный объект, возвращаемый при использовании, `-Detailed` который может использоваться для анализа конкретных файлов, которые могут или не прошли проверку, какие хэши ожидались и не были найдены, а также алгоритм, используемый в каталоге.</span><span class="sxs-lookup"><span data-stu-id="47a2f-141">A more detailed object returned when using `-Detailed` which can be used to analyze specific files that may or may not have passed validation, which hashes were expected vs. found, and the algorithm used in the catalog.</span></span>

## <span data-ttu-id="47a2f-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="47a2f-142">NOTES</span></span>

<span data-ttu-id="47a2f-143">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="47a2f-143">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="47a2f-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="47a2f-144">RELATED LINKS</span></span>

[<span data-ttu-id="47a2f-145">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="47a2f-145">New-FileCatalog</span></span>](New-FileCatalog.md)

[<span data-ttu-id="47a2f-146">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="47a2f-146">PowerShellGet</span></span>](/powershell/module/PowerShellGet)
