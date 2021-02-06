---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 34843894cb6253e3d8e89072cf79cb9237d4fc19
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602869"
---
# <span data-ttu-id="6e254-102">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="6e254-102">Get-Runspace</span></span>

## <span data-ttu-id="6e254-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6e254-103">SYNOPSIS</span></span>
<span data-ttu-id="6e254-104">Возвращает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e254-104">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="6e254-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e254-105">SYNTAX</span></span>

### <span data-ttu-id="6e254-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6e254-106">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6e254-107">идпараметерсет</span><span class="sxs-lookup"><span data-stu-id="6e254-107">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="6e254-108">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="6e254-108">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="6e254-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e254-109">DESCRIPTION</span></span>

<span data-ttu-id="6e254-110">`Get-Runspace`Командлет получает активные пространства выполнения в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e254-110">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="6e254-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="6e254-111">EXAMPLES</span></span>

### <span data-ttu-id="6e254-112">Пример 1. получение пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="6e254-112">Example 1: Get runspaces</span></span>

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

### <span data-ttu-id="6e254-113">Пример 2. Получение пространства выполнения по идентификатору</span><span class="sxs-lookup"><span data-stu-id="6e254-113">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="6e254-114">Пример 3. Получение пространства выполнения по имени</span><span class="sxs-lookup"><span data-stu-id="6e254-114">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="6e254-115">Пример 4. Получение пространства выполнения по InstanceId</span><span class="sxs-lookup"><span data-stu-id="6e254-115">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="6e254-116">В этом примере мы выявлением доступного пространства выполнения с помощью `Name` параметра и сохраняем возвращаемый объект в переменной `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="6e254-116">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="6e254-117">Это позволяет использовать свойства **пространства выполнения** при последующих запусках `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="6e254-117">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="6e254-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e254-118">PARAMETERS</span></span>

### <span data-ttu-id="6e254-119">-Id</span><span class="sxs-lookup"><span data-stu-id="6e254-119">-Id</span></span>

<span data-ttu-id="6e254-120">Указывает идентификатор пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="6e254-120">Specifies the Id of a runspace</span></span>

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

### <span data-ttu-id="6e254-121">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="6e254-121">-InstanceId</span></span>

<span data-ttu-id="6e254-122">Указывает идентификатор GUID экземпляра выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="6e254-122">Specifies the instance ID GUID of a running job.</span></span>

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

### <span data-ttu-id="6e254-123">-Name</span><span class="sxs-lookup"><span data-stu-id="6e254-123">-Name</span></span>

<span data-ttu-id="6e254-124">Задает имя пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="6e254-124">Specifies the Name of a runspace</span></span>

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

### <span data-ttu-id="6e254-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6e254-125">CommonParameters</span></span>

<span data-ttu-id="6e254-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e254-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e254-127">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e254-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e254-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6e254-128">INPUTS</span></span>

## <span data-ttu-id="6e254-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6e254-129">OUTPUTS</span></span>

### <span data-ttu-id="6e254-130">System. Management. Automation. пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="6e254-130">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="6e254-131">Результаты команды можно передать `Get-Runspace` в `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="6e254-131">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="6e254-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6e254-132">NOTES</span></span>

## <span data-ttu-id="6e254-133">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6e254-133">RELATED LINKS</span></span>

[<span data-ttu-id="6e254-134">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="6e254-134">Debug-Runspace</span></span>](Debug-Runspace.md)

