---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 12530b9cf30b34598dfc3a049f5553920abecc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228986"
---
# <span data-ttu-id="f0476-103">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="f0476-103">Get-Runspace</span></span>

## <span data-ttu-id="f0476-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f0476-104">SYNOPSIS</span></span>
<span data-ttu-id="f0476-105">Возвращает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0476-105">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="f0476-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f0476-106">SYNTAX</span></span>

### <span data-ttu-id="f0476-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f0476-107">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f0476-108">идпараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0476-108">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="f0476-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="f0476-109">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="f0476-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f0476-110">DESCRIPTION</span></span>

<span data-ttu-id="f0476-111">`Get-Runspace`Командлет получает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0476-111">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="f0476-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0476-112">EXAMPLES</span></span>

### <span data-ttu-id="f0476-113">Пример 1. получение пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="f0476-113">Example 1: Get runspaces</span></span>

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### <span data-ttu-id="f0476-114">Пример 2. Получение пространства выполнения по идентификатору</span><span class="sxs-lookup"><span data-stu-id="f0476-114">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="f0476-115">Пример 3. Получение пространства выполнения по имени</span><span class="sxs-lookup"><span data-stu-id="f0476-115">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="f0476-116">Пример 4. Получение пространства выполнения по InstanceId</span><span class="sxs-lookup"><span data-stu-id="f0476-116">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="f0476-117">В этом примере мы выявлением доступного пространства выполнения с помощью `Name` параметра и сохраняем возвращаемый объект в переменной `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="f0476-117">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="f0476-118">Это позволяет использовать свойства **пространства выполнения** при последующих запусках `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="f0476-118">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="f0476-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f0476-119">PARAMETERS</span></span>

### <span data-ttu-id="f0476-120">-Id</span><span class="sxs-lookup"><span data-stu-id="f0476-120">-Id</span></span>

<span data-ttu-id="f0476-121">Указывает идентификатор пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="f0476-121">Specifies the Id of a runspace</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0476-122">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="f0476-122">-InstanceId</span></span>

<span data-ttu-id="f0476-123">Указывает идентификатор GUID экземпляра выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="f0476-123">Specifies the instance ID GUID of a running job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0476-124">-Name</span><span class="sxs-lookup"><span data-stu-id="f0476-124">-Name</span></span>

<span data-ttu-id="f0476-125">Задает имя пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="f0476-125">Specifies the Name of a runspace</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0476-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f0476-126">CommonParameters</span></span>

<span data-ttu-id="f0476-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f0476-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f0476-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f0476-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f0476-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f0476-129">INPUTS</span></span>

## <span data-ttu-id="f0476-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f0476-130">OUTPUTS</span></span>

### <span data-ttu-id="f0476-131">System. Management. Automation. пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="f0476-131">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="f0476-132">Результаты команды можно передать `Get-Runspace` в `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="f0476-132">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="f0476-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f0476-133">NOTES</span></span>

## <span data-ttu-id="f0476-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f0476-134">RELATED LINKS</span></span>

[<span data-ttu-id="f0476-135">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="f0476-135">Debug-Runspace</span></span>](Debug-Runspace.md)
