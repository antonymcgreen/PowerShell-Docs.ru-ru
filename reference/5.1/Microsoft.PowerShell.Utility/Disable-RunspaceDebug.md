---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 79fe5c58f26f9146adfca18827f65cff53bde23f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227702"
---
# <span data-ttu-id="88d56-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="88d56-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="88d56-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="88d56-104">SYNOPSIS</span></span>
<span data-ttu-id="88d56-105">Отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="88d56-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="88d56-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88d56-106">SYNTAX</span></span>

### <span data-ttu-id="88d56-107">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="88d56-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="88d56-108">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="88d56-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="88d56-109">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="88d56-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="88d56-110">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="88d56-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="88d56-111">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="88d56-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="88d56-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="88d56-112">DESCRIPTION</span></span>

<span data-ttu-id="88d56-113">`Disable-RunspaceDebug`Командлет отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="88d56-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="88d56-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="88d56-114">EXAMPLES</span></span>

### <span data-ttu-id="88d56-115">1: отключить отладчик пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="88d56-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="88d56-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88d56-116">PARAMETERS</span></span>

### <span data-ttu-id="88d56-117">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="88d56-117">-AppDomainName</span></span>

<span data-ttu-id="88d56-118">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d56-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="88d56-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="88d56-119">-ProcessName</span></span>

<span data-ttu-id="88d56-120">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88d56-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="88d56-121">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="88d56-121">-Runspace</span></span>

<span data-ttu-id="88d56-122">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="88d56-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="88d56-123">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="88d56-123">-RunspaceId</span></span>

<span data-ttu-id="88d56-124">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="88d56-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="88d56-125">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="88d56-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="88d56-126">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="88d56-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="88d56-127">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="88d56-127">-RunspaceName</span></span>

<span data-ttu-id="88d56-128">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="88d56-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="88d56-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="88d56-129">CommonParameters</span></span>

<span data-ttu-id="88d56-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="88d56-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="88d56-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="88d56-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="88d56-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="88d56-132">INPUTS</span></span>

## <span data-ttu-id="88d56-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="88d56-133">OUTPUTS</span></span>

## <span data-ttu-id="88d56-134">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="88d56-134">NOTES</span></span>

## <span data-ttu-id="88d56-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="88d56-135">RELATED LINKS</span></span>

[<span data-ttu-id="88d56-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="88d56-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="88d56-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="88d56-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
