---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226893"
---
# <span data-ttu-id="1526a-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="1526a-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="1526a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1526a-104">SYNOPSIS</span></span>
<span data-ttu-id="1526a-105">Создает представление объекта или объектов в двоичном кодировке и сохраняет его в файле.</span><span class="sxs-lookup"><span data-stu-id="1526a-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="1526a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1526a-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="1526a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1526a-107">DESCRIPTION</span></span>

<span data-ttu-id="1526a-108">`Export-BinaryMILog`Командлет создает двоичное представление объекта или объектов и сохраняет его в файле.</span><span class="sxs-lookup"><span data-stu-id="1526a-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="1526a-109">Затем можно использовать `Import-BinaryMiLog` командлет для повторного создания сохраненного объекта на основе содержимого этого файла.</span><span class="sxs-lookup"><span data-stu-id="1526a-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="1526a-110">Этот командлет аналогичен `Import-Clixml` , за исключением того, что `Export-BinaryMILog` сохраняет полученный объект в двоичном кодированном файле.</span><span class="sxs-lookup"><span data-stu-id="1526a-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="1526a-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="1526a-111">EXAMPLES</span></span>

### <span data-ttu-id="1526a-112">Пример 1. Создание двоичного представления Циминстанцес</span><span class="sxs-lookup"><span data-stu-id="1526a-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="1526a-113">Эта команда экспортирует **Циминстанцес** в файл журнала ДВОИЧной MI, заданный параметром path.</span><span class="sxs-lookup"><span data-stu-id="1526a-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="1526a-114">См. пример для Import-BinaryMiLog, чтобы узнать, как повторно создать **Циминстанцес** путем импорта этого файла.</span><span class="sxs-lookup"><span data-stu-id="1526a-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="1526a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1526a-115">PARAMETERS</span></span>

### <span data-ttu-id="1526a-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1526a-116">-InputObject</span></span>

<span data-ttu-id="1526a-117">Задает входные данные для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="1526a-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="1526a-118">Можно использовать данный параметр или передавать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="1526a-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1526a-119">-Path</span><span class="sxs-lookup"><span data-stu-id="1526a-119">-Path</span></span>

<span data-ttu-id="1526a-120">Задает путь к файлу, в котором сохраняется двоичное представление объекта.</span><span class="sxs-lookup"><span data-stu-id="1526a-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="1526a-121">Параметр **path** поддерживает подстановочные знаки и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="1526a-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="1526a-122">Этот командлет выдает ошибку, если путь разрешается в более чем один файл.</span><span class="sxs-lookup"><span data-stu-id="1526a-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1526a-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1526a-123">CommonParameters</span></span>

<span data-ttu-id="1526a-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1526a-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1526a-125">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1526a-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1526a-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1526a-126">INPUTS</span></span>

### <span data-ttu-id="1526a-127">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="1526a-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="1526a-128">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1526a-128">OUTPUTS</span></span>

### <span data-ttu-id="1526a-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="1526a-129">System.Object</span></span>

## <span data-ttu-id="1526a-130">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1526a-130">NOTES</span></span>

## <span data-ttu-id="1526a-131">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1526a-131">RELATED LINKS</span></span>

[<span data-ttu-id="1526a-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="1526a-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="1526a-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="1526a-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="1526a-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="1526a-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
