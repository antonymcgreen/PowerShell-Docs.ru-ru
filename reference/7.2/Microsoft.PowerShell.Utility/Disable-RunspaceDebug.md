---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 589c8cb36a91de510ffc30973fe70729700ad020
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599395"
---
# <span data-ttu-id="a6e49-102">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="a6e49-102">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="a6e49-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a6e49-103">SYNOPSIS</span></span>
<span data-ttu-id="a6e49-104">Отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="a6e49-104">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="a6e49-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6e49-105">SYNTAX</span></span>

### <span data-ttu-id="a6e49-106">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a6e49-106">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a6e49-107">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a6e49-107">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="a6e49-108">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a6e49-108">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="a6e49-109">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a6e49-109">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="a6e49-110">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a6e49-110">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a6e49-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6e49-111">DESCRIPTION</span></span>

<span data-ttu-id="a6e49-112">`Disable-RunspaceDebug`Командлет отключает отладку в одном или нескольких пространствах выполнения и освобождает все ожидающие завершения отладчика.</span><span class="sxs-lookup"><span data-stu-id="a6e49-112">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="a6e49-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="a6e49-113">EXAMPLES</span></span>

### <span data-ttu-id="a6e49-114">1: отключить отладчик пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a6e49-114">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="a6e49-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6e49-115">PARAMETERS</span></span>

### <span data-ttu-id="a6e49-116">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="a6e49-116">-AppDomainName</span></span>

<span data-ttu-id="a6e49-117">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6e49-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="a6e49-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="a6e49-118">-ProcessName</span></span>

<span data-ttu-id="a6e49-119">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6e49-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="a6e49-120">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="a6e49-120">-Runspace</span></span>

<span data-ttu-id="a6e49-121">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="a6e49-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="a6e49-122">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="a6e49-122">-RunspaceId</span></span>

<span data-ttu-id="a6e49-123">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="a6e49-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="a6e49-124">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="a6e49-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="a6e49-125">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="a6e49-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="a6e49-126">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="a6e49-126">-RunspaceName</span></span>

<span data-ttu-id="a6e49-127">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="a6e49-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="a6e49-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a6e49-128">CommonParameters</span></span>

<span data-ttu-id="a6e49-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6e49-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6e49-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6e49-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6e49-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a6e49-131">INPUTS</span></span>

## <span data-ttu-id="a6e49-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a6e49-132">OUTPUTS</span></span>

## <span data-ttu-id="a6e49-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a6e49-133">NOTES</span></span>

## <span data-ttu-id="a6e49-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a6e49-134">RELATED LINKS</span></span>

[<span data-ttu-id="a6e49-135">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="a6e49-135">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="a6e49-136">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="a6e49-136">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

