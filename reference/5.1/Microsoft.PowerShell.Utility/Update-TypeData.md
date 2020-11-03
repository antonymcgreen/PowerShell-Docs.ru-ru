---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: eb7bafff1af34ef34a1b67c1fbe8f9e2db0ca7ad
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227474"
---
# <span data-ttu-id="df1a5-103">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="df1a5-103">Update-TypeData</span></span>

## <span data-ttu-id="df1a5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="df1a5-104">Synopsis</span></span>
<span data-ttu-id="df1a5-105">Обновляет данные расширенного типа во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="df1a5-105">Updates the extended type data in the session.</span></span>

## <span data-ttu-id="df1a5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df1a5-106">Syntax</span></span>

### <span data-ttu-id="df1a5-107">FileSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="df1a5-107">FileSet (Default)</span></span>

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="df1a5-108">DynamicTypeSet</span><span class="sxs-lookup"><span data-stu-id="df1a5-108">DynamicTypeSet</span></span>

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="df1a5-109">TypeDataSet</span><span class="sxs-lookup"><span data-stu-id="df1a5-109">TypeDataSet</span></span>

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="df1a5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="df1a5-110">Description</span></span>

<span data-ttu-id="df1a5-111">`Update-TypeData`Командлет обновляет данные расширенного типа в сеансе путем перезагрузки `Types.ps1xml` файлов в память и добавления новых данных расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-111">The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.</span></span>

<span data-ttu-id="df1a5-112">По умолчанию PowerShell загружает данные расширенного типа по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="df1a5-112">By default, PowerShell loads extended type data as it is needed.</span></span> <span data-ttu-id="df1a5-113">Без параметров `Update-TypeData` перезагружает все `Types.ps1xml` файлы, загруженные в сеанс, включая все добавленные файлы типов.</span><span class="sxs-lookup"><span data-stu-id="df1a5-113">Without parameters, `Update-TypeData` reloads all of the `Types.ps1xml` files that it has loaded in the session, including any type files that you added.</span></span> <span data-ttu-id="df1a5-114">С помощью параметров можно `Update-TypeData` добавлять новые файлы типов, а также добавлять и заменять данные расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-114">You can use the parameters of `Update-TypeData` to add new type files and add and replace extended type data.</span></span>

<span data-ttu-id="df1a5-115">`Update-TypeData`Командлет можно использовать для предварительной загрузки всех данных типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-115">The `Update-TypeData` cmdlet can be used to preload all type data.</span></span> <span data-ttu-id="df1a5-116">Эта функция особенно полезна при разработке собственных типов, так как позволяет загружать их для тестирования.</span><span class="sxs-lookup"><span data-stu-id="df1a5-116">This feature is particularly useful when you are developing types and want to load those new types for testing purposes.</span></span>

<span data-ttu-id="df1a5-117">Начиная с Windows PowerShell 3,0, можно использовать `Update-TypeData` для добавления и замены данных расширенного типа в сеансе без использования `Types.ps1xml` файла.</span><span class="sxs-lookup"><span data-stu-id="df1a5-117">Beginning in Windows PowerShell 3.0, you can use `Update-TypeData` to add and replace extended type data in the session without using a `Types.ps1xml` file.</span></span> <span data-ttu-id="df1a5-118">Данные типа, добавленные динамически, то есть без помощи файла, добавляются только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="df1a5-118">Type data that is added dynamically, that is, without a file, is added only to the current session.</span></span> <span data-ttu-id="df1a5-119">Чтобы добавить данные типа во все сеансы, добавьте `Update-TypeData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df1a5-119">To add the type data to all sessions, add an `Update-TypeData` command to your PowerShell profile.</span></span> <span data-ttu-id="df1a5-120">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="df1a5-120">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="df1a5-121">Кроме того, начиная с Windows PowerShell 3,0, командлет можно использовать `Get-TypeData` для получения расширенных типов в текущем сеансе и `Remove-TypeData` командлета для удаления расширенных типов из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="df1a5-121">Also, beginning in Windows PowerShell 3.0, you can use the `Get-TypeData` cmdlet to get the extended types in the current session and the `Remove-TypeData` cmdlet to delete extended types from the current session.</span></span>

<span data-ttu-id="df1a5-122">Исключения, возникающие в свойствах или при добавлении свойств в `Update-TypeData` команду, не сообщают об ошибках.</span><span class="sxs-lookup"><span data-stu-id="df1a5-122">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors.</span></span> <span data-ttu-id="df1a5-123">Это необходимо для подавления исключений, которые могут возникнуть во многих распространенных типах в процессе форматирования и вывода.</span><span class="sxs-lookup"><span data-stu-id="df1a5-123">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="df1a5-124">Если вы получаете свойства .NET, подавление исключений можно обойти с помощью синтаксиса метода, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df1a5-124">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

`"hello".get_Length()`

<span data-ttu-id="df1a5-125">Обратите внимание, что синтаксис метода можно использовать только со свойствами .NET.</span><span class="sxs-lookup"><span data-stu-id="df1a5-125">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="df1a5-126">Свойства, которые добавляются путем запуска `Update-TypeData` командлета, не могут использовать синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="df1a5-126">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

<span data-ttu-id="df1a5-127">Дополнительные сведения о `Types.ps1xml` файлах в PowerShell см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="df1a5-127">For more information about the `Types.ps1xml` files in PowerShell, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

## <span data-ttu-id="df1a5-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="df1a5-128">Examples</span></span>

### <span data-ttu-id="df1a5-129">Пример 1. обновление расширенных типов</span><span class="sxs-lookup"><span data-stu-id="df1a5-129">Example 1: Update extended types</span></span>

```powershell
Update-TypeData
```

<span data-ttu-id="df1a5-130">Эта команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, которые уже использовались в сеансе.</span><span class="sxs-lookup"><span data-stu-id="df1a5-130">This command updates the extended type configuration from the `Types.ps1xml` files that have already been used in the session.</span></span>

### <span data-ttu-id="df1a5-131">Пример 2. Обновление типов несколько раз</span><span class="sxs-lookup"><span data-stu-id="df1a5-131">Example 2: Update types multiple times</span></span>

<span data-ttu-id="df1a5-132">В этом примере показано, как обновить типы в файле типа несколько раз в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="df1a5-132">This example shows how to update the types in a type file multiple times in the same session.</span></span>

<span data-ttu-id="df1a5-133">Первая команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, сначала обрабатывая `TypesA.types.ps1xml` файлы и `TypesB.types.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-133">The first command updates the extended type configuration from the `Types.ps1xml` files, processing the `TypesA.types.ps1xml` and `TypesB.types.ps1xml` files first.</span></span>

<span data-ttu-id="df1a5-134">Вторая команда показывает `TypesA.types.ps1xml` , как выполнить повторное обновление, например, если вы добавили или изменили тип в файле.</span><span class="sxs-lookup"><span data-stu-id="df1a5-134">The second command shows how to update the `TypesA.types.ps1xml` again, such as you might do if you added or changed a type in the file.</span></span> <span data-ttu-id="df1a5-135">Можно либо повторить предыдущую команду для `TypesA.types.ps1xml` файла, либо выполнить `Update-TypeData` команду без параметров, поскольку `TypesA.types.ps1xml` уже существует в списке файлов типов для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="df1a5-135">You can either repeat the previous command for the `TypesA.types.ps1xml` file, or run an `Update-TypeData` command without parameters, because `TypesA.types.ps1xml` is already in the type file list for the current session.</span></span>

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### <span data-ttu-id="df1a5-136">Пример 3. Добавление свойства скрипта в объекты DateTime</span><span class="sxs-lookup"><span data-stu-id="df1a5-136">Example 3: Add a script property to DateTime objects</span></span>

<span data-ttu-id="df1a5-137">В этом примере используется `Update-TypeData` для добавления свойства сценария **Quarter** в объекты **System. DateTime** в текущем сеансе, например, возвращаемые `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="df1a5-137">This example uses `Update-TypeData` to add the **Quarter** script property to **System.DateTime** objects in the current session, such as those returned by the `Get-Date` cmdlet.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

<span data-ttu-id="df1a5-138">`Update-TypeData`Команда использует параметр **TypeName** для указания типа **System. DateTime** , параметр **MemberName** для указания имени нового свойства, свойство **MemberType** для указания типа **ScriptProperty** , а параметр **value** — для указания скрипта, определяющего ежегодный квартал.</span><span class="sxs-lookup"><span data-stu-id="df1a5-138">The `Update-TypeData` command uses the **TypeName** parameter to specify **the System.DateTime** type, the **MemberName** parameter to specify a name for the new property, the **MemberType** property to specify the **ScriptProperty** type, and the **Value** parameter to specify the script that determines the annual quarter.</span></span>

<span data-ttu-id="df1a5-139">Значение свойства **Value**  — это сценарий, вычисляющий текущий годовой квартал.</span><span class="sxs-lookup"><span data-stu-id="df1a5-139">The value of the **Value** property is a script that calculates the current annual quarter.</span></span> <span data-ttu-id="df1a5-140">Блок скрипта использует `$this` автоматическую переменную для представления текущего экземпляра объекта и оператор in для определения того, отображается ли значение месяца в каждом массиве целых чисел.</span><span class="sxs-lookup"><span data-stu-id="df1a5-140">The script block uses the `$this` automatic variable to represent the current instance of the object and the In operator to determine whether the month value appears in each integer array.</span></span> <span data-ttu-id="df1a5-141">Дополнительные сведения об `-in` операторе см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="df1a5-141">For more information about the `-in` operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span></span>

<span data-ttu-id="df1a5-142">Вторая команда возвращает новое свойство Quarter текущей даты.</span><span class="sxs-lookup"><span data-stu-id="df1a5-142">The second command gets the new Quarter property of the current date.</span></span>

### <span data-ttu-id="df1a5-143">Пример 4. Обновление типа, который по умолчанию отображает в списках</span><span class="sxs-lookup"><span data-stu-id="df1a5-143">Example 4: Update a type that displays in lists by default</span></span>

<span data-ttu-id="df1a5-144">В этом примере показано, как задать свойства типа, который по умолчанию отображает в списках, то есть если свойства не заданы.</span><span class="sxs-lookup"><span data-stu-id="df1a5-144">This example shows how to set the properties of a type that displays in lists by default, that is, when no properties are specified.</span></span> <span data-ttu-id="df1a5-145">Поскольку данные типа не указываются в `Types.ps1xml` файле, они вступают в силу только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="df1a5-145">Because the type data is not specified in a `Types.ps1xml` file, it is effective only in the current session.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

<span data-ttu-id="df1a5-146">Первая команда использует `Update-TypeData` командлет для задания свойств списка по умолчанию для типа **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-146">The first command uses the `Update-TypeData` cmdlet to set the default list properties for the **System.DateTime** type.</span></span> <span data-ttu-id="df1a5-147">С помощью параметра **TypeName** она определяет тип, а с помощью параметра **DefaultDisplayPropertySet**  — свойства списка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="df1a5-147">The command uses the **TypeName** parameter to specify the type and the **DefaultDisplayPropertySet** parameter to specify the default properties for a list.</span></span> <span data-ttu-id="df1a5-148">Выбранные свойства включают новое свойство **четвертого** сценария, добавленное в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="df1a5-148">The selected properties include the new **Quarter** script property that was added in a previous example.</span></span>

<span data-ttu-id="df1a5-149">Вторая команда использует `Get-Date` командлет для получения объекта **System. DateTime** , представляющего текущую дату.</span><span class="sxs-lookup"><span data-stu-id="df1a5-149">The second command uses the `Get-Date` cmdlet to get a **System.DateTime** object that represents the current date.</span></span> <span data-ttu-id="df1a5-150">Команда использует оператор конвейера ( `|` ) для отправки объекта **DateTime** в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="df1a5-150">The command uses a pipeline operator (`|`) to send the **DateTime** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="df1a5-151">Поскольку `Format-List` команда не указывает свойства, которые должны отображаться в списке, PowerShell использует значения по умолчанию, установленные `Update-TypeData` командой.</span><span class="sxs-lookup"><span data-stu-id="df1a5-151">Because the `Format-List` command does not specify the properties to display in the list, PowerShell uses the default values that were established by the `Update-TypeData` command.</span></span>

### <span data-ttu-id="df1a5-152">Пример 5. обновление данных типа для поконвейерного объекта</span><span class="sxs-lookup"><span data-stu-id="df1a5-152">Example 5: Update type data for a piped object</span></span>

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

<span data-ttu-id="df1a5-153">В этом примере показано, что при передаче объекта в `Update-TypeData` объект `Update-TypeData` добавляет Расширенные данные типа для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="df1a5-153">This example demonstrates that when you pipe an object to `Update-TypeData`, `Update-TypeData` adds extended type data for the object type.</span></span>

<span data-ttu-id="df1a5-154">Этот метод быстрее, чем использование `Get-Member` командлета или `Get-Type` метода для получения типа объекта.</span><span class="sxs-lookup"><span data-stu-id="df1a5-154">This technique is quicker than using the `Get-Member` cmdlet or the `Get-Type` method to get the object type.</span></span> <span data-ttu-id="df1a5-155">Однако при передаче коллекции объектов в `Update-TypeData` объект обновляет данные типа первого типа объектов, а затем возвращает ошибку для всех остальных объектов в коллекции, поскольку этот элемент уже определен в типе.</span><span class="sxs-lookup"><span data-stu-id="df1a5-155">However, if you pipe a collection of objects to `Update-TypeData`, it updates the type data of the first object type and then returns an error for all other objects in the collection because the member is already defined on the type.</span></span>

<span data-ttu-id="df1a5-156">Первая команда использует `Get-Module` командлет для получения модуля PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="df1a5-156">The first command uses the `Get-Module` cmdlet to get the PSScheduledJob module.</span></span> <span data-ttu-id="df1a5-157">Команда передает объект Module в `Update-TypeData` командлет, который обновляет данные типа для типа **System. Management. Automation. PSModuleInfo** и производных от него типов, например тип модулеинфограупинг, `Get-Module` возвращаемый при использовании параметра **ListAvailable** в команде.</span><span class="sxs-lookup"><span data-stu-id="df1a5-157">The command pipes the module object to the `Update-TypeData` cmdlet, which updates the type data for the **System.Management.Automation.PSModuleInfo** type and the types derived from it, such as the ModuleInfoGrouping type that `Get-Module` returns when you use the **ListAvailable** parameter in the command.</span></span>

<span data-ttu-id="df1a5-158">`Update-TypeData`Команды добавляют свойство скрипта **SupportsUpdatableHelp** во все импортированные модули.</span><span class="sxs-lookup"><span data-stu-id="df1a5-158">The `Update-TypeData` commands adds the **SupportsUpdatableHelp** script property to all imported modules.</span></span> <span data-ttu-id="df1a5-159">Значением параметра **value** является скрипт, который возвращает значение, `$True` Если свойство **HelpInfoUri** модуля заполнено и `$False` в противном случае —.</span><span class="sxs-lookup"><span data-stu-id="df1a5-159">The value of the **Value** parameter is a script that returns `$True` if the **HelpInfoUri** property of the module is populated and `$False` otherwise.</span></span>

<span data-ttu-id="df1a5-160">Вторая команда передает объекты модуля из `Get-Module` в `Format-Table` командлет, который отображает свойства **Name** и **SupportsUpdatableHelp** всех модулей в списке.</span><span class="sxs-lookup"><span data-stu-id="df1a5-160">The second command pipes the module objects from `Get-Module` to the `Format-Table` cmdlet, which displays the **Name** and **SupportsUpdatableHelp** properties of all modules in a list.</span></span>

## <span data-ttu-id="df1a5-161">Параметры</span><span class="sxs-lookup"><span data-stu-id="df1a5-161">Parameters</span></span>

### <span data-ttu-id="df1a5-162">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="df1a5-162">-AppendPath</span></span>

<span data-ttu-id="df1a5-163">Указывает путь к необязательным `.ps1xml` файлам.</span><span class="sxs-lookup"><span data-stu-id="df1a5-163">Specifies the path to optional `.ps1xml` files.</span></span> <span data-ttu-id="df1a5-164">Эти файлы загружаются в том порядке, в котором они были указаны, после загрузки встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="df1a5-164">The specified files are loaded in the order that they are listed after the built-in files are loaded.</span></span> <span data-ttu-id="df1a5-165">Можно также передать значение **AppendPath** в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-165">You can also pipe an **AppendPath** value to `Update-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-166">-DefaultDisplayProperty</span><span class="sxs-lookup"><span data-stu-id="df1a5-166">-DefaultDisplayProperty</span></span>

<span data-ttu-id="df1a5-167">Указывает свойство типа, отображаемое `Format-Wide` командлетом, если другие свойства не указаны.</span><span class="sxs-lookup"><span data-stu-id="df1a5-167">Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="df1a5-168">Введите имя стандартного или расширенного свойства типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-168">Type the name of a standard or extended property of the type.</span></span> <span data-ttu-id="df1a5-169">В качестве значения этого параметра может выступать имя типа, добавленного в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="df1a5-169">The value of this parameter can be the name of a type that is added in the same command.</span></span>

<span data-ttu-id="df1a5-170">Это значение вступает в силу только в том случае, если для типа в файле не определены широкие представления `Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-170">This value is effective only when there are no wide views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="df1a5-171">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-171">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-172">-DefaultDisplayPropertySet</span><span class="sxs-lookup"><span data-stu-id="df1a5-172">-DefaultDisplayPropertySet</span></span>

<span data-ttu-id="df1a5-173">Определяет одно или несколько свойств типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-173">Specifies one or more properties of the type.</span></span> <span data-ttu-id="df1a5-174">Эти свойства отображаются `Format-List` командлетом, если не заданы другие свойства.</span><span class="sxs-lookup"><span data-stu-id="df1a5-174">These properties are displayed by the `Format-List` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="df1a5-175">Введите имена стандартных или расширенных свойств типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-175">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="df1a5-176">В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="df1a5-176">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="df1a5-177">Это значение вступает в силу только при отсутствии представлений списков, определенных для типа в `Format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="df1a5-177">This value is effective only when there are no list views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="df1a5-178">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-178">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-179">-DefaultKeyPropertySet</span><span class="sxs-lookup"><span data-stu-id="df1a5-179">-DefaultKeyPropertySet</span></span>

<span data-ttu-id="df1a5-180">Определяет одно или несколько свойств типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-180">Specifies one or more properties of the type.</span></span> <span data-ttu-id="df1a5-181">Эти свойства используются `Group-Object` командлетами и, `Sort-Object` если другие свойства не указаны.</span><span class="sxs-lookup"><span data-stu-id="df1a5-181">These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.</span></span>

<span data-ttu-id="df1a5-182">Введите имена стандартных или расширенных свойств типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-182">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="df1a5-183">В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="df1a5-183">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="df1a5-184">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-184">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-185">-Force</span><span class="sxs-lookup"><span data-stu-id="df1a5-185">-Force</span></span>

<span data-ttu-id="df1a5-186">Указывает, что командлет использует указанные данные типа, даже если данные типа уже указаны для этого типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-186">Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.</span></span>

<span data-ttu-id="df1a5-187">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-187">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-188">-InheritPropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="df1a5-188">-InheritPropertySerializationSet</span></span>

<span data-ttu-id="df1a5-189">Указывает, унаследован ли набор сериализованных свойств.</span><span class="sxs-lookup"><span data-stu-id="df1a5-189">Indicates whether the set of properties that are serialized is inherited.</span></span> <span data-ttu-id="df1a5-190">Значение по умолчанию — `$Null`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-190">The default value is `$Null`.</span></span> <span data-ttu-id="df1a5-191">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="df1a5-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df1a5-192">`$True`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-192">`$True`.</span></span> <span data-ttu-id="df1a5-193">набор свойств наследуется.</span><span class="sxs-lookup"><span data-stu-id="df1a5-193">The property set is inherited.</span></span>
- <span data-ttu-id="df1a5-194">`$False`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-194">`$False`.</span></span> <span data-ttu-id="df1a5-195">набор свойств не наследуется.</span><span class="sxs-lookup"><span data-stu-id="df1a5-195">The property set is not inherited.</span></span>
- <span data-ttu-id="df1a5-196">`$Null`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-196">`$Null`.</span></span> <span data-ttu-id="df1a5-197">наследование не определено.</span><span class="sxs-lookup"><span data-stu-id="df1a5-197">Inheritance is not defined.</span></span>

<span data-ttu-id="df1a5-198">Этот параметр допустим только в том случае, если значение параметра **метод serializationmethod** равно `SpecificProperties` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-198">This parameter is valid only when the value of the **SerializationMethod** parameter is `SpecificProperties`.</span></span> <span data-ttu-id="df1a5-199">Если значение этого параметра равно `$False` , параметр **пропертисериализатионсет** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="df1a5-199">When the value of this parameter is `$False`, the **PropertySerializationSet** parameter is required.</span></span>

<span data-ttu-id="df1a5-200">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="df1a5-201">-MemberName</span></span>

<span data-ttu-id="df1a5-202">Определяет имя свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="df1a5-202">Specifies the name of a property or method.</span></span>

<span data-ttu-id="df1a5-203">Вместе с параметрами **TypeName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-203">Use this parameter with the **TypeName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="df1a5-204">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-205">-MemberType</span><span class="sxs-lookup"><span data-stu-id="df1a5-205">-MemberType</span></span>

<span data-ttu-id="df1a5-206">Определяет тип элемента для добавления или изменения.</span><span class="sxs-lookup"><span data-stu-id="df1a5-206">Specifies the type of the member to add or change.</span></span>

<span data-ttu-id="df1a5-207">Вместе с параметрами **TypeName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-207">Use this parameter with the **TypeName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span> <span data-ttu-id="df1a5-208">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="df1a5-208">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df1a5-209">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="df1a5-209">AliasProperty</span></span>
- <span data-ttu-id="df1a5-210">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="df1a5-210">CodeMethod</span></span>
- <span data-ttu-id="df1a5-211">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="df1a5-211">CodeProperty</span></span>
- <span data-ttu-id="df1a5-212">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="df1a5-212">Noteproperty</span></span>
- <span data-ttu-id="df1a5-213">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="df1a5-213">ScriptMethod</span></span>
- <span data-ttu-id="df1a5-214">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="df1a5-214">ScriptProperty</span></span>

<span data-ttu-id="df1a5-215">Дополнительные сведения об этих значениях см. в разделе [Псмембертипес enumeration](/dotnet/api/system.management.automation.psmembertypes).</span><span class="sxs-lookup"><span data-stu-id="df1a5-215">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="df1a5-216">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-217">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="df1a5-217">-PrependPath</span></span>

<span data-ttu-id="df1a5-218">Указывает путь к необязательным `.ps1xml` файлам.</span><span class="sxs-lookup"><span data-stu-id="df1a5-218">Specifies the path to the optional `.ps1xml` files.</span></span> <span data-ttu-id="df1a5-219">Эти файлы загружаются в том порядке, в котором они были указаны, до загрузки встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="df1a5-219">The specified files are loaded in the order that they are listed before the built-in files are loaded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-220">-PropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="df1a5-220">-PropertySerializationSet</span></span>

<span data-ttu-id="df1a5-221">Определяет имена сериализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="df1a5-221">Specifies the names of properties that are serialized.</span></span> <span data-ttu-id="df1a5-222">Используйте этот параметр, если параметр **SerializationMethod** имеет значение **SpecificProperties** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-222">Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-223">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="df1a5-223">-SecondValue</span></span>

<span data-ttu-id="df1a5-224">Определяет дополнительные значения для элементов **AliasProperty** , **ScriptProperty** , **CodeProperty** , или **CodeMethod** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-224">Specifies additional values for **AliasProperty** , **ScriptProperty** , **CodeProperty** , or **CodeMethod** members.</span></span>

<span data-ttu-id="df1a5-225">Используйте этот параметр с параметрами **TypeName** , **MemberType** , **value** и **SecondValue** для добавления или изменения свойства или метода типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-225">Use this parameter with the **TypeName** , **MemberType** , **Value** , and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="df1a5-226">Если значение параметра **MemberType** равно `AliasProperty` , значение параметра **SecondValue** должно быть типом данных.</span><span class="sxs-lookup"><span data-stu-id="df1a5-226">When the value of the **MemberType** parameter is `AliasProperty`, the value of the **SecondValue** parameter must be a data type.</span></span> <span data-ttu-id="df1a5-227">PowerShell преобразует значение свойства Alias в указанный тип (то есть приводит).</span><span class="sxs-lookup"><span data-stu-id="df1a5-227">PowerShell converts (that is, casts) the value of the alias property to the specified type.</span></span> <span data-ttu-id="df1a5-228">Например, если добавить свойство Alias, которое предоставляет альтернативное имя для свойства строки, можно также указать **SecondValue** для **System. Int32** , чтобы преобразовать строковое значение с псевдонимом в целое число.</span><span class="sxs-lookup"><span data-stu-id="df1a5-228">For example, if you add an alias property that provides an alternate name for a string property, you can also specify a **SecondValue** of **System.Int32** to convert the aliased string value to an integer.</span></span>

<span data-ttu-id="df1a5-229">Если значение параметра **MemberType** равно `ScriptProperty` , можно использовать параметр **SecondValue** , чтобы указать дополнительный блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="df1a5-229">When the value of the **MemberType** parameter is `ScriptProperty`, you can use the **SecondValue** parameter to specify an additional script block.</span></span> <span data-ttu-id="df1a5-230">Блок скрипта в значении параметра **Value** получает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="df1a5-230">The script block in the value of the **Value** parameter gets the value of a variable.</span></span> <span data-ttu-id="df1a5-231">Блок скрипта в значении параметра **SecondValue** устанавливает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="df1a5-231">The script block in the value of the **SecondValue** parameter set the value of the variable.</span></span>

<span data-ttu-id="df1a5-232">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-233">-SerializationDepth</span><span class="sxs-lookup"><span data-stu-id="df1a5-233">-SerializationDepth</span></span>

<span data-ttu-id="df1a5-234">Определяет, сколько уровней объектов типа будут сериализованы как строки.</span><span class="sxs-lookup"><span data-stu-id="df1a5-234">Specifies how many levels of type objects are serialized as strings.</span></span> <span data-ttu-id="df1a5-235">Значение по умолчанию `1` сериализует объект и его свойства.</span><span class="sxs-lookup"><span data-stu-id="df1a5-235">The default value `1` serializes the object and its properties.</span></span> <span data-ttu-id="df1a5-236">Значение `0` сериализует объект, но не его свойства.</span><span class="sxs-lookup"><span data-stu-id="df1a5-236">A value of `0` serializes the object, but not its properties.</span></span> <span data-ttu-id="df1a5-237">Значение `2` сериализует объект, его свойства и все объекты в значениях свойств.</span><span class="sxs-lookup"><span data-stu-id="df1a5-237">A value of `2` serializes the object, its properties, and any objects in property values.</span></span>

<span data-ttu-id="df1a5-238">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-239">-SerializationMethod</span><span class="sxs-lookup"><span data-stu-id="df1a5-239">-SerializationMethod</span></span>

<span data-ttu-id="df1a5-240">Указывает метод сериализации для типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-240">Specifies a serialization method for the type.</span></span> <span data-ttu-id="df1a5-241">Метод сериализации определяет сериализуемые свойства типа и метод сериализации.</span><span class="sxs-lookup"><span data-stu-id="df1a5-241">A serialization method determines which properties of the type are serialized and the technique that is used to serialize them.</span></span> <span data-ttu-id="df1a5-242">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="df1a5-242">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df1a5-243">`AllPublicProperties`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-243">`AllPublicProperties`.</span></span> <span data-ttu-id="df1a5-244">сериализуются все открытые свойства типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-244">Serialize all public properties of the type.</span></span> <span data-ttu-id="df1a5-245">Можно использовать параметр **SerializationDepth** , позволяющий включить сериализацию дочерних свойств.</span><span class="sxs-lookup"><span data-stu-id="df1a5-245">You can use the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>
- <span data-ttu-id="df1a5-246">`String`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-246">`String`.</span></span> <span data-ttu-id="df1a5-247">типа сериализуется в виде строки.</span><span class="sxs-lookup"><span data-stu-id="df1a5-247">Serialize the type as a string.</span></span> <span data-ttu-id="df1a5-248">Можно использовать параметр **StringSerializationSource** , позволяющий указать свойство типа для использования в результате сериализации.</span><span class="sxs-lookup"><span data-stu-id="df1a5-248">You can use the **StringSerializationSource** to specify a property of the type to use as the serialization result.</span></span> <span data-ttu-id="df1a5-249">В противном случае тип сериализуется с использованием метода объекта **ToString** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-249">Otherwise, the type is serialized by using the **ToString** method of the object.</span></span>
- <span data-ttu-id="df1a5-250">`SpecificProperties`.</span><span class="sxs-lookup"><span data-stu-id="df1a5-250">`SpecificProperties`.</span></span> <span data-ttu-id="df1a5-251">Сериализация только указанных свойств этого типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-251">Serialize only the specified properties of this type.</span></span> <span data-ttu-id="df1a5-252">Параметр **PropertySerializationSet** позволяет указать, какие свойства типа требуют сериализации.</span><span class="sxs-lookup"><span data-stu-id="df1a5-252">Use the **PropertySerializationSet** parameter to specify the properties of the type that are serialized.</span></span>
  <span data-ttu-id="df1a5-253">Можно также использовать параметр **InheritPropertySerializationSet** , определяющий наследование набора свойств, и параметр **SerializationDepth** , определяющий сериализацию дочерних свойств.</span><span class="sxs-lookup"><span data-stu-id="df1a5-253">You can also use the **InheritPropertySerializationSet** parameter to determine whether the property set is inherited and the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>

<span data-ttu-id="df1a5-254">В PowerShell методы сериализации хранятся в внутренних объектах **псстандардмемберс** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-254">In PowerShell, serialization methods are stored in **PSStandardMembers** internal objects.</span></span>

<span data-ttu-id="df1a5-255">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-255">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-256">-StringSerializationSource</span><span class="sxs-lookup"><span data-stu-id="df1a5-256">-StringSerializationSource</span></span>

<span data-ttu-id="df1a5-257">Определяет имя свойства типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-257">Specifies the name of a property of the type.</span></span> <span data-ttu-id="df1a5-258">Значение указанного свойства используется в качестве результате сериализации.</span><span class="sxs-lookup"><span data-stu-id="df1a5-258">The value of specified property is used as the serialization result.</span></span> <span data-ttu-id="df1a5-259">Этот параметр допустим только в том случае, если параметр **метод serializationmethod** имеет значение String.</span><span class="sxs-lookup"><span data-stu-id="df1a5-259">This parameter is valid only when the value of the **SerializationMethod** parameter is String.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-260">-TargetTypeForDeserialization</span><span class="sxs-lookup"><span data-stu-id="df1a5-260">-TargetTypeForDeserialization</span></span>

<span data-ttu-id="df1a5-261">Определяет, в какой типа должны конвертироваться объекты данного типа при десериализации.</span><span class="sxs-lookup"><span data-stu-id="df1a5-261">Specifies the type to which object of this type are converted when they are deserialized.</span></span>

<span data-ttu-id="df1a5-262">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-263">-TypeAdapter</span><span class="sxs-lookup"><span data-stu-id="df1a5-263">-TypeAdapter</span></span>

<span data-ttu-id="df1a5-264">Указывает тип адаптера типа, например **Microsoft. PowerShell. CIM. Циминстанцеадаптер** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-264">Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter** .</span></span> <span data-ttu-id="df1a5-265">Адаптер типов позволяет PowerShell получать члены типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-265">A type adapter enables PowerShell to get the members of a type.</span></span>

<span data-ttu-id="df1a5-266">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-267">-TypeConverter</span><span class="sxs-lookup"><span data-stu-id="df1a5-267">-TypeConverter</span></span>

<span data-ttu-id="df1a5-268">Определяет преобразователь типов для конвертации значений из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="df1a5-268">Specifies a type converter to convert values between different types.</span></span> <span data-ttu-id="df1a5-269">Если для типа определен преобразователь, для конвертации используется экземпляр этого преобразователя.</span><span class="sxs-lookup"><span data-stu-id="df1a5-269">If a type converter is defined for a type, an instance of the type converter is used for the conversion.</span></span>

<span data-ttu-id="df1a5-270">Введите значение **System.Type** , которое является производным от класса **System.ComponentModel.TypeConverter** или **System.Management.Automation.PSTypeConverter** .</span><span class="sxs-lookup"><span data-stu-id="df1a5-270">Enter a **System.Type** value that is derived from the **System.ComponentModel.TypeConverter** or **System.Management.Automation.PSTypeConverter** classes.</span></span>

<span data-ttu-id="df1a5-271">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-272">-TypeData</span><span class="sxs-lookup"><span data-stu-id="df1a5-272">-TypeData</span></span>

<span data-ttu-id="df1a5-273">Указывает массив данных типа, который этот командлет добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="df1a5-273">Specifies an array of type data that this cmdlet adds to the session.</span></span> <span data-ttu-id="df1a5-274">Введите переменную, содержащую объект **TypeData** , или команду, которая получает объект **TypeData** , например `Get-TypeData` команду.</span><span class="sxs-lookup"><span data-stu-id="df1a5-274">Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="df1a5-275">Можно также передать объект **TypeData** в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-275">You can also pipe a **TypeData** object to `Update-TypeData`.</span></span>

<span data-ttu-id="df1a5-276">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-276">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-277">-TypeName</span><span class="sxs-lookup"><span data-stu-id="df1a5-277">-TypeName</span></span>

<span data-ttu-id="df1a5-278">Определяет имя типа для расширения.</span><span class="sxs-lookup"><span data-stu-id="df1a5-278">Specifies the name of the type to extend.</span></span>

<span data-ttu-id="df1a5-279">Для типов в пространстве имен **System** необходимо указывать короткое имя.</span><span class="sxs-lookup"><span data-stu-id="df1a5-279">For types in the **System** namespace, enter the short name.</span></span> <span data-ttu-id="df1a5-280">В остальных случаях требуется полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-280">Otherwise, the full type name is required.</span></span> <span data-ttu-id="df1a5-281">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="df1a5-281">Wildcards are not supported.</span></span>

<span data-ttu-id="df1a5-282">Можно передать имена типов в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-282">You can pipe type names to `Update-TypeData`.</span></span> <span data-ttu-id="df1a5-283">При передаче объекта в `Update-TypeData` `Update-TypeData` возвращает имя типа объекта и тип данных в тип объекта.</span><span class="sxs-lookup"><span data-stu-id="df1a5-283">When you pipe an object to `Update-TypeData`, `Update-TypeData` gets the type name of the object and type data to the object type.</span></span>

<span data-ttu-id="df1a5-284">Вместе с параметрами **MemberName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-284">Use this parameter with the **MemberName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="df1a5-285">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-286">-Value</span><span class="sxs-lookup"><span data-stu-id="df1a5-286">-Value</span></span>

<span data-ttu-id="df1a5-287">Определяет значение свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="df1a5-287">Specifies the value of the property or method.</span></span>

<span data-ttu-id="df1a5-288">При добавлении `AliasProperty` члена,, `CodeProperty` `ScriptProperty` или `CodeMethod` можно использовать параметр **SecondValue** для добавления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="df1a5-288">If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional information.</span></span>

<span data-ttu-id="df1a5-289">Вместе с параметрами **MemberName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="df1a5-289">Use this parameter with the **MemberName** , **MemberType** , **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="df1a5-290">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df1a5-290">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-291">-Confirm</span><span class="sxs-lookup"><span data-stu-id="df1a5-291">-Confirm</span></span>

<span data-ttu-id="df1a5-292">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="df1a5-292">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-293">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="df1a5-293">-WhatIf</span></span>

<span data-ttu-id="df1a5-294">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="df1a5-294">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="df1a5-295">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="df1a5-295">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df1a5-296">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="df1a5-296">CommonParameters</span></span>

<span data-ttu-id="df1a5-297">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="df1a5-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df1a5-298">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="df1a5-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df1a5-299">Входные данные</span><span class="sxs-lookup"><span data-stu-id="df1a5-299">Inputs</span></span>

### <span data-ttu-id="df1a5-300">System.String</span><span class="sxs-lookup"><span data-stu-id="df1a5-300">System.String</span></span>

<span data-ttu-id="df1a5-301">Строку, содержащую значения параметров **AppendPath** , **TypeName** или **TypeData** , можно передать в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="df1a5-301">You can pipe a string that contains the values of the **AppendPath** , **TypeName** , or **TypeData** parameters to `Update-TypeData`.</span></span>

## <span data-ttu-id="df1a5-302">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="df1a5-302">Outputs</span></span>

### <span data-ttu-id="df1a5-303">Нет</span><span class="sxs-lookup"><span data-stu-id="df1a5-303">None</span></span>

<span data-ttu-id="df1a5-304">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="df1a5-304">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="df1a5-305">Примечания</span><span class="sxs-lookup"><span data-stu-id="df1a5-305">Notes</span></span>

## <span data-ttu-id="df1a5-306">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="df1a5-306">Related links</span></span>

[<span data-ttu-id="df1a5-307">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="df1a5-307">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="df1a5-308">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="df1a5-308">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="df1a5-309">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="df1a5-309">Remove-TypeData</span></span>](Remove-TypeData.md)
