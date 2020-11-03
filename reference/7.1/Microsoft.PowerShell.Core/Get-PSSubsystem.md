---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: ''
schema: 2.0.0
ms.openlocfilehash: 34998e7c4a6876821df949019970dc1d87297397
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232929"
---
# <span data-ttu-id="5f5e8-101">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="5f5e8-101">Get-PSSubsystem</span></span>

## <span data-ttu-id="5f5e8-102">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5f5e8-102">SYNOPSIS</span></span>
<span data-ttu-id="5f5e8-103">Извлекает сведения о подсистемах, зарегистрированных в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-103">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="5f5e8-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f5e8-104">SYNTAX</span></span>

### <span data-ttu-id="5f5e8-105">Жеталлсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5f5e8-105">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="5f5e8-106">жетбикиндсет</span><span class="sxs-lookup"><span data-stu-id="5f5e8-106">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="5f5e8-107">жетбитипесет</span><span class="sxs-lookup"><span data-stu-id="5f5e8-107">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="5f5e8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f5e8-108">DESCRIPTION</span></span>

<span data-ttu-id="5f5e8-109">Извлекает сведения о подсистемах, зарегистрированных в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-109">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="5f5e8-110">Это экспериментальная функция.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-110">This is an experimental feature.</span></span> <span data-ttu-id="5f5e8-111">Этот командлет доступен только при `PSSubsystemPluginModel` включенной функции.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-111">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="5f5e8-112">Дополнительные сведения см. [в разделе Использование экспериментальных функций](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="5f5e8-112">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="5f5e8-113">Эта функция позволяет разделять компоненты `System.Management.Automation.dll` в отдельные подсистемы, находящиеся в их собственной сборке.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-113">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="5f5e8-114">Такое разделение сокращает объем дискового пространства ядра PowerShell и позволяет этим компонентам стать необязательными для минимальной установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-114">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="5f5e8-115">В настоящее время поддерживается только подсистема **CommandPredictor** .</span><span class="sxs-lookup"><span data-stu-id="5f5e8-115">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="5f5e8-116">Эта подсистема используется вместе с модулем PSReadLine для предоставления настраиваемых подключаемых модулей прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-116">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="5f5e8-117">В будущем **задание** , **CommandCompleter** , **удаленное взаимодействие** и другие компоненты можно будет разделить на сборки подсистемы за пределами `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-117">In future, **Job** , **CommandCompleter** , **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="5f5e8-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="5f5e8-118">EXAMPLES</span></span>

### <span data-ttu-id="5f5e8-119">Пример 1. Отображение всех доступных подсистем</span><span class="sxs-lookup"><span data-stu-id="5f5e8-119">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="5f5e8-120">Пример 2. Отображение всех доступных подсистем определенного типа</span><span class="sxs-lookup"><span data-stu-id="5f5e8-120">Example 2 - Display all available subsystems of a specific kind</span></span>

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## <span data-ttu-id="5f5e8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f5e8-121">PARAMETERS</span></span>

### <span data-ttu-id="5f5e8-122">-Kind</span><span class="sxs-lookup"><span data-stu-id="5f5e8-122">-Kind</span></span>


<span data-ttu-id="5f5e8-123">Указывает тип возвращаемой подсистемы.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-123">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="5f5e8-124">Допустимые значения: `CommandPredictor` .</span><span class="sxs-lookup"><span data-stu-id="5f5e8-124">Valid values are: `CommandPredictor`.</span></span>

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5f5e8-125">-Субсистемтипе</span><span class="sxs-lookup"><span data-stu-id="5f5e8-125">-SubsystemType</span></span>

<span data-ttu-id="5f5e8-126">Указывает тип возвращаемой подсистемы.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-126">Specifies the type of subsystem to be returned.</span></span>

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5f5e8-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5f5e8-127">CommonParameters</span></span>

<span data-ttu-id="5f5e8-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5f5e8-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f5e8-129">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5f5e8-129">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5f5e8-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5f5e8-130">INPUTS</span></span>

### <span data-ttu-id="5f5e8-131">System. Management. Automation. подсистема. Субсистемкинд</span><span class="sxs-lookup"><span data-stu-id="5f5e8-131">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="5f5e8-132">System.Type</span><span class="sxs-lookup"><span data-stu-id="5f5e8-132">System.Type</span></span>

## <span data-ttu-id="5f5e8-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5f5e8-133">OUTPUTS</span></span>

### <span data-ttu-id="5f5e8-134">System. Management. Automation. подсистема. Субсистеминфо</span><span class="sxs-lookup"><span data-stu-id="5f5e8-134">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="5f5e8-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5f5e8-135">NOTES</span></span>

## <span data-ttu-id="5f5e8-136">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5f5e8-136">RELATED LINKS</span></span>

[<span data-ttu-id="5f5e8-137">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="5f5e8-137">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="5f5e8-138">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="5f5e8-138">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="5f5e8-139">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="5f5e8-139">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="5f5e8-140">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="5f5e8-140">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="5f5e8-141">Использование экспериментальных возможностей</span><span class="sxs-lookup"><span data-stu-id="5f5e8-141">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
