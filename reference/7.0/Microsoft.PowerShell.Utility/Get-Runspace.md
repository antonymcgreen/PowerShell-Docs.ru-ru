---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 7d2dc7ce170d3f5de15fe5ad289e664e9f11847b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226042"
---
# <span data-ttu-id="1608b-103">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="1608b-103">Get-Runspace</span></span>

## <span data-ttu-id="1608b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1608b-104">SYNOPSIS</span></span>
<span data-ttu-id="1608b-105">Возвращает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1608b-105">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="1608b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1608b-106">SYNTAX</span></span>

### <span data-ttu-id="1608b-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1608b-107">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="1608b-108">идпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1608b-108">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="1608b-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1608b-109">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="1608b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1608b-110">DESCRIPTION</span></span>

<span data-ttu-id="1608b-111">`Get-Runspace`Командлет получает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1608b-111">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="1608b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="1608b-112">EXAMPLES</span></span>

### <span data-ttu-id="1608b-113">Пример 1. получение пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="1608b-113">Example 1: Get runspaces</span></span>

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

### <span data-ttu-id="1608b-114">Пример 2. Получение пространства выполнения по идентификатору</span><span class="sxs-lookup"><span data-stu-id="1608b-114">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="1608b-115">Пример 3. Получение пространства выполнения по имени</span><span class="sxs-lookup"><span data-stu-id="1608b-115">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="1608b-116">Пример 4. Получение пространства выполнения по InstanceId</span><span class="sxs-lookup"><span data-stu-id="1608b-116">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="1608b-117">В этом примере мы выявлением доступного пространства выполнения с помощью `Name` параметра и сохраняем возвращаемый объект в переменной `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="1608b-117">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="1608b-118">Это позволяет использовать свойства **пространства выполнения** при последующих запусках `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="1608b-118">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="1608b-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1608b-119">PARAMETERS</span></span>

### <span data-ttu-id="1608b-120">-Id</span><span class="sxs-lookup"><span data-stu-id="1608b-120">-Id</span></span>

<span data-ttu-id="1608b-121">Указывает идентификатор пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="1608b-121">Specifies the Id of a runspace</span></span>

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

### <span data-ttu-id="1608b-122">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="1608b-122">-InstanceId</span></span>

<span data-ttu-id="1608b-123">Указывает идентификатор GUID экземпляра выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="1608b-123">Specifies the instance ID GUID of a running job.</span></span>

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

### <span data-ttu-id="1608b-124">-Name</span><span class="sxs-lookup"><span data-stu-id="1608b-124">-Name</span></span>

<span data-ttu-id="1608b-125">Задает имя пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="1608b-125">Specifies the Name of a runspace</span></span>

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

### <span data-ttu-id="1608b-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1608b-126">CommonParameters</span></span>

<span data-ttu-id="1608b-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1608b-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1608b-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1608b-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1608b-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1608b-129">INPUTS</span></span>

## <span data-ttu-id="1608b-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1608b-130">OUTPUTS</span></span>

### <span data-ttu-id="1608b-131">System. Management. Automation. пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="1608b-131">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="1608b-132">Результаты команды можно передать `Get-Runspace` в `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="1608b-132">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="1608b-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1608b-133">NOTES</span></span>

## <span data-ttu-id="1608b-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1608b-134">RELATED LINKS</span></span>

[<span data-ttu-id="1608b-135">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="1608b-135">Debug-Runspace</span></span>](Debug-Runspace.md)
