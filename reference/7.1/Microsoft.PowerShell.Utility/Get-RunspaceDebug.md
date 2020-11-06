---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: 821b532dc44702af4243bf36ca7f5d4089a057d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227178"
---
# <span data-ttu-id="817da-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="817da-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="817da-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="817da-104">SYNOPSIS</span></span>
<span data-ttu-id="817da-105">Показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="817da-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="817da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="817da-106">SYNTAX</span></span>

### <span data-ttu-id="817da-107">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="817da-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="817da-108">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="817da-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="817da-109">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="817da-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="817da-110">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="817da-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="817da-111">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="817da-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="817da-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="817da-112">DESCRIPTION</span></span>

<span data-ttu-id="817da-113">`Get-RunspaceDebug`Командлет показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="817da-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="817da-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="817da-114">EXAMPLES</span></span>

### <span data-ttu-id="817da-115">1: отображение состояния отладчика пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="817da-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="817da-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="817da-116">PARAMETERS</span></span>

### <span data-ttu-id="817da-117">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="817da-117">-AppDomainName</span></span>

<span data-ttu-id="817da-118">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="817da-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="817da-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="817da-119">-ProcessName</span></span>

<span data-ttu-id="817da-120">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="817da-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="817da-121">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="817da-121">-Runspace</span></span>

<span data-ttu-id="817da-122">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="817da-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="817da-123">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="817da-123">-RunspaceId</span></span>

<span data-ttu-id="817da-124">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="817da-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="817da-125">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="817da-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="817da-126">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="817da-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="817da-127">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="817da-127">-RunspaceName</span></span>

<span data-ttu-id="817da-128">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="817da-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="817da-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="817da-129">CommonParameters</span></span>

<span data-ttu-id="817da-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="817da-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="817da-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="817da-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="817da-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="817da-132">INPUTS</span></span>

## <span data-ttu-id="817da-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="817da-133">OUTPUTS</span></span>

## <span data-ttu-id="817da-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="817da-134">NOTES</span></span>

## <span data-ttu-id="817da-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="817da-135">RELATED LINKS</span></span>

[<span data-ttu-id="817da-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="817da-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="817da-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="817da-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
