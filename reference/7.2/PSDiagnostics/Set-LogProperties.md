---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: 51bb791e0633cf172252f5b0dca22373bb065fcc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604661"
---
# <span data-ttu-id="d0d6a-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d0d6a-102">Set-LogProperties</span></span>

## <span data-ttu-id="d0d6a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d0d6a-103">SYNOPSIS</span></span>
<span data-ttu-id="d0d6a-104">Изменяет свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="d0d6a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0d6a-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="d0d6a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0d6a-106">DESCRIPTION</span></span>

<span data-ttu-id="d0d6a-107">Этот командлет изменяет параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="d0d6a-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="d0d6a-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d0d6a-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d0d6a-110">EXAMPLES</span></span>

### <span data-ttu-id="d0d6a-111">Пример 1. изменение параметра хранения журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d6a-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="d0d6a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0d6a-112">PARAMETERS</span></span>

### <span data-ttu-id="d0d6a-113">-Force</span><span class="sxs-lookup"><span data-stu-id="d0d6a-113">-Force</span></span>

<span data-ttu-id="d0d6a-114">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="d0d6a-115">-Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="d0d6a-115">-LogDetails</span></span>

<span data-ttu-id="d0d6a-116">Обновленные параметры конфигурации, которые будут назначены журналу событий.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-116">The updated configuration settings to be assigned to the event log.</span></span>

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

### <span data-ttu-id="d0d6a-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d0d6a-117">CommonParameters</span></span>

<span data-ttu-id="d0d6a-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0d6a-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d0d6a-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0d6a-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d0d6a-120">INPUTS</span></span>

### <span data-ttu-id="d0d6a-121">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="d0d6a-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="d0d6a-122">В командлет необходимо передать полностью настроенный объект **логдетаилс** `Set-LogProperties` .</span><span class="sxs-lookup"><span data-stu-id="d0d6a-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="d0d6a-123">Поэтому для изменения одного параметра следует использовать `Get-LogProperties` для получения текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="d0d6a-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d0d6a-124">OUTPUTS</span></span>

### <span data-ttu-id="d0d6a-125">None</span><span class="sxs-lookup"><span data-stu-id="d0d6a-125">None</span></span>

## <span data-ttu-id="d0d6a-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d0d6a-126">NOTES</span></span>

<span data-ttu-id="d0d6a-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d0d6a-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d0d6a-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d0d6a-128">RELATED LINKS</span></span>

[<span data-ttu-id="d0d6a-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d0d6a-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="d0d6a-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d0d6a-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="d0d6a-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d0d6a-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

