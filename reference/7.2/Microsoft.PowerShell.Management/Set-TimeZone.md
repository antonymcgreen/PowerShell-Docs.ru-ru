---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: ddce638972aabb1afc1c8fe500df380dd01dff14
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600195"
---
# <span data-ttu-id="31f99-102">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="31f99-102">Set-TimeZone</span></span>

## <span data-ttu-id="31f99-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="31f99-103">SYNOPSIS</span></span>
<span data-ttu-id="31f99-104">Устанавливает часовой пояс системы в указанный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="31f99-104">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="31f99-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31f99-105">SYNTAX</span></span>

### <span data-ttu-id="31f99-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="31f99-106">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="31f99-107">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="31f99-107">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="31f99-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="31f99-108">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="31f99-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31f99-109">DESCRIPTION</span></span>

<span data-ttu-id="31f99-110">`Set-TimeZone`Командлет устанавливает часовой пояс системы в указанный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="31f99-110">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="31f99-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="31f99-111">EXAMPLES</span></span>

### <span data-ttu-id="31f99-112">Пример 1. Задание часового пояса по идентификатору</span><span class="sxs-lookup"><span data-stu-id="31f99-112">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="31f99-113">В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).</span><span class="sxs-lookup"><span data-stu-id="31f99-113">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

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

### <span data-ttu-id="31f99-114">Пример 2. Настройка часового пояса по имени</span><span class="sxs-lookup"><span data-stu-id="31f99-114">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="31f99-115">В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).</span><span class="sxs-lookup"><span data-stu-id="31f99-115">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="31f99-116">Как было показано в предыдущем примере, **идентификатор** и **имя** часового пояса не всегда совпадают.</span><span class="sxs-lookup"><span data-stu-id="31f99-116">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="31f99-117">Параметр **Name** должен соответствовать свойствам **StandardName** или **дайлигхтнаме** объекта **TimeZoneInfo** .</span><span class="sxs-lookup"><span data-stu-id="31f99-117">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="31f99-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31f99-118">PARAMETERS</span></span>

### <span data-ttu-id="31f99-119">-Id</span><span class="sxs-lookup"><span data-stu-id="31f99-119">-Id</span></span>

<span data-ttu-id="31f99-120">Указывает идентификатор часового пояса, который задается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="31f99-120">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="31f99-121">Полный список идентификаторов часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="31f99-121">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="31f99-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="31f99-122">-InputObject</span></span>

<span data-ttu-id="31f99-123">Указывает объект **TimeZoneInfo** для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="31f99-123">Specifies a **TimeZoneInfo** object to use as input.</span></span>

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

### <span data-ttu-id="31f99-124">-Name</span><span class="sxs-lookup"><span data-stu-id="31f99-124">-Name</span></span>

<span data-ttu-id="31f99-125">Указывает имя часового пояса, который устанавливает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="31f99-125">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="31f99-126">Полный список имен часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="31f99-126">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="31f99-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="31f99-127">-PassThru</span></span>

<span data-ttu-id="31f99-128">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="31f99-128">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="31f99-129">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="31f99-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="31f99-130">-Confirm</span><span class="sxs-lookup"><span data-stu-id="31f99-130">-Confirm</span></span>

<span data-ttu-id="31f99-131">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="31f99-131">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="31f99-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="31f99-132">-WhatIf</span></span>

<span data-ttu-id="31f99-133">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="31f99-133">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="31f99-134">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="31f99-134">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="31f99-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="31f99-135">CommonParameters</span></span>

<span data-ttu-id="31f99-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31f99-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31f99-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31f99-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31f99-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="31f99-138">INPUTS</span></span>

### <span data-ttu-id="31f99-139">System. String, System. TimeZoneInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="31f99-139">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="31f99-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="31f99-140">OUTPUTS</span></span>

## <span data-ttu-id="31f99-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="31f99-141">NOTES</span></span>

<span data-ttu-id="31f99-142">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="31f99-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="31f99-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="31f99-143">RELATED LINKS</span></span>

[<span data-ttu-id="31f99-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="31f99-144">Get-TimeZone</span></span>](Get-TimeZone.md)
