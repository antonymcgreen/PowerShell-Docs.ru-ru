---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: a04be33767c9e0435de9693fbd5e07d66705b5d1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226393"
---
# <span data-ttu-id="15eb0-102">Get-Uptime</span><span class="sxs-lookup"><span data-stu-id="15eb0-102">Get-Uptime</span></span>

## <span data-ttu-id="15eb0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="15eb0-103">SYNOPSIS</span></span>
<span data-ttu-id="15eb0-104">Получение **временного интервала** с момента последней загрузки.</span><span class="sxs-lookup"><span data-stu-id="15eb0-104">Get the **TimeSpan** since last boot.</span></span>

## <span data-ttu-id="15eb0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15eb0-105">SYNTAX</span></span>

### <span data-ttu-id="15eb0-106">TimeSpan (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="15eb0-106">Timespan (Default)</span></span>

```
Get-Uptime [<CommonParameters>]
```

### <span data-ttu-id="15eb0-107">Шедших</span><span class="sxs-lookup"><span data-stu-id="15eb0-107">Since</span></span>

```
Get-Uptime [-Since] [<CommonParameters>]
```

## <span data-ttu-id="15eb0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15eb0-108">DESCRIPTION</span></span>

<span data-ttu-id="15eb0-109">Этот командлет возвращает время, прошедшее с момента последней загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="15eb0-109">This cmdlet returns the time elapsed since the last boot of the operating system.</span></span>

<span data-ttu-id="15eb0-110">`Get-Uptime`Командлет был представлен в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="15eb0-110">The `Get-Uptime` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="15eb0-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="15eb0-111">EXAMPLES</span></span>

### <span data-ttu-id="15eb0-112">Пример 1. Отображение времени с момента последней загрузки</span><span class="sxs-lookup"><span data-stu-id="15eb0-112">Example 1 - Show time since last boot</span></span>

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### <span data-ttu-id="15eb0-113">Пример 2. Отображение времени последней загрузки</span><span class="sxs-lookup"><span data-stu-id="15eb0-113">Example 2 - Show the time of the last boot</span></span>

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## <span data-ttu-id="15eb0-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15eb0-114">PARAMETERS</span></span>

### <span data-ttu-id="15eb0-115">— С</span><span class="sxs-lookup"><span data-stu-id="15eb0-115">-Since</span></span>

<span data-ttu-id="15eb0-116">Вызов командлета для возврата объекта **DateTime** , представляющего время последней загрузки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="15eb0-116">Cause the cmdlet to return a **DateTime** object representing the last time that the operating system was booted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15eb0-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="15eb0-117">CommonParameters</span></span>

<span data-ttu-id="15eb0-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15eb0-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15eb0-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15eb0-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15eb0-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="15eb0-120">INPUTS</span></span>

### <span data-ttu-id="15eb0-121">Нет</span><span class="sxs-lookup"><span data-stu-id="15eb0-121">None</span></span>

## <span data-ttu-id="15eb0-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="15eb0-122">OUTPUTS</span></span>

### <span data-ttu-id="15eb0-123">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="15eb0-123">System.TimeSpan</span></span>

<span data-ttu-id="15eb0-124">Это возвращаемый тип по умолчанию, если параметры не используются.</span><span class="sxs-lookup"><span data-stu-id="15eb0-124">This is the default return type when no parameters are used.</span></span>

### <span data-ttu-id="15eb0-125">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="15eb0-125">System.DateTime</span></span>

<span data-ttu-id="15eb0-126">Этот тип возвращается при использовании параметра **с** .</span><span class="sxs-lookup"><span data-stu-id="15eb0-126">This type is returned when using the **Since** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="15eb0-127">Если параметр быстрого запуска Windows включен, Windows не обновляет значение, хранящееся в **LastBootUpTime**.</span><span class="sxs-lookup"><span data-stu-id="15eb0-127">If Windows fast startup is enabled, Windows does not update the value stored in **LastBootUpTime**.</span></span> <span data-ttu-id="15eb0-128">Чтобы отключить быстрый запуск, выполните следующую команду: `Powercfg -h off` .</span><span class="sxs-lookup"><span data-stu-id="15eb0-128">To disable fast startup, run the following command: `Powercfg -h off`.</span></span>
>
> <span data-ttu-id="15eb0-129">Дополнительные сведения о быстром запуске Windows см. в разделе [различия быстрого запуска от пробуждения из спящего режима](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span><span class="sxs-lookup"><span data-stu-id="15eb0-129">For more information about Windows fast startup, see [Distinguishing Fast Startup from Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span></span>

## <span data-ttu-id="15eb0-130">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="15eb0-130">NOTES</span></span>

<span data-ttu-id="15eb0-131">В Windows возвращаемое значение совпадает со свойством **LastBootUpTime** класса **Win32_OperatingSystem** в WMI.</span><span class="sxs-lookup"><span data-stu-id="15eb0-131">On Windows, the value returned is the same as the **LastBootUpTime** property of the **Win32_OperatingSystem** class in WMI.</span></span>

## <span data-ttu-id="15eb0-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="15eb0-132">RELATED LINKS</span></span>

[<span data-ttu-id="15eb0-133">Win32_OperatingSystem</span><span class="sxs-lookup"><span data-stu-id="15eb0-133">Win32_OperatingSystem</span></span>](/windows/win32/cimwin32prov/win32-operatingsystem#properties)
