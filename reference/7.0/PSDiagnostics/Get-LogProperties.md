---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 08638749b7a5bb57bee804fccf9de17f50fd6736
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226017"
---
# <span data-ttu-id="fcd64-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fcd64-102">Get-LogProperties</span></span>

## <span data-ttu-id="fcd64-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fcd64-103">SYNOPSIS</span></span>
<span data-ttu-id="fcd64-104">Извлекает свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="fcd64-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="fcd64-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fcd64-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="fcd64-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fcd64-106">DESCRIPTION</span></span>

<span data-ttu-id="fcd64-107">Этот командлет возвращает параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="fcd64-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="fcd64-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="fcd64-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="fcd64-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="fcd64-109">EXAMPLES</span></span>

### <span data-ttu-id="fcd64-110">Пример 1. получение параметров конфигурации журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcd64-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="fcd64-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fcd64-111">PARAMETERS</span></span>

### <span data-ttu-id="fcd64-112">-Name</span><span class="sxs-lookup"><span data-stu-id="fcd64-112">-Name</span></span>

<span data-ttu-id="fcd64-113">Имя поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="fcd64-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="fcd64-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fcd64-114">CommonParameters</span></span>

<span data-ttu-id="fcd64-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fcd64-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fcd64-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fcd64-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fcd64-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fcd64-117">INPUTS</span></span>

### <span data-ttu-id="fcd64-118">System.String</span><span class="sxs-lookup"><span data-stu-id="fcd64-118">System.String</span></span>

## <span data-ttu-id="fcd64-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fcd64-119">OUTPUTS</span></span>

### <span data-ttu-id="fcd64-120">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="fcd64-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="fcd64-121">Модуль **PSDiagnostics** добавляет класс **логдетаилс** в `Microsoft.PowerShell.Diagnostics` пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fcd64-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="fcd64-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fcd64-122">NOTES</span></span>

## <span data-ttu-id="fcd64-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fcd64-123">RELATED LINKS</span></span>

[<span data-ttu-id="fcd64-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fcd64-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="fcd64-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fcd64-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="fcd64-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fcd64-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
