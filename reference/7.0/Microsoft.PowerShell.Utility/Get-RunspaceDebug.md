---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: 627b1446f37b951eb5455ca1d9b41ec5453e2cc7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226041"
---
# <span data-ttu-id="bbd4d-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bbd4d-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="bbd4d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bbd4d-104">SYNOPSIS</span></span>
<span data-ttu-id="bbd4d-105">Показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="bbd4d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bbd4d-106">SYNTAX</span></span>

### <span data-ttu-id="bbd4d-107">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bbd4d-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bbd4d-108">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bbd4d-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="bbd4d-109">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bbd4d-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="bbd4d-110">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bbd4d-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="bbd4d-111">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bbd4d-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bbd4d-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bbd4d-112">DESCRIPTION</span></span>

<span data-ttu-id="bbd4d-113">`Get-RunspaceDebug`Командлет показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="bbd4d-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="bbd4d-114">EXAMPLES</span></span>

### <span data-ttu-id="bbd4d-115">1: отображение состояния отладчика пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bbd4d-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="bbd4d-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bbd4d-116">PARAMETERS</span></span>

### <span data-ttu-id="bbd4d-117">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="bbd4d-117">-AppDomainName</span></span>

<span data-ttu-id="bbd4d-118">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="bbd4d-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="bbd4d-119">-ProcessName</span></span>

<span data-ttu-id="bbd4d-120">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="bbd4d-121">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="bbd4d-121">-Runspace</span></span>

<span data-ttu-id="bbd4d-122">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="bbd4d-123">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="bbd4d-123">-RunspaceId</span></span>

<span data-ttu-id="bbd4d-124">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="bbd4d-125">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="bbd4d-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="bbd4d-126">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="bbd4d-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="bbd4d-127">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="bbd4d-127">-RunspaceName</span></span>

<span data-ttu-id="bbd4d-128">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="bbd4d-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bbd4d-129">CommonParameters</span></span>

<span data-ttu-id="bbd4d-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bbd4d-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bbd4d-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bbd4d-132">INPUTS</span></span>

## <span data-ttu-id="bbd4d-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bbd4d-133">OUTPUTS</span></span>

## <span data-ttu-id="bbd4d-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bbd4d-134">NOTES</span></span>

## <span data-ttu-id="bbd4d-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bbd4d-135">RELATED LINKS</span></span>

[<span data-ttu-id="bbd4d-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bbd4d-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="bbd4d-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bbd4d-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
