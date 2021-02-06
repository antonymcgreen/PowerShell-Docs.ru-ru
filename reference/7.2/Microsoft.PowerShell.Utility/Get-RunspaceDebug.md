---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: a77695fe32345fda8e6a0284cd29becb432a4273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601506"
---
# <span data-ttu-id="c92e8-102">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="c92e8-102">Get-RunspaceDebug</span></span>

## <span data-ttu-id="c92e8-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c92e8-103">SYNOPSIS</span></span>
<span data-ttu-id="c92e8-104">Показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="c92e8-104">Shows runspace debugging options.</span></span>

## <span data-ttu-id="c92e8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c92e8-105">SYNTAX</span></span>

### <span data-ttu-id="c92e8-106">Рунспаценамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c92e8-106">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="c92e8-107">рунспацепараметерсет</span><span class="sxs-lookup"><span data-stu-id="c92e8-107">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="c92e8-108">рунспацеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="c92e8-108">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="c92e8-109">рунспацеинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="c92e8-109">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="c92e8-110">процесснамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="c92e8-110">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="c92e8-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c92e8-111">DESCRIPTION</span></span>

<span data-ttu-id="c92e8-112">`Get-RunspaceDebug`Командлет показывает параметры отладки пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="c92e8-112">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="c92e8-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c92e8-113">EXAMPLES</span></span>

### <span data-ttu-id="c92e8-114">1: отображение состояния отладчика пространства выполнения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c92e8-114">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="c92e8-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c92e8-115">PARAMETERS</span></span>

### <span data-ttu-id="c92e8-116">-Аппдомаиннаме</span><span class="sxs-lookup"><span data-stu-id="c92e8-116">-AppDomainName</span></span>

<span data-ttu-id="c92e8-117">Имя домена приложения, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c92e8-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="c92e8-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="c92e8-118">-ProcessName</span></span>

<span data-ttu-id="c92e8-119">Имя процесса, в котором размещается пространство выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c92e8-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="c92e8-120">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="c92e8-120">-Runspace</span></span>

<span data-ttu-id="c92e8-121">Одно или несколько объектов **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="c92e8-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="c92e8-122">-Рунспацеид</span><span class="sxs-lookup"><span data-stu-id="c92e8-122">-RunspaceId</span></span>

<span data-ttu-id="c92e8-123">Один или несколько идентификаторов **пространства выполнения** для отключения.</span><span class="sxs-lookup"><span data-stu-id="c92e8-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="c92e8-124">-Рунспацеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="c92e8-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="c92e8-125">Необходимо отключить одно или несколько идентификаторов GUID для **пространства выполнения** .</span><span class="sxs-lookup"><span data-stu-id="c92e8-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="c92e8-126">-Рунспаценаме</span><span class="sxs-lookup"><span data-stu-id="c92e8-126">-RunspaceName</span></span>

<span data-ttu-id="c92e8-127">Одно или несколько имен **пространства выполнения** , которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="c92e8-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="c92e8-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c92e8-128">CommonParameters</span></span>

<span data-ttu-id="c92e8-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c92e8-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c92e8-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c92e8-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c92e8-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c92e8-131">INPUTS</span></span>

## <span data-ttu-id="c92e8-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c92e8-132">OUTPUTS</span></span>

## <span data-ttu-id="c92e8-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c92e8-133">NOTES</span></span>

## <span data-ttu-id="c92e8-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c92e8-134">RELATED LINKS</span></span>

[<span data-ttu-id="c92e8-135">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="c92e8-135">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="c92e8-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="c92e8-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

