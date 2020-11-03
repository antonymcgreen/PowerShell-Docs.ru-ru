---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: e5d66d628f2240c86c8b94b846b0397d517adf43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226513"
---
# <span data-ttu-id="ebe49-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ebe49-102">Set-LogProperties</span></span>

## <span data-ttu-id="ebe49-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ebe49-103">SYNOPSIS</span></span>
<span data-ttu-id="ebe49-104">Изменяет свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe49-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="ebe49-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ebe49-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="ebe49-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ebe49-106">DESCRIPTION</span></span>

<span data-ttu-id="ebe49-107">Этот командлет изменяет параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe49-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="ebe49-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="ebe49-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="ebe49-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ebe49-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ebe49-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ebe49-110">EXAMPLES</span></span>

### <span data-ttu-id="ebe49-111">Пример 1. изменение параметра хранения журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe49-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

```powershell
$logDetails = Get-LogProperties 'Windows PowerShell'
$logDetails.Retention = $True
Set-LogProperties -LogDetails $logDetails
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : True
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="ebe49-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ebe49-112">PARAMETERS</span></span>

### <span data-ttu-id="ebe49-113">-Force</span><span class="sxs-lookup"><span data-stu-id="ebe49-113">-Force</span></span>

<span data-ttu-id="ebe49-114">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="ebe49-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="ebe49-115">-Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="ebe49-115">-LogDetails</span></span>

<span data-ttu-id="ebe49-116">Обновленные параметры конфигурации, которые будут назначены журналу событий.</span><span class="sxs-lookup"><span data-stu-id="ebe49-116">The updated configuration settings to be assigned to the event log.</span></span>

```yaml
Type: Microsoft.PowerShell.Diagnostics.LogDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ebe49-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ebe49-117">CommonParameters</span></span>

<span data-ttu-id="ebe49-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ebe49-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ebe49-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ebe49-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ebe49-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ebe49-120">INPUTS</span></span>

### <span data-ttu-id="ebe49-121">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="ebe49-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="ebe49-122">В командлет необходимо передать полностью настроенный объект **логдетаилс** `Set-LogProperties` .</span><span class="sxs-lookup"><span data-stu-id="ebe49-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="ebe49-123">Поэтому для изменения одного параметра следует использовать `Get-LogProperties` для получения текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ebe49-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="ebe49-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ebe49-124">OUTPUTS</span></span>

### <span data-ttu-id="ebe49-125">Нет</span><span class="sxs-lookup"><span data-stu-id="ebe49-125">None</span></span>

## <span data-ttu-id="ebe49-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ebe49-126">NOTES</span></span>

<span data-ttu-id="ebe49-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="ebe49-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ebe49-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ebe49-128">RELATED LINKS</span></span>

[<span data-ttu-id="ebe49-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ebe49-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="ebe49-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ebe49-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="ebe49-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ebe49-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

