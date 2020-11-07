---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: 4a39714995c31a4d44177312dd8e5dad9ab43712
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342337"
---
# <span data-ttu-id="dcf39-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="dcf39-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="dcf39-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dcf39-104">SYNOPSIS</span></span>
<span data-ttu-id="dcf39-105">Возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="dcf39-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="dcf39-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcf39-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="dcf39-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dcf39-107">DESCRIPTION</span></span>

<span data-ttu-id="dcf39-108">`Get-ComputerInfo`Командлет возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="dcf39-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="dcf39-109">Этот командлет появился в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="dcf39-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="dcf39-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="dcf39-110">EXAMPLES</span></span>

### <span data-ttu-id="dcf39-111">Пример 1. получение свойств всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="dcf39-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="dcf39-112">Эта команда возвращает все свойства системы и операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="dcf39-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="dcf39-113">Пример 2. получение свойств операционной системы для всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="dcf39-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="dcf39-114">Эта команда возвращает все свойства операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="dcf39-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="dcf39-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcf39-115">PARAMETERS</span></span>

### <span data-ttu-id="dcf39-116">-Property</span><span class="sxs-lookup"><span data-stu-id="dcf39-116">-Property</span></span>

<span data-ttu-id="dcf39-117">Указывает в виде массива строк свойства компьютера, в которых отображается этот командлет.</span><span class="sxs-lookup"><span data-stu-id="dcf39-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="dcf39-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dcf39-118">CommonParameters</span></span>

<span data-ttu-id="dcf39-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dcf39-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dcf39-120">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="dcf39-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dcf39-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dcf39-121">INPUTS</span></span>

### <span data-ttu-id="dcf39-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="dcf39-122">System.String[]</span></span>

## <span data-ttu-id="dcf39-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dcf39-123">OUTPUTS</span></span>

### <span data-ttu-id="dcf39-124">Microsoft. PowerShell. Management. Компутеринфо</span><span class="sxs-lookup"><span data-stu-id="dcf39-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="dcf39-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dcf39-125">NOTES</span></span>

<span data-ttu-id="dcf39-126">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="dcf39-126">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="dcf39-127">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dcf39-127">RELATED LINKS</span></span>
