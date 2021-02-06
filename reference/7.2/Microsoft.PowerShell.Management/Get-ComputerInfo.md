---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: abc820bd6f8f5c8cd8c6301aacee268c82161d7e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605296"
---
# <span data-ttu-id="81aae-102">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="81aae-102">Get-ComputerInfo</span></span>

## <span data-ttu-id="81aae-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="81aae-103">SYNOPSIS</span></span>
<span data-ttu-id="81aae-104">Возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="81aae-104">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="81aae-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="81aae-105">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="81aae-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="81aae-106">DESCRIPTION</span></span>

<span data-ttu-id="81aae-107">`Get-ComputerInfo`Командлет возвращает объединенный объект систем и свойств операционной системы.</span><span class="sxs-lookup"><span data-stu-id="81aae-107">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="81aae-108">Этот командлет появился в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="81aae-108">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="81aae-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="81aae-109">EXAMPLES</span></span>

### <span data-ttu-id="81aae-110">Пример 1. получение свойств всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="81aae-110">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="81aae-111">Эта команда возвращает все свойства системы и операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="81aae-111">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="81aae-112">Пример 2. получение свойств операционной системы для всех компьютеров</span><span class="sxs-lookup"><span data-stu-id="81aae-112">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="81aae-113">Эта команда возвращает все свойства операционной системы с компьютера.</span><span class="sxs-lookup"><span data-stu-id="81aae-113">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="81aae-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="81aae-114">PARAMETERS</span></span>

### <span data-ttu-id="81aae-115">-Property</span><span class="sxs-lookup"><span data-stu-id="81aae-115">-Property</span></span>

<span data-ttu-id="81aae-116">Указывает в виде массива строк свойства компьютера, в которых отображается этот командлет.</span><span class="sxs-lookup"><span data-stu-id="81aae-116">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="81aae-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="81aae-117">CommonParameters</span></span>

<span data-ttu-id="81aae-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="81aae-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="81aae-119">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="81aae-119">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="81aae-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="81aae-120">INPUTS</span></span>

### <span data-ttu-id="81aae-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="81aae-121">System.String[]</span></span>

## <span data-ttu-id="81aae-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="81aae-122">OUTPUTS</span></span>

### <span data-ttu-id="81aae-123">Microsoft. PowerShell. Management. Компутеринфо</span><span class="sxs-lookup"><span data-stu-id="81aae-123">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="81aae-124">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="81aae-124">NOTES</span></span>

<span data-ttu-id="81aae-125">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="81aae-125">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="81aae-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="81aae-126">RELATED LINKS</span></span>
