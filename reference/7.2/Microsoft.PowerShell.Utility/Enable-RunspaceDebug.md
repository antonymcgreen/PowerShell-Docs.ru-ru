---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 26ab9b9135eedafa0238eab5c07aa7abb7880ed4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599809"
---
# <span data-ttu-id="784e3-102">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="784e3-102">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="784e3-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="784e3-103">SYNOPSIS</span></span>
<span data-ttu-id="784e3-104">Включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="784e3-104">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="784e3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="784e3-105">SYNTAX</span></span>

### <span data-ttu-id="784e3-106">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="784e3-106">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="784e3-107">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="784e3-107">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="784e3-108">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="784e3-108">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="784e3-109">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="784e3-109">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="784e3-110">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="784e3-110">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="784e3-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="784e3-111">DESCRIPTION</span></span>

<span data-ttu-id="784e3-112">`Enable-RunspaceDebug`Командлет включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="784e3-112">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="784e3-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="784e3-113">EXAMPLES</span></span>

### <span data-ttu-id="784e3-114">1: включить отладчик пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="784e3-114">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="784e3-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="784e3-115">PARAMETERS</span></span>

### <span data-ttu-id="784e3-116">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="784e3-116">-AppDomainName</span></span>

<span data-ttu-id="784e3-117">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="784e3-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-118">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="784e3-118">-BreakAll</span></span>

<span data-ttu-id="784e3-119">Вызывает остановку любой выполняемой команды или скрипта в пространстве выполнения в пошаговом режиме, независимо от того, присоединен ли отладчик.</span><span class="sxs-lookup"><span data-stu-id="784e3-119">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="784e3-120">Сценарий или команда будет оставаться остановленной до тех пор, пока не будет присоединен отладчик для отладки текущей точки останова.</span><span class="sxs-lookup"><span data-stu-id="784e3-120">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-121">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="784e3-121">-ProcessName</span></span>

<span data-ttu-id="784e3-122">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="784e3-122">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-123">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="784e3-123">-Runspace</span></span>

<span data-ttu-id="784e3-124">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="784e3-124">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-125">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="784e3-125">-RunspaceId</span></span>

<span data-ttu-id="784e3-126">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="784e3-126">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-127">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="784e3-127">-RunspaceInstanceId</span></span>

<span data-ttu-id="784e3-128">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="784e3-128">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-129">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="784e3-129">-RunspaceName</span></span>

<span data-ttu-id="784e3-130">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="784e3-130">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="784e3-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="784e3-131">CommonParameters</span></span>

<span data-ttu-id="784e3-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="784e3-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="784e3-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="784e3-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="784e3-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="784e3-134">INPUTS</span></span>

## <span data-ttu-id="784e3-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="784e3-135">OUTPUTS</span></span>

## <span data-ttu-id="784e3-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="784e3-136">NOTES</span></span>

## <span data-ttu-id="784e3-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="784e3-137">RELATED LINKS</span></span>

[<span data-ttu-id="784e3-138">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="784e3-138">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="784e3-139">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="784e3-139">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

