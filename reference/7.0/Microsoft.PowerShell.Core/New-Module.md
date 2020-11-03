---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: a0d0e31e9010c5ee119b4fbe5f6a877ebc4dc1d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226297"
---
# <span data-ttu-id="855fb-103">New-Module</span><span class="sxs-lookup"><span data-stu-id="855fb-103">New-Module</span></span>

## <span data-ttu-id="855fb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="855fb-104">SYNOPSIS</span></span>
<span data-ttu-id="855fb-105">Создает новый динамический модуль, который существует только в памяти.</span><span class="sxs-lookup"><span data-stu-id="855fb-105">Creates a new dynamic module that exists only in memory.</span></span>

## <span data-ttu-id="855fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="855fb-106">SYNTAX</span></span>

### <span data-ttu-id="855fb-107">ScriptBlock (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="855fb-107">ScriptBlock (Default)</span></span>

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="855fb-108">name</span><span class="sxs-lookup"><span data-stu-id="855fb-108">Name</span></span>

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="855fb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="855fb-109">DESCRIPTION</span></span>

<span data-ttu-id="855fb-110">`New-Module`Командлет создает динамический модуль из блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="855fb-110">The `New-Module` cmdlet creates a dynamic module from a script block.</span></span> <span data-ttu-id="855fb-111">Элементы динамического модуля, например функции и переменные, сразу же становятся доступными в рамках сеанса и остаются таковыми до его завершения.</span><span class="sxs-lookup"><span data-stu-id="855fb-111">The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.</span></span>

<span data-ttu-id="855fb-112">Для динамических, как и для статических, модулей командлеты и функции по умолчанию экспортируются, а переменные и псевдонимы — нет.</span><span class="sxs-lookup"><span data-stu-id="855fb-112">Like static modules, by default, the cmdlets and functions in a dynamic module are exported and the variables and aliases are not.</span></span> <span data-ttu-id="855fb-113">Однако можно использовать командлет Export-ModuleMember и параметры, `New-Module` чтобы переопределить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="855fb-113">However, you can use the Export-ModuleMember cmdlet and the parameters of `New-Module` to override the defaults.</span></span>

<span data-ttu-id="855fb-114">**AsCustomObject** `New-Module` Для возврата динамического модуля в качестве пользовательского объекта можно также использовать параметр AsCustomObject.</span><span class="sxs-lookup"><span data-stu-id="855fb-114">You can also use the **AsCustomObject** parameter of `New-Module` to return the dynamic module as a custom object.</span></span> <span data-ttu-id="855fb-115">Элементы модулей, например функции, не импортируются в сеанс, а реализуются в виде методов скриптов пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="855fb-115">The members of the modules, such as functions, are implemented as script methods of the custom object instead of being imported into the session.</span></span>

<span data-ttu-id="855fb-116">Динамические модули существуют только в памяти, а не на диске.</span><span class="sxs-lookup"><span data-stu-id="855fb-116">Dynamic modules exist only in memory, not on disk.</span></span> <span data-ttu-id="855fb-117">Как и элементы всех остальных модулей, элементы динамических модулей выполняются в закрытой области модуля, являющейся дочерней областью глобальной области.</span><span class="sxs-lookup"><span data-stu-id="855fb-117">Like all modules, the members of dynamic modules run in a private module scope that is a child of the global scope.</span></span> <span data-ttu-id="855fb-118">Командлет Get-Module не может получить динамический модуль, но командлет Get-Command может получить экспортированные элементы.</span><span class="sxs-lookup"><span data-stu-id="855fb-118">Get-Module cannot get a dynamic module, but Get-Command can get the exported members.</span></span>

<span data-ttu-id="855fb-119">Чтобы сделать динамический модуль доступным, передайте `Get-Module` `New-Module` команду в командлет Import-Module или передайте объект модуля, который `New-Module` возвращает в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="855fb-119">To make a dynamic module available to `Get-Module`, pipe a `New-Module` command to Import-Module, or pipe the module object that `New-Module` returns to `Import-Module`.</span></span> <span data-ttu-id="855fb-120">Это действие добавляет в список динамический модуль `Get-Module` , но не сохраняет модуль на диск или делает его постоянным.</span><span class="sxs-lookup"><span data-stu-id="855fb-120">This action adds the dynamic module to the `Get-Module` list, but it does not save the module to disk or make it persistent.</span></span>

## <span data-ttu-id="855fb-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="855fb-121">EXAMPLES</span></span>

### <span data-ttu-id="855fb-122">Пример 1. Создание динамического модуля</span><span class="sxs-lookup"><span data-stu-id="855fb-122">Example 1: Create a dynamic module</span></span>

<span data-ttu-id="855fb-123">В этом примере создается новый динамический модуль с именем функции `Hello` .</span><span class="sxs-lookup"><span data-stu-id="855fb-123">This example creates a new dynamic module with a function called `Hello`.</span></span> <span data-ttu-id="855fb-124">Команда возвращает объект модуля, представляющий новый динамический модуль.</span><span class="sxs-lookup"><span data-stu-id="855fb-124">The command returns a module object that represents the new dynamic module.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### <span data-ttu-id="855fb-125">Пример 2. Работа с динамическими модулями, Get-Module и Get-Command</span><span class="sxs-lookup"><span data-stu-id="855fb-125">Example 2: Working with dynamic modules and Get-Module and Get-Command</span></span>

<span data-ttu-id="855fb-126">В этом примере показано, что динамические модули не возвращаются `Get-Module` командлетом.</span><span class="sxs-lookup"><span data-stu-id="855fb-126">This example demonstrates that dynamic modules are not returned by the `Get-Module` cmdlet.</span></span> <span data-ttu-id="855fb-127">Члены, которые они экспортируют, возвращаются `Get-Command` командлетом.</span><span class="sxs-lookup"><span data-stu-id="855fb-127">The members that they export are returned by the `Get-Command` cmdlet.</span></span>

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### <span data-ttu-id="855fb-128">Пример 3. экспорт переменной в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="855fb-128">Example 3: Export a variable into the current session</span></span>

<span data-ttu-id="855fb-129">В этом примере `Export-ModuleMember` командлет используется для экспорта переменной в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="855fb-129">This example uses the `Export-ModuleMember` cmdlet to export a variable into the current session.</span></span>
<span data-ttu-id="855fb-130">Без `Export-ModuleMember` команды экспортируется только функция.</span><span class="sxs-lookup"><span data-stu-id="855fb-130">Without the `Export-ModuleMember` command, only the function is exported.</span></span>

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

<span data-ttu-id="855fb-131">В выходных данных показано, что в сеанс были экспортированы и переменная, и функция.</span><span class="sxs-lookup"><span data-stu-id="855fb-131">The output shows that both the variable and the function were exported into the session.</span></span>

### <span data-ttu-id="855fb-132">Пример 4. предоставление доступа к динамическому модулю для Get-Module</span><span class="sxs-lookup"><span data-stu-id="855fb-132">Example 4: Make a dynamic module available to Get-Module</span></span>

<span data-ttu-id="855fb-133">В этом примере показано, как можно сделать динамический модуль доступным `Get-Module` по конвейеру динамического модуля в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="855fb-133">This example demonstrates that you can make a dynamic module available to `Get-Module` by piping the dynamic module to `Import-Module`.</span></span>

<span data-ttu-id="855fb-134">`New-Module` Создает объект модуля, который передается в `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="855fb-134">`New-Module` creates a module object that is piped to the `Import-Module` cmdlet.</span></span> <span data-ttu-id="855fb-135">Параметр **Name** объекта `New-Module` присваивает понятное имя модулю.</span><span class="sxs-lookup"><span data-stu-id="855fb-135">The **Name** parameter of `New-Module` assigns a friendly name to the module.</span></span> <span data-ttu-id="855fb-136">Поскольку `Import-Module` по умолчанию не возвращает никаких объектов, выходные данные этой команды отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="855fb-136">Because `Import-Module` does not return any objects by default, there is no output from this command.</span></span> <span data-ttu-id="855fb-137">`Get-Module` , что **гритингмодуле** был импортирован в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="855fb-137">`Get-Module` that the **GreetingModule** has been imported into the current session.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

<span data-ttu-id="855fb-138">`Get-Command`Командлет показывает `Hello` функцию, экспортируемую динамическим модулем.</span><span class="sxs-lookup"><span data-stu-id="855fb-138">The `Get-Command` cmdlet shows the `Hello` function that the dynamic module exports.</span></span>

### <span data-ttu-id="855fb-139">Пример 5. Создание пользовательского объекта, который содержит экспортированные функции</span><span class="sxs-lookup"><span data-stu-id="855fb-139">Example 5: Generate a custom object that has exported functions</span></span>

<span data-ttu-id="855fb-140">В этом примере показано, как использовать параметр **AsCustomObject** метода `New-Module` для создания пользовательского объекта, который содержит методы скрипта, представляющие экспортированные функции.</span><span class="sxs-lookup"><span data-stu-id="855fb-140">This example shows how to use the **AsCustomObject** parameter of `New-Module` to generate a custom object that has script methods that represent the exported functions.</span></span>

<span data-ttu-id="855fb-141">`New-Module`Командлет создает динамический модуль с двумя функциями `Hello` и `Goodbye` .</span><span class="sxs-lookup"><span data-stu-id="855fb-141">The `New-Module` cmdlet creates a dynamic module with two functions, `Hello` and `Goodbye`.</span></span> <span data-ttu-id="855fb-142">Параметр **AsCustomObject** создает пользовательский объект вместо объекта **PSModuleInfo** , который `New-Module` создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="855fb-142">The **AsCustomObject** parameter creates a custom object instead of the **PSModuleInfo** object that `New-Module` generates by default.</span></span> <span data-ttu-id="855fb-143">Этот пользовательский объект сохраняется в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="855fb-143">This custom object is saved in the `$m` variable.</span></span>
<span data-ttu-id="855fb-144">`$m`Переменная, по видимому, не имеет присвоенного значения.</span><span class="sxs-lookup"><span data-stu-id="855fb-144">The `$m` variable appears to have no assigned value.</span></span>

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

<span data-ttu-id="855fb-145">Передача по конвейеру в `$m` `Get-Member` командлет отображает свойства и методы пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="855fb-145">Piping `$m` to the `Get-Member` cmdlet displays the properties and methods of the custom object.</span></span> <span data-ttu-id="855fb-146">Выходные данные показывают, что объект содержит методы скрипта, представляющие `Hello` `Goodbye` функции и.</span><span class="sxs-lookup"><span data-stu-id="855fb-146">The output shows that the object has script methods that represent the `Hello` and `Goodbye` functions.</span></span>
<span data-ttu-id="855fb-147">Наконец, мы вызываем эти методы скрипта и отображаем результаты.</span><span class="sxs-lookup"><span data-stu-id="855fb-147">Finally, we call these script methods and display the results.</span></span>

### <span data-ttu-id="855fb-148">Пример 6. получение результатов блока Script</span><span class="sxs-lookup"><span data-stu-id="855fb-148">Example 6: Get the results of the script block</span></span>

<span data-ttu-id="855fb-149">В этом примере используется параметр **ReturnResult** для запроса результатов выполнения блока сценария вместо запроса объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="855fb-149">This example uses the **ReturnResult** parameter to request the results of running the script block instead of requesting a module object.</span></span> <span data-ttu-id="855fb-150">Блок скрипта в новом модуле определяет `SayHello` функцию, а затем вызывает функцию.</span><span class="sxs-lookup"><span data-stu-id="855fb-150">The script block in the new module defines the `SayHello` function and then calls the function.</span></span>

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## <span data-ttu-id="855fb-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="855fb-151">PARAMETERS</span></span>

### <span data-ttu-id="855fb-152">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="855fb-152">-ArgumentList</span></span>

<span data-ttu-id="855fb-153">Задает массив аргументов, которые являются значениями параметров, передаваемыми в блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="855fb-153">Specifies an array of arguments which are parameter values that are passed to the script block.</span></span> <span data-ttu-id="855fb-154">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="855fb-154">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-155">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="855fb-155">-AsCustomObject</span></span>

<span data-ttu-id="855fb-156">Указывает, что этот командлет возвращает пользовательский объект, представляющий динамический модуль.</span><span class="sxs-lookup"><span data-stu-id="855fb-156">Indicates that this cmdlet returns a custom object that represents the dynamic module.</span></span> <span data-ttu-id="855fb-157">Элементы модуля не импортируются в сеанс, а реализуются в виде методов скриптов пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="855fb-157">The module members are implemented as script methods of the custom object, but they are not imported into the session.</span></span> <span data-ttu-id="855fb-158">Пользовательский объект можно сохранить в переменную и использовать точку для вызова элементов.</span><span class="sxs-lookup"><span data-stu-id="855fb-158">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

<span data-ttu-id="855fb-159">Если модуль содержит несколько членов с одинаковым именем, например функцию и переменную с именем A, доступ к одному элементу с каждым именем можно получить из пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="855fb-159">If the module has multiple members with the same name, such as a function and a variable that are both named A, only one member with each name can be accessed from the custom object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-160">Командлет</span><span class="sxs-lookup"><span data-stu-id="855fb-160">-Cmdlet</span></span>

<span data-ttu-id="855fb-161">Указывает массив командлетов, которые этот командлет экспортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="855fb-161">Specifies an array of cmdlets that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="855fb-162">Введите список командлетов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="855fb-162">Enter a comma-separated list of cmdlets.</span></span> <span data-ttu-id="855fb-163">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="855fb-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="855fb-164">По умолчанию экспортируются все командлеты в модуле.</span><span class="sxs-lookup"><span data-stu-id="855fb-164">By default, all cmdlets in the module are exported.</span></span>

<span data-ttu-id="855fb-165">В блоке скрипта определять командлеты нельзя, однако, динамический модуль может включать командлеты, если импортирует их из двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="855fb-165">You cannot define cmdlets in a script block, but a dynamic module can include cmdlets if it imports the cmdlets from a binary module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-166">-Function</span><span class="sxs-lookup"><span data-stu-id="855fb-166">-Function</span></span>

<span data-ttu-id="855fb-167">Указывает массив функций, которые этот командлет экспортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="855fb-167">Specifies an array of functions that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="855fb-168">Введите список функций, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="855fb-168">Enter a comma-separated list of functions.</span></span> <span data-ttu-id="855fb-169">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="855fb-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="855fb-170">По умолчанию экспортируются все определенные в модуле функции.</span><span class="sxs-lookup"><span data-stu-id="855fb-170">By default, all functions defined in a module are exported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="855fb-171">-Name</span><span class="sxs-lookup"><span data-stu-id="855fb-171">-Name</span></span>

<span data-ttu-id="855fb-172">Задает имя нового модуля.</span><span class="sxs-lookup"><span data-stu-id="855fb-172">Specifies a name for the new module.</span></span> <span data-ttu-id="855fb-173">Имя модуля можно также передать в командлет New-Module по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="855fb-173">You can also pipe a module name to New-Module.</span></span>

<span data-ttu-id="855fb-174">Значение по умолчанию — это автоматически сформированное имя, которое начинается с `__DynamicModule_` и за которым следует идентификатор GUID, указывающий путь к динамическому модулю.</span><span class="sxs-lookup"><span data-stu-id="855fb-174">The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that specifies the path of the dynamic module.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-175">-ReturnResult</span><span class="sxs-lookup"><span data-stu-id="855fb-175">-ReturnResult</span></span>

<span data-ttu-id="855fb-176">Указывает, что этот командлет запускает блок скрипта и возвращает результаты блока сценария вместо возврата объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="855fb-176">Indicates that this cmdlet runs the script block and returns the script block results instead of returning a module object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-177">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="855fb-177">-ScriptBlock</span></span>

<span data-ttu-id="855fb-178">Задает содержимое динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="855fb-178">Specifies the contents of the dynamic module.</span></span> <span data-ttu-id="855fb-179">Заключите содержимое в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="855fb-179">Enclose the contents in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="855fb-180">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="855fb-180">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="855fb-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="855fb-181">CommonParameters</span></span>

<span data-ttu-id="855fb-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="855fb-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="855fb-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="855fb-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="855fb-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="855fb-184">INPUTS</span></span>

### <span data-ttu-id="855fb-185">System.String</span><span class="sxs-lookup"><span data-stu-id="855fb-185">System.String</span></span>

<span data-ttu-id="855fb-186">Имя модуля можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="855fb-186">You can pipe a module name to this cmdlet.</span></span>

## <span data-ttu-id="855fb-187">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="855fb-187">OUTPUTS</span></span>

### <span data-ttu-id="855fb-188">System. Management. Automation. PSModuleInfo, System. Management. Automation. PSCustomObject или None</span><span class="sxs-lookup"><span data-stu-id="855fb-188">System.Management.Automation.PSModuleInfo, System.Management.Automation.PSCustomObject, or None</span></span>

<span data-ttu-id="855fb-189">По умолчанию этот командлет создает объект **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="855fb-189">This cmdlet generates a **PSModuleInfo** object, by default.</span></span> <span data-ttu-id="855fb-190">При использовании параметра **AsCustomObject** создается объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="855fb-190">If you use the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span> <span data-ttu-id="855fb-191">Если вы используете параметр **ReturnResult** , он возвращает результат вычисления блока скрипта в динамическом модуле.</span><span class="sxs-lookup"><span data-stu-id="855fb-191">If you use the **ReturnResult** parameter, it returns the result of evaluating the script block in the dynamic module.</span></span>

## <span data-ttu-id="855fb-192">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="855fb-192">NOTES</span></span>

<span data-ttu-id="855fb-193">Также можно ссылаться `New-Module` по его псевдониму, `nmo` .</span><span class="sxs-lookup"><span data-stu-id="855fb-193">You can also refer to `New-Module` by its alias, `nmo`.</span></span> <span data-ttu-id="855fb-194">Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="855fb-194">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="855fb-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="855fb-195">RELATED LINKS</span></span>

[<span data-ttu-id="855fb-196">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="855fb-196">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="855fb-197">Get-Module</span><span class="sxs-lookup"><span data-stu-id="855fb-197">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="855fb-198">Import-Module</span><span class="sxs-lookup"><span data-stu-id="855fb-198">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="855fb-199">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="855fb-199">Remove-Module</span></span>](Remove-Module.md)
