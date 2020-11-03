---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 2a66f906025f7a25609080e0b8da7f01755cd2fa
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225705"
---
# <span data-ttu-id="1f13f-103">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="1f13f-103">New-DscChecksum</span></span>

## <span data-ttu-id="1f13f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1f13f-104">SYNOPSIS</span></span>
<span data-ttu-id="1f13f-105">Создает файлы контрольных сумм для документов DSC и ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="1f13f-105">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="1f13f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f13f-106">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1f13f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f13f-107">DESCRIPTION</span></span>

<span data-ttu-id="1f13f-108">Командлет **New-DSCCheckSum** создает файлы контрольных сумм для документов DSC и сжатых ресурсов DSC PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f13f-108">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="1f13f-109">Этот командлет создает файл контрольной суммы для каждой конфигурации и ресурса, которые будут использоваться в режиме опроса.</span><span class="sxs-lookup"><span data-stu-id="1f13f-109">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="1f13f-110">Служба DSC использует контрольные суммы, чтобы убедиться, что на целевом узле существуют правильная конфигурация и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="1f13f-110">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="1f13f-111">Разместите контрольные суммы вместе со связанными документами DSC и сжатыми ресурсами DSC в хранилище служб DSC.</span><span class="sxs-lookup"><span data-stu-id="1f13f-111">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="1f13f-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="1f13f-112">EXAMPLES</span></span>

### <span data-ttu-id="1f13f-113">Пример 1. Создание файлов контрольной суммы для всех конфигураций по указанному пути</span><span class="sxs-lookup"><span data-stu-id="1f13f-113">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="1f13f-114">Эта команда создает файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="1f13f-114">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="1f13f-115">Все уже существующие файлы контрольных сумм пропускаются.</span><span class="sxs-lookup"><span data-stu-id="1f13f-115">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="1f13f-116">Пример 2. Создание файлов контрольной суммы для всех конфигураций по указанному пути и перезапись существующих файлов контрольной суммы</span><span class="sxs-lookup"><span data-stu-id="1f13f-116">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="1f13f-117">Эта команда создает новые файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="1f13f-117">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="1f13f-118">Указание параметра *Force* приводит к тому, что команда перезаписывает все уже существующие файлы контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="1f13f-118">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="1f13f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f13f-119">PARAMETERS</span></span>

### <span data-ttu-id="1f13f-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1f13f-120">-Confirm</span></span>

<span data-ttu-id="1f13f-121">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1f13f-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1f13f-122">-Force</span><span class="sxs-lookup"><span data-stu-id="1f13f-122">-Force</span></span>

<span data-ttu-id="1f13f-123">Указывает, что командлет перезаписывает выбранный выходной файл, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="1f13f-123">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="1f13f-124">-Путь</span><span class="sxs-lookup"><span data-stu-id="1f13f-124">-OutPath</span></span>

<span data-ttu-id="1f13f-125">Указывает путь и имя выходного файла контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="1f13f-125">Specifies the path and file name of the output checksum file.</span></span>

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

### <span data-ttu-id="1f13f-126">-Path</span><span class="sxs-lookup"><span data-stu-id="1f13f-126">-Path</span></span>

<span data-ttu-id="1f13f-127">Задает путь к входному файлу.</span><span class="sxs-lookup"><span data-stu-id="1f13f-127">Specifies the path of the input file.</span></span>

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

### <span data-ttu-id="1f13f-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1f13f-128">-WhatIf</span></span>

<span data-ttu-id="1f13f-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1f13f-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1f13f-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1f13f-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1f13f-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1f13f-131">CommonParameters</span></span>

<span data-ttu-id="1f13f-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1f13f-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f13f-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1f13f-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f13f-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1f13f-134">INPUTS</span></span>

### <span data-ttu-id="1f13f-135">Нет</span><span class="sxs-lookup"><span data-stu-id="1f13f-135">None</span></span>

## <span data-ttu-id="1f13f-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1f13f-136">OUTPUTS</span></span>

### <span data-ttu-id="1f13f-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="1f13f-137">System.Object</span></span>

## <span data-ttu-id="1f13f-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1f13f-138">NOTES</span></span>

## <span data-ttu-id="1f13f-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1f13f-139">RELATED LINKS</span></span>

[<span data-ttu-id="1f13f-140">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="1f13f-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)
