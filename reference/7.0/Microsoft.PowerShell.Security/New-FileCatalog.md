---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 007b486b7b65d9b6481839643fe839eda49a1113
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346961"
---
# <span data-ttu-id="1294a-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="1294a-103">New-FileCatalog</span></span>

## <span data-ttu-id="1294a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1294a-104">SYNOPSIS</span></span>
<span data-ttu-id="1294a-105">`New-FileCatalog` создает файл каталога хэшей файлов, который можно использовать для проверки подлинности файла.</span><span class="sxs-lookup"><span data-stu-id="1294a-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="1294a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1294a-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="1294a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1294a-107">DESCRIPTION</span></span>

<span data-ttu-id="1294a-108">`New-FileCatalog` создает [файл каталога Windows](/windows-hardware/drivers/install/catalog-files) для набора папок и файлов.</span><span class="sxs-lookup"><span data-stu-id="1294a-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span> <span data-ttu-id="1294a-109">Этот файл каталога содержит хэши для всех файлов в указанных путях.</span><span class="sxs-lookup"><span data-stu-id="1294a-109">This catalog file contains hashes for all files in the provided paths.</span></span> <span data-ttu-id="1294a-110">Затем пользователи могут распространить каталог вместе с файлами, чтобы пользователи могли проверить, были ли сделаны изменения в папках с момента создания каталога.</span><span class="sxs-lookup"><span data-stu-id="1294a-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="1294a-111">Поддерживаются каталоги версий 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="1294a-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="1294a-112">В версии 1 для создания хэшей файлов используется алгоритм хэширования SHA1 (не рекомендуется), а в версии 2 используется SHA256.</span><span class="sxs-lookup"><span data-stu-id="1294a-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span> <span data-ttu-id="1294a-113">Каталог версии 2 не поддерживается в Windows Server 2008 R2 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1294a-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="1294a-114">На платформах Windows 8, Windows Server 2012 и более поздней версии рекомендуется использовать каталог версии 2.</span><span class="sxs-lookup"><span data-stu-id="1294a-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="1294a-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="1294a-115">EXAMPLES</span></span>

### <span data-ttu-id="1294a-116">Пример 1. Создание каталога файлов для `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="1294a-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="1294a-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1294a-117">PARAMETERS</span></span>

### <span data-ttu-id="1294a-118">-Каталогфилепас</span><span class="sxs-lookup"><span data-stu-id="1294a-118">-CatalogFilePath</span></span>

<span data-ttu-id="1294a-119">Путь к файлу или папке, в которую следует поместить файл каталога (. cat).</span><span class="sxs-lookup"><span data-stu-id="1294a-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span> <span data-ttu-id="1294a-120">Если указан путь к папке, будет использоваться имя файла по умолчанию `catalog.cat` .</span><span class="sxs-lookup"><span data-stu-id="1294a-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="1294a-121">-Каталогверсион</span><span class="sxs-lookup"><span data-stu-id="1294a-121">-CatalogVersion</span></span>

<span data-ttu-id="1294a-122">Принимает `1.0` или `2.0` в качестве возможных значений для указания версии каталога.</span><span class="sxs-lookup"><span data-stu-id="1294a-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span> <span data-ttu-id="1294a-123">`1.0` следует избегать по возможности, если это возможно, так как в нем используется небезопасный алгоритм хэширования SHA-1, а `2.0` используется алгоритм Secure SHA-256, но `1.0` это единственный поддерживаемый алгоритм в Windows 7 и Server 2008R2.</span><span class="sxs-lookup"><span data-stu-id="1294a-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1294a-124">-Path</span><span class="sxs-lookup"><span data-stu-id="1294a-124">-Path</span></span>

<span data-ttu-id="1294a-125">Принимает путь или массив путей к файлам или папкам, которые должны быть добавлены в файл каталога.</span><span class="sxs-lookup"><span data-stu-id="1294a-125">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span> <span data-ttu-id="1294a-126">Если указана папка, будут также включаться все файлы в этой папке.</span><span class="sxs-lookup"><span data-stu-id="1294a-126">If a folder is specified, all the files in the folder will be included as well.</span></span>

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

### <span data-ttu-id="1294a-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1294a-127">-Confirm</span></span>

<span data-ttu-id="1294a-128">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1294a-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1294a-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1294a-129">-WhatIf</span></span>

<span data-ttu-id="1294a-130">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1294a-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1294a-131">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1294a-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1294a-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1294a-132">CommonParameters</span></span>

<span data-ttu-id="1294a-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1294a-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1294a-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1294a-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1294a-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1294a-135">INPUTS</span></span>

### <span data-ttu-id="1294a-136">System.String</span><span class="sxs-lookup"><span data-stu-id="1294a-136">System.String</span></span>

<span data-ttu-id="1294a-137">Конвейер принимает строку, которая используется в качестве имени файла каталога.</span><span class="sxs-lookup"><span data-stu-id="1294a-137">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="1294a-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1294a-138">OUTPUTS</span></span>

### <span data-ttu-id="1294a-139">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="1294a-139">System.IO.FileInfo</span></span>

## <span data-ttu-id="1294a-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1294a-140">NOTES</span></span>

<span data-ttu-id="1294a-141">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="1294a-141">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="1294a-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1294a-142">RELATED LINKS</span></span>

[<span data-ttu-id="1294a-143">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="1294a-143">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="1294a-144">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1294a-144">PowerShellGet</span></span>](/powerShell/module/powershellget)
