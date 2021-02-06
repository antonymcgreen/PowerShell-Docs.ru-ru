---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: 646f3e0990ce451300a28ca0de58576c70c55a9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602854"
---
# <span data-ttu-id="8774b-102">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="8774b-102">Import-BinaryMiLog</span></span>

## <span data-ttu-id="8774b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8774b-103">SYNOPSIS</span></span>
<span data-ttu-id="8774b-104">Используется для повторного создания сохраненных объектов на основе содержимого файла экспорта.</span><span class="sxs-lookup"><span data-stu-id="8774b-104">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="8774b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8774b-105">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="8774b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8774b-106">DESCRIPTION</span></span>

<span data-ttu-id="8774b-107">Используйте этот командлет для повторного создания сохраненных объектов на основе содержимого файла экспорта, созданного `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="8774b-107">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="8774b-108">Этот командлет аналогичен `Import-Clixml` , за исключением того, что `Export-BinaryMILog` сохраняет полученный объект в двоичном кодированном файле.</span><span class="sxs-lookup"><span data-stu-id="8774b-108">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="8774b-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="8774b-109">EXAMPLES</span></span>

### <span data-ttu-id="8774b-110">Пример 1. восстановление объектов, экспортированных в файл</span><span class="sxs-lookup"><span data-stu-id="8774b-110">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="8774b-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8774b-111">PARAMETERS</span></span>

### <span data-ttu-id="8774b-112">-Path</span><span class="sxs-lookup"><span data-stu-id="8774b-112">-Path</span></span>

<span data-ttu-id="8774b-113">Задает путь к файлу, в котором сохраняется двоичное представление объекта.</span><span class="sxs-lookup"><span data-stu-id="8774b-113">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="8774b-114">Параметр **path** поддерживает подстановочные знаки и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="8774b-114">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="8774b-115">Этот командлет выдает ошибку, если путь разрешается в более чем один файл.</span><span class="sxs-lookup"><span data-stu-id="8774b-115">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="8774b-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8774b-116">CommonParameters</span></span>
<span data-ttu-id="8774b-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8774b-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8774b-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8774b-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8774b-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8774b-119">INPUTS</span></span>

### <span data-ttu-id="8774b-120">None</span><span class="sxs-lookup"><span data-stu-id="8774b-120">None</span></span>

## <span data-ttu-id="8774b-121">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8774b-121">OUTPUTS</span></span>

### <span data-ttu-id="8774b-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="8774b-122">System.Object</span></span>

## <span data-ttu-id="8774b-123">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8774b-123">NOTES</span></span>

## <span data-ttu-id="8774b-124">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8774b-124">RELATED LINKS</span></span>
