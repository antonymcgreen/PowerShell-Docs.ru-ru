---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: e9b9e63815e1eb312a30eca11c691107ea3d070f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228406"
---
# <span data-ttu-id="ce84b-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="ce84b-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="ce84b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ce84b-104">SYNOPSIS</span></span>
<span data-ttu-id="ce84b-105">Возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ce84b-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="ce84b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce84b-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ce84b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce84b-107">DESCRIPTION</span></span>

<span data-ttu-id="ce84b-108">`Get-ComputerInfo`Командлет возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ce84b-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="ce84b-109">Этот командлет появился в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="ce84b-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="ce84b-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ce84b-110">EXAMPLES</span></span>

### <span data-ttu-id="ce84b-111">Пример 1. получение свойств всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="ce84b-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="ce84b-112">Эта команда возвращает все свойства системы и операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce84b-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="ce84b-113">Пример 2. получение свойств операционной системы для всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="ce84b-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="ce84b-114">Эта команда возвращает все свойства операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce84b-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="ce84b-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce84b-115">PARAMETERS</span></span>

### <span data-ttu-id="ce84b-116">-Property</span><span class="sxs-lookup"><span data-stu-id="ce84b-116">-Property</span></span>

<span data-ttu-id="ce84b-117">Указывает в виде массива строк свойства компьютера, в которых отображается этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ce84b-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ce84b-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ce84b-118">CommonParameters</span></span>

<span data-ttu-id="ce84b-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce84b-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce84b-120">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ce84b-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ce84b-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ce84b-121">INPUTS</span></span>

### <span data-ttu-id="ce84b-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="ce84b-122">System.String[]</span></span>

## <span data-ttu-id="ce84b-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ce84b-123">OUTPUTS</span></span>

### <span data-ttu-id="ce84b-124">Microsoft. PowerShell. Management. Компутеринфо</span><span class="sxs-lookup"><span data-stu-id="ce84b-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="ce84b-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ce84b-125">NOTES</span></span>

## <span data-ttu-id="ce84b-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ce84b-126">RELATED LINKS</span></span>
