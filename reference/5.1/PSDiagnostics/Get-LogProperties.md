---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 0f675c2b0bf2b7e5ebfe3a1677f5bc194e8fe844
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227430"
---
# <span data-ttu-id="858cb-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="858cb-102">Get-LogProperties</span></span>

## <span data-ttu-id="858cb-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="858cb-103">SYNOPSIS</span></span>
<span data-ttu-id="858cb-104">Извлекает свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="858cb-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="858cb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="858cb-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <string> [<CommonParameters>]
```

## <span data-ttu-id="858cb-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="858cb-106">DESCRIPTION</span></span>

<span data-ttu-id="858cb-107">Этот командлет возвращает параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="858cb-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="858cb-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="858cb-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="858cb-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="858cb-109">EXAMPLES</span></span>

### <span data-ttu-id="858cb-110">Пример 1. получение параметров конфигурации журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="858cb-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="858cb-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="858cb-111">PARAMETERS</span></span>

### <span data-ttu-id="858cb-112">-Name</span><span class="sxs-lookup"><span data-stu-id="858cb-112">-Name</span></span>

<span data-ttu-id="858cb-113">Имя поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="858cb-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="858cb-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="858cb-114">CommonParameters</span></span>

<span data-ttu-id="858cb-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="858cb-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="858cb-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="858cb-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="858cb-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="858cb-117">INPUTS</span></span>

### <span data-ttu-id="858cb-118">System.Object</span><span class="sxs-lookup"><span data-stu-id="858cb-118">System.Object</span></span>

## <span data-ttu-id="858cb-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="858cb-119">OUTPUTS</span></span>

### <span data-ttu-id="858cb-120">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="858cb-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="858cb-121">Модуль **PSDiagnostics** добавляет класс **логдетаилс** в `Microsoft.PowerShell.Diagnostics` пространство имен.</span><span class="sxs-lookup"><span data-stu-id="858cb-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="858cb-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="858cb-122">NOTES</span></span>

## <span data-ttu-id="858cb-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="858cb-123">RELATED LINKS</span></span>

[<span data-ttu-id="858cb-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="858cb-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="858cb-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="858cb-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="858cb-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="858cb-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
