---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228469"
---
# <span data-ttu-id="71247-103">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="71247-103">Checkpoint-Computer</span></span>

## <span data-ttu-id="71247-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="71247-104">SYNOPSIS</span></span>
<span data-ttu-id="71247-105">Создает точку восстановления системы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71247-105">Creates a system restore point on the local computer.</span></span>

## <span data-ttu-id="71247-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71247-106">SYNTAX</span></span>

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## <span data-ttu-id="71247-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71247-107">DESCRIPTION</span></span>

<span data-ttu-id="71247-108">`Checkpoint-Computer`Командлет создает точку восстановления системы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71247-108">The `Checkpoint-Computer` cmdlet creates a system restore point on the local computer.</span></span>

<span data-ttu-id="71247-109">Точки восстановления системы и `Checkpoint-Computer` командлеты поддерживаются только в клиентских операционных системах, таких как Windows 8, Windows 7, Windows Vista и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="71247-109">System restore points and the `Checkpoint-Computer` cmdlet are supported only on client operating systems, such as Windows 8, Windows 7, Windows Vista, and Windows XP.</span></span>

<span data-ttu-id="71247-110">Начиная с Windows 8, `Checkpoint-Computer` каждый день нельзя создавать более одной контрольной точки.</span><span class="sxs-lookup"><span data-stu-id="71247-110">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one checkpoint each day.</span></span>

## <span data-ttu-id="71247-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="71247-111">EXAMPLES</span></span>

### <span data-ttu-id="71247-112">Пример 1. Создание точки восстановления системы</span><span class="sxs-lookup"><span data-stu-id="71247-112">Example 1: Create a system restore point</span></span>

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

<span data-ttu-id="71247-113">Эта команда создает точку восстановления системы с именем Install MyApp.</span><span class="sxs-lookup"><span data-stu-id="71247-113">This command creates a system restore point called Install MyApp.</span></span>
<span data-ttu-id="71247-114">Она использует тип точки восстановления APPLICATION_INSTALL по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71247-114">It uses the default APPLICATION_INSTALL restore point type.</span></span>

### <span data-ttu-id="71247-115">Пример 2. Создание точки восстановления системы MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="71247-115">Example 2: Create a system MODIFY_SETTINGS restore point</span></span>

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

<span data-ttu-id="71247-116">Эта команда создает точку восстановления системы MODIFY_SETTINGS с именем ChangeNetSettings.</span><span class="sxs-lookup"><span data-stu-id="71247-116">This command creates a MODIFY_SETTINGS system restore point called "ChangeNetSettings".</span></span>

## <span data-ttu-id="71247-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71247-117">PARAMETERS</span></span>

### <span data-ttu-id="71247-118">-Description</span><span class="sxs-lookup"><span data-stu-id="71247-118">-Description</span></span>

<span data-ttu-id="71247-119">Указывает описательное имя для точки восстановления.</span><span class="sxs-lookup"><span data-stu-id="71247-119">Specifies a descriptive name for the restore point.</span></span>
<span data-ttu-id="71247-120">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="71247-120">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71247-121">-Ресторепоинттипе</span><span class="sxs-lookup"><span data-stu-id="71247-121">-RestorePointType</span></span>

<span data-ttu-id="71247-122">Указывает тип точки восстановления.</span><span class="sxs-lookup"><span data-stu-id="71247-122">Specifies the type of restore point.</span></span>
<span data-ttu-id="71247-123">Значение по умолчанию — APPLICATION_INSTALL.</span><span class="sxs-lookup"><span data-stu-id="71247-123">The default is APPLICATION_INSTALL.</span></span>

<span data-ttu-id="71247-124">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="71247-124">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="71247-125">APPLICATION_INSTALL</span><span class="sxs-lookup"><span data-stu-id="71247-125">APPLICATION_INSTALL</span></span>
- <span data-ttu-id="71247-126">APPLICATION_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="71247-126">APPLICATION_UNINSTALL</span></span>
- <span data-ttu-id="71247-127">DEVICE_DRIVER_INSTALL</span><span class="sxs-lookup"><span data-stu-id="71247-127">DEVICE_DRIVER_INSTALL</span></span>
- <span data-ttu-id="71247-128">MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="71247-128">MODIFY_SETTINGS</span></span>
- <span data-ttu-id="71247-129">CANCELLED_OPERATION</span><span class="sxs-lookup"><span data-stu-id="71247-129">CANCELLED_OPERATION</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71247-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="71247-130">CommonParameters</span></span>

<span data-ttu-id="71247-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71247-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71247-132">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="71247-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="71247-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="71247-133">INPUTS</span></span>

### <span data-ttu-id="71247-134">Нет</span><span class="sxs-lookup"><span data-stu-id="71247-134">None</span></span>

<span data-ttu-id="71247-135">Вы не можете передать объекты в `Checkpoint-Computer` .</span><span class="sxs-lookup"><span data-stu-id="71247-135">You cannot pipe objects to `Checkpoint-Computer`.</span></span>

## <span data-ttu-id="71247-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="71247-136">OUTPUTS</span></span>

### <span data-ttu-id="71247-137">Нет</span><span class="sxs-lookup"><span data-stu-id="71247-137">None</span></span>

<span data-ttu-id="71247-138">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="71247-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="71247-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="71247-139">NOTES</span></span>

- <span data-ttu-id="71247-140">Этот командлет использует метод **креатересторепоинт** класса **SystemRestore** с событием **BEGIN_SYSTEM_CHANGE** .</span><span class="sxs-lookup"><span data-stu-id="71247-140">This cmdlet uses the **CreateRestorePoint** method of the **SystemRestore** class with a **BEGIN_SYSTEM_CHANGE** event.</span></span>
- <span data-ttu-id="71247-141">Начиная с Windows 8, `Checkpoint-Computer` каждый день не может создавать более одной точки восстановления системы.</span><span class="sxs-lookup"><span data-stu-id="71247-141">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one system restore point each day.</span></span> <span data-ttu-id="71247-142">При попытке создать новую точку восстановления до истечения 24-часового периода в Windows PowerShell возникнет следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="71247-142">If you try to create a new restore point before the 24-hour period has elapsed, Windows PowerShell generates the following error:</span></span>

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## <span data-ttu-id="71247-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="71247-143">RELATED LINKS</span></span>

[<span data-ttu-id="71247-144">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="71247-144">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="71247-145">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="71247-145">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="71247-146">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="71247-146">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="71247-147">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="71247-147">Restore-Computer</span></span>](Restore-Computer.md)
