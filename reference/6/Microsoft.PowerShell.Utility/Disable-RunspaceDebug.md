---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: ad9a08b3936044ef74c83b5e0d0cff146bf43e3f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229049"
---
# <span data-ttu-id="842f4-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="842f4-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="842f4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="842f4-104">SYNOPSIS</span></span>
<span data-ttu-id="842f4-105">Отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="842f4-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="842f4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="842f4-106">SYNTAX</span></span>

### <span data-ttu-id="842f4-107">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="842f4-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="842f4-108">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="842f4-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="842f4-109">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="842f4-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="842f4-110">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="842f4-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="842f4-111">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="842f4-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="842f4-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="842f4-112">DESCRIPTION</span></span>

<span data-ttu-id="842f4-113">`Disable-RunspaceDebug`Командлет отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="842f4-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="842f4-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="842f4-114">EXAMPLES</span></span>

### <span data-ttu-id="842f4-115">1: отключить отладчик пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="842f4-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="842f4-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="842f4-116">PARAMETERS</span></span>

### <span data-ttu-id="842f4-117">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="842f4-117">-AppDomainName</span></span>

<span data-ttu-id="842f4-118">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="842f4-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="842f4-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="842f4-119">-ProcessName</span></span>

<span data-ttu-id="842f4-120">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="842f4-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="842f4-121">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="842f4-121">-Runspace</span></span>

<span data-ttu-id="842f4-122">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="842f4-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="842f4-123">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="842f4-123">-RunspaceId</span></span>

<span data-ttu-id="842f4-124">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="842f4-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="842f4-125">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="842f4-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="842f4-126">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="842f4-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="842f4-127">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="842f4-127">-RunspaceName</span></span>

<span data-ttu-id="842f4-128">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="842f4-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="842f4-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="842f4-129">CommonParameters</span></span>

<span data-ttu-id="842f4-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="842f4-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="842f4-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="842f4-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="842f4-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="842f4-132">INPUTS</span></span>

## <span data-ttu-id="842f4-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="842f4-133">OUTPUTS</span></span>

## <span data-ttu-id="842f4-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="842f4-134">NOTES</span></span>

## <span data-ttu-id="842f4-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="842f4-135">RELATED LINKS</span></span>

[<span data-ttu-id="842f4-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="842f4-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="842f4-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="842f4-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
