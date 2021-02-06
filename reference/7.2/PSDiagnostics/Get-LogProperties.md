---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: f532dd3ff46f14348437de531e80e94b192b13e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602494"
---
# <span data-ttu-id="9dcd3-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="9dcd3-102">Get-LogProperties</span></span>

## <span data-ttu-id="9dcd3-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9dcd3-103">SYNOPSIS</span></span>
<span data-ttu-id="9dcd3-104">Извлекает свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="9dcd3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9dcd3-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="9dcd3-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9dcd3-106">DESCRIPTION</span></span>

<span data-ttu-id="9dcd3-107">Этот командлет возвращает параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="9dcd3-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="9dcd3-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="9dcd3-109">EXAMPLES</span></span>

### <span data-ttu-id="9dcd3-110">Пример 1. получение параметров конфигурации журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dcd3-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="9dcd3-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9dcd3-111">PARAMETERS</span></span>

### <span data-ttu-id="9dcd3-112">-Name</span><span class="sxs-lookup"><span data-stu-id="9dcd3-112">-Name</span></span>

<span data-ttu-id="9dcd3-113">Имя поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-113">The name of the event provider.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9dcd3-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9dcd3-114">CommonParameters</span></span>

<span data-ttu-id="9dcd3-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dcd3-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9dcd3-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9dcd3-117">INPUTS</span></span>

### <span data-ttu-id="9dcd3-118">System.String</span><span class="sxs-lookup"><span data-stu-id="9dcd3-118">System.String</span></span>

## <span data-ttu-id="9dcd3-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9dcd3-119">OUTPUTS</span></span>

### <span data-ttu-id="9dcd3-120">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="9dcd3-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="9dcd3-121">Модуль **PSDiagnostics** добавляет класс **логдетаилс** в `Microsoft.PowerShell.Diagnostics` пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="9dcd3-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9dcd3-122">NOTES</span></span>

## <span data-ttu-id="9dcd3-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9dcd3-123">RELATED LINKS</span></span>

[<span data-ttu-id="9dcd3-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="9dcd3-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="9dcd3-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="9dcd3-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="9dcd3-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="9dcd3-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)

