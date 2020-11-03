---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233186"
---
# <span data-ttu-id="5c16e-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="5c16e-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="5c16e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5c16e-104">SYNOPSIS</span></span>
<span data-ttu-id="5c16e-105">Используется для повторного создания сохраненных объектов на основе содержимого файла экспорта.</span><span class="sxs-lookup"><span data-stu-id="5c16e-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="5c16e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c16e-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="5c16e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c16e-107">DESCRIPTION</span></span>

<span data-ttu-id="5c16e-108">Используйте этот командлет для повторного создания сохраненных объектов на основе содержимого файла экспорта, созданного `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="5c16e-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="5c16e-109">Этот командлет аналогичен `Import-Clixml` , за исключением того, что `Export-BinaryMILog` сохраняет полученный объект в двоичном кодированном файле.</span><span class="sxs-lookup"><span data-stu-id="5c16e-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="5c16e-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="5c16e-110">EXAMPLES</span></span>

### <span data-ttu-id="5c16e-111">Пример 1. восстановление объектов, экспортированных в файл</span><span class="sxs-lookup"><span data-stu-id="5c16e-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="5c16e-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c16e-112">PARAMETERS</span></span>

### <span data-ttu-id="5c16e-113">-Path</span><span class="sxs-lookup"><span data-stu-id="5c16e-113">-Path</span></span>

<span data-ttu-id="5c16e-114">Задает путь к файлу, в котором сохраняется двоичное представление объекта.</span><span class="sxs-lookup"><span data-stu-id="5c16e-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="5c16e-115">Параметр **path** поддерживает подстановочные знаки и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="5c16e-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="5c16e-116">Этот командлет выдает ошибку, если путь разрешается в более чем один файл.</span><span class="sxs-lookup"><span data-stu-id="5c16e-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="5c16e-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5c16e-117">CommonParameters</span></span>
<span data-ttu-id="5c16e-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c16e-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c16e-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c16e-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c16e-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5c16e-120">INPUTS</span></span>

### <span data-ttu-id="5c16e-121">Нет</span><span class="sxs-lookup"><span data-stu-id="5c16e-121">None</span></span>

## <span data-ttu-id="5c16e-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5c16e-122">OUTPUTS</span></span>

### <span data-ttu-id="5c16e-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="5c16e-123">System.Object</span></span>

## <span data-ttu-id="5c16e-124">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5c16e-124">NOTES</span></span>

## <span data-ttu-id="5c16e-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5c16e-125">RELATED LINKS</span></span>
