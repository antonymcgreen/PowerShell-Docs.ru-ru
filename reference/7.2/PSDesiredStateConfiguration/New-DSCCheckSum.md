---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 8b8d0c545cdb36b6184a0670a52a5a30aa33a465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605049"
---
# <span data-ttu-id="b8f44-102">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="b8f44-102">New-DscChecksum</span></span>

## <span data-ttu-id="b8f44-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b8f44-103">SYNOPSIS</span></span>
<span data-ttu-id="b8f44-104">Создает файлы контрольных сумм для документов DSC и ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="b8f44-104">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="b8f44-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8f44-105">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b8f44-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8f44-106">DESCRIPTION</span></span>

<span data-ttu-id="b8f44-107">Командлет **New-DSCCheckSum** создает файлы контрольных сумм для документов DSC и сжатых ресурсов DSC PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8f44-107">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="b8f44-108">Этот командлет создает файл контрольной суммы для каждой конфигурации и ресурса, которые будут использоваться в режиме опроса.</span><span class="sxs-lookup"><span data-stu-id="b8f44-108">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="b8f44-109">Служба DSC использует контрольные суммы, чтобы убедиться, что на целевом узле существуют правильная конфигурация и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b8f44-109">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="b8f44-110">Разместите контрольные суммы вместе со связанными документами DSC и сжатыми ресурсами DSC в хранилище служб DSC.</span><span class="sxs-lookup"><span data-stu-id="b8f44-110">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="b8f44-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8f44-111">EXAMPLES</span></span>

### <span data-ttu-id="b8f44-112">Пример 1. Создание файлов контрольной суммы для всех конфигураций по указанному пути</span><span class="sxs-lookup"><span data-stu-id="b8f44-112">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="b8f44-113">Эта команда создает файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="b8f44-113">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="b8f44-114">Все уже существующие файлы контрольных сумм пропускаются.</span><span class="sxs-lookup"><span data-stu-id="b8f44-114">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="b8f44-115">Пример 2. Создание файлов контрольной суммы для всех конфигураций по указанному пути и перезапись существующих файлов контрольной суммы</span><span class="sxs-lookup"><span data-stu-id="b8f44-115">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="b8f44-116">Эта команда создает новые файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="b8f44-116">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="b8f44-117">Указание параметра *Force* приводит к тому, что команда перезаписывает все уже существующие файлы контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="b8f44-117">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="b8f44-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8f44-118">PARAMETERS</span></span>

### <span data-ttu-id="b8f44-119">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b8f44-119">-Confirm</span></span>

<span data-ttu-id="b8f44-120">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b8f44-120">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b8f44-121">-Force</span><span class="sxs-lookup"><span data-stu-id="b8f44-121">-Force</span></span>

<span data-ttu-id="b8f44-122">Указывает, что командлет перезаписывает выбранный выходной файл, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="b8f44-122">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="b8f44-123">-Путь</span><span class="sxs-lookup"><span data-stu-id="b8f44-123">-OutPath</span></span>

<span data-ttu-id="b8f44-124">Указывает путь и имя выходного файла контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="b8f44-124">Specifies the path and file name of the output checksum file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f44-125">-Path</span><span class="sxs-lookup"><span data-stu-id="b8f44-125">-Path</span></span>

<span data-ttu-id="b8f44-126">Задает путь к входному файлу.</span><span class="sxs-lookup"><span data-stu-id="b8f44-126">Specifies the path of the input file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f44-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b8f44-127">-WhatIf</span></span>

<span data-ttu-id="b8f44-128">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b8f44-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b8f44-129">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b8f44-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b8f44-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b8f44-130">CommonParameters</span></span>

<span data-ttu-id="b8f44-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b8f44-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8f44-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b8f44-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8f44-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b8f44-133">INPUTS</span></span>

### <span data-ttu-id="b8f44-134">None</span><span class="sxs-lookup"><span data-stu-id="b8f44-134">None</span></span>

## <span data-ttu-id="b8f44-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8f44-135">OUTPUTS</span></span>

### <span data-ttu-id="b8f44-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="b8f44-136">System.Object</span></span>

## <span data-ttu-id="b8f44-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b8f44-137">NOTES</span></span>

## <span data-ttu-id="b8f44-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b8f44-138">RELATED LINKS</span></span>

[<span data-ttu-id="b8f44-139">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="b8f44-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

