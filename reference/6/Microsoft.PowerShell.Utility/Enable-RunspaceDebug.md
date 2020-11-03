---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 5b92af5f98239375eec35b82c3ae3756c9853d22
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229045"
---
# <span data-ttu-id="ca90f-103">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ca90f-103">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="ca90f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ca90f-104">SYNOPSIS</span></span>
<span data-ttu-id="ca90f-105">Включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="ca90f-105">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="ca90f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca90f-106">SYNTAX</span></span>

### <span data-ttu-id="ca90f-107">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ca90f-107">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ca90f-108">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="ca90f-108">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="ca90f-109">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="ca90f-109">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="ca90f-110">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="ca90f-110">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="ca90f-111">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="ca90f-111">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ca90f-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca90f-112">DESCRIPTION</span></span>

<span data-ttu-id="ca90f-113">`Enable-RunspaceDebug`Командлет включает отладку в пространствах выполнения, где любая точка останова сохраняется до тех пор, пока не будет присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="ca90f-113">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="ca90f-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="ca90f-114">EXAMPLES</span></span>

### <span data-ttu-id="ca90f-115">1: включить отладчик пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ca90f-115">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="ca90f-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca90f-116">PARAMETERS</span></span>

### <span data-ttu-id="ca90f-117">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="ca90f-117">-AppDomainName</span></span>

<span data-ttu-id="ca90f-118">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca90f-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ca90f-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="ca90f-119">-BreakAll</span></span>

<span data-ttu-id="ca90f-120">Вызывает остановку любой выполняемой команды или скрипта в пространстве выполнения в пошаговом режиме, независимо от того, присоединен ли отладчик.</span><span class="sxs-lookup"><span data-stu-id="ca90f-120">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="ca90f-121">Сценарий или команда будет оставаться остановленной до тех пор, пока не будет присоединен отладчик для отладки текущей точки останова.</span><span class="sxs-lookup"><span data-stu-id="ca90f-121">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

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

### <span data-ttu-id="ca90f-122">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="ca90f-122">-ProcessName</span></span>

<span data-ttu-id="ca90f-123">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca90f-123">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ca90f-124">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="ca90f-124">-Runspace</span></span>

<span data-ttu-id="ca90f-125">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="ca90f-125">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="ca90f-126">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="ca90f-126">-RunspaceId</span></span>

<span data-ttu-id="ca90f-127">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="ca90f-127">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="ca90f-128">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="ca90f-128">-RunspaceInstanceId</span></span>

<span data-ttu-id="ca90f-129">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="ca90f-129">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="ca90f-130">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="ca90f-130">-RunspaceName</span></span>

<span data-ttu-id="ca90f-131">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="ca90f-131">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="ca90f-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ca90f-132">CommonParameters</span></span>

<span data-ttu-id="ca90f-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca90f-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca90f-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca90f-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca90f-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ca90f-135">INPUTS</span></span>

## <span data-ttu-id="ca90f-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ca90f-136">OUTPUTS</span></span>

## <span data-ttu-id="ca90f-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ca90f-137">NOTES</span></span>

## <span data-ttu-id="ca90f-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ca90f-138">RELATED LINKS</span></span>

[<span data-ttu-id="ca90f-139">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ca90f-139">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="ca90f-140">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ca90f-140">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
