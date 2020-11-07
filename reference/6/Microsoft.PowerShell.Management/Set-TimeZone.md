---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 3738ac6202fa7a46c9a742e48edaeb1b82b5d749
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345125"
---
# <span data-ttu-id="34bc1-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="34bc1-103">Set-TimeZone</span></span>

## <span data-ttu-id="34bc1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="34bc1-104">SYNOPSIS</span></span>
<span data-ttu-id="34bc1-105">Устанавливает часовой пояс системы в указанный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="34bc1-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="34bc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34bc1-106">SYNTAX</span></span>

### <span data-ttu-id="34bc1-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="34bc1-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="34bc1-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="34bc1-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="34bc1-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="34bc1-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="34bc1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="34bc1-110">DESCRIPTION</span></span>

<span data-ttu-id="34bc1-111">`Set-TimeZone`Командлет устанавливает часовой пояс системы в указанный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="34bc1-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="34bc1-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="34bc1-112">EXAMPLES</span></span>

### <span data-ttu-id="34bc1-113">Пример 1. Задание часового пояса по идентификатору</span><span class="sxs-lookup"><span data-stu-id="34bc1-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="34bc1-114">В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).</span><span class="sxs-lookup"><span data-stu-id="34bc1-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### <span data-ttu-id="34bc1-115">Пример 2. Настройка часового пояса по имени</span><span class="sxs-lookup"><span data-stu-id="34bc1-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="34bc1-116">В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).</span><span class="sxs-lookup"><span data-stu-id="34bc1-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="34bc1-117">Как было показано в предыдущем примере, **идентификатор** и **имя** часового пояса не всегда совпадают.</span><span class="sxs-lookup"><span data-stu-id="34bc1-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="34bc1-118">Параметр **Name** должен соответствовать свойствам **StandardName** или **дайлигхтнаме** объекта **TimeZoneInfo** .</span><span class="sxs-lookup"><span data-stu-id="34bc1-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="34bc1-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34bc1-119">PARAMETERS</span></span>

### <span data-ttu-id="34bc1-120">-Id</span><span class="sxs-lookup"><span data-stu-id="34bc1-120">-Id</span></span>

<span data-ttu-id="34bc1-121">Указывает идентификатор часового пояса, который задается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="34bc1-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="34bc1-122">Полный список идентификаторов часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="34bc1-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="34bc1-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="34bc1-123">-InputObject</span></span>

<span data-ttu-id="34bc1-124">Указывает объект **TimeZoneInfo** для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="34bc1-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="34bc1-125">-Name</span><span class="sxs-lookup"><span data-stu-id="34bc1-125">-Name</span></span>

<span data-ttu-id="34bc1-126">Указывает имя часового пояса, который устанавливает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="34bc1-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="34bc1-127">Полный список имен часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="34bc1-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34bc1-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="34bc1-128">-PassThru</span></span>

<span data-ttu-id="34bc1-129">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="34bc1-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="34bc1-130">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="34bc1-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="34bc1-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="34bc1-131">-Confirm</span></span>

<span data-ttu-id="34bc1-132">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="34bc1-132">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34bc1-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="34bc1-133">-WhatIf</span></span>

<span data-ttu-id="34bc1-134">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="34bc1-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="34bc1-135">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="34bc1-135">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34bc1-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="34bc1-136">CommonParameters</span></span>

<span data-ttu-id="34bc1-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="34bc1-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34bc1-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="34bc1-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34bc1-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="34bc1-139">INPUTS</span></span>

### <span data-ttu-id="34bc1-140">System. String, System. TimeZoneInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="34bc1-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="34bc1-141">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="34bc1-141">OUTPUTS</span></span>

## <span data-ttu-id="34bc1-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="34bc1-142">NOTES</span></span>

<span data-ttu-id="34bc1-143">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="34bc1-143">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="34bc1-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="34bc1-144">RELATED LINKS</span></span>

[<span data-ttu-id="34bc1-145">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="34bc1-145">Get-TimeZone</span></span>](Get-TimeZone.md)
