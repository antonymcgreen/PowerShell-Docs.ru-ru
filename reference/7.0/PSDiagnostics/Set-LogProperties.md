---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: baf737a649e96488aff10959e02b59a0323e3ac4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225650"
---
# <span data-ttu-id="34320-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="34320-102">Set-LogProperties</span></span>

## <span data-ttu-id="34320-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="34320-103">SYNOPSIS</span></span>
<span data-ttu-id="34320-104">Изменяет свойства журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="34320-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="34320-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34320-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="34320-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="34320-106">DESCRIPTION</span></span>

<span data-ttu-id="34320-107">Этот командлет изменяет параметры конфигурации для журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="34320-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="34320-108">Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="34320-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="34320-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="34320-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="34320-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="34320-110">EXAMPLES</span></span>

### <span data-ttu-id="34320-111">Пример 1. изменение параметра хранения журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34320-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="34320-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34320-112">PARAMETERS</span></span>

### <span data-ttu-id="34320-113">-Force</span><span class="sxs-lookup"><span data-stu-id="34320-113">-Force</span></span>

<span data-ttu-id="34320-114">Используется для принудительного изменения без запроса.</span><span class="sxs-lookup"><span data-stu-id="34320-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="34320-115">-Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="34320-115">-LogDetails</span></span>

<span data-ttu-id="34320-116">Обновленные параметры конфигурации, которые будут назначены журналу событий.</span><span class="sxs-lookup"><span data-stu-id="34320-116">The updated configuration settings to be assigned to the event log.</span></span>

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

### <span data-ttu-id="34320-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="34320-117">CommonParameters</span></span>

<span data-ttu-id="34320-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="34320-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34320-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="34320-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34320-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="34320-120">INPUTS</span></span>

### <span data-ttu-id="34320-121">Microsoft. PowerShell. Diagnostics. Логдетаилс</span><span class="sxs-lookup"><span data-stu-id="34320-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="34320-122">В командлет необходимо передать полностью настроенный объект **логдетаилс** `Set-LogProperties` .</span><span class="sxs-lookup"><span data-stu-id="34320-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="34320-123">Поэтому для изменения одного параметра следует использовать `Get-LogProperties` для получения текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34320-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="34320-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="34320-124">OUTPUTS</span></span>

### <span data-ttu-id="34320-125">Нет</span><span class="sxs-lookup"><span data-stu-id="34320-125">None</span></span>

## <span data-ttu-id="34320-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="34320-126">NOTES</span></span>

<span data-ttu-id="34320-127">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="34320-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="34320-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="34320-128">RELATED LINKS</span></span>

[<span data-ttu-id="34320-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="34320-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="34320-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="34320-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="34320-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="34320-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
