---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: 1314d388bff5a46bcf335f3da7908a65233aa46e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600688"
---
# <span data-ttu-id="5a779-102">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="5a779-102">Update-TypeData</span></span>

## <span data-ttu-id="5a779-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5a779-103">Synopsis</span></span>
<span data-ttu-id="5a779-104">Обновляет данные расширенного типа во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="5a779-104">Updates the extended type data in the session.</span></span>

## <span data-ttu-id="5a779-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a779-105">Syntax</span></span>

### <span data-ttu-id="5a779-106">FileSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a779-106">FileSet (Default)</span></span>

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5a779-107">DynamicTypeSet</span><span class="sxs-lookup"><span data-stu-id="5a779-107">DynamicTypeSet</span></span>

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

### <span data-ttu-id="5a779-108">TypeDataSet</span><span class="sxs-lookup"><span data-stu-id="5a779-108">TypeDataSet</span></span>

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a779-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5a779-109">Description</span></span>

<span data-ttu-id="5a779-110">`Update-TypeData`Командлет обновляет данные расширенного типа в сеансе путем перезагрузки `Types.ps1xml` файлов в память и добавления новых данных расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-110">The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.</span></span>

<span data-ttu-id="5a779-111">По умолчанию PowerShell загружает данные расширенного типа по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="5a779-111">By default, PowerShell loads extended type data as it is needed.</span></span> <span data-ttu-id="5a779-112">Без параметров `Update-TypeData` перезагружает все `Types.ps1xml` файлы, загруженные в сеанс, включая все добавленные файлы типов.</span><span class="sxs-lookup"><span data-stu-id="5a779-112">Without parameters, `Update-TypeData` reloads all of the `Types.ps1xml` files that it has loaded in the session, including any type files that you added.</span></span> <span data-ttu-id="5a779-113">С помощью параметров можно `Update-TypeData` добавлять новые файлы типов, а также добавлять и заменять данные расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-113">You can use the parameters of `Update-TypeData` to add new type files and add and replace extended type data.</span></span>

<span data-ttu-id="5a779-114">`Update-TypeData`Командлет можно использовать для предварительной загрузки всех данных типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-114">The `Update-TypeData` cmdlet can be used to preload all type data.</span></span> <span data-ttu-id="5a779-115">Эта функция особенно полезна при разработке собственных типов, так как позволяет загружать их для тестирования.</span><span class="sxs-lookup"><span data-stu-id="5a779-115">This feature is particularly useful when you are developing types and want to load those new types for testing purposes.</span></span>

<span data-ttu-id="5a779-116">Начиная с Windows PowerShell 3,0, можно использовать `Update-TypeData` для добавления и замены данных расширенного типа в сеансе без использования `Types.ps1xml` файла.</span><span class="sxs-lookup"><span data-stu-id="5a779-116">Beginning in Windows PowerShell 3.0, you can use `Update-TypeData` to add and replace extended type data in the session without using a `Types.ps1xml` file.</span></span> <span data-ttu-id="5a779-117">Данные типа, добавленные динамически, то есть без помощи файла, добавляются только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5a779-117">Type data that is added dynamically, that is, without a file, is added only to the current session.</span></span> <span data-ttu-id="5a779-118">Чтобы добавить данные типа во все сеансы, добавьте `Update-TypeData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a779-118">To add the type data to all sessions, add an `Update-TypeData` command to your PowerShell profile.</span></span> <span data-ttu-id="5a779-119">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5a779-119">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="5a779-120">Кроме того, начиная с Windows PowerShell 3,0, командлет можно использовать `Get-TypeData` для получения расширенных типов в текущем сеансе и `Remove-TypeData` командлета для удаления расширенных типов из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5a779-120">Also, beginning in Windows PowerShell 3.0, you can use the `Get-TypeData` cmdlet to get the extended types in the current session and the `Remove-TypeData` cmdlet to delete extended types from the current session.</span></span>

<span data-ttu-id="5a779-121">Исключения, возникающие в свойствах или при добавлении свойств в `Update-TypeData` команду, не сообщают об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5a779-121">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors.</span></span> <span data-ttu-id="5a779-122">Это необходимо для подавления исключений, которые могут возникнуть во многих распространенных типах в процессе форматирования и вывода.</span><span class="sxs-lookup"><span data-stu-id="5a779-122">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="5a779-123">Если вы получаете свойства .NET, подавление исключений можно обойти с помощью синтаксиса метода, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5a779-123">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

`"hello".get_Length()`

<span data-ttu-id="5a779-124">Обратите внимание, что синтаксис метода можно использовать только со свойствами .NET.</span><span class="sxs-lookup"><span data-stu-id="5a779-124">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="5a779-125">Свойства, которые добавляются путем запуска `Update-TypeData` командлета, не могут использовать синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="5a779-125">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

<span data-ttu-id="5a779-126">Дополнительные сведения о `Types.ps1xml` файлах в PowerShell см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="5a779-126">For more information about the `Types.ps1xml` files in PowerShell, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

## <span data-ttu-id="5a779-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="5a779-127">Examples</span></span>

### <span data-ttu-id="5a779-128">Пример 1. обновление расширенных типов</span><span class="sxs-lookup"><span data-stu-id="5a779-128">Example 1: Update extended types</span></span>

```powershell
Update-TypeData
```

<span data-ttu-id="5a779-129">Эта команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, которые уже использовались в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5a779-129">This command updates the extended type configuration from the `Types.ps1xml` files that have already been used in the session.</span></span>

### <span data-ttu-id="5a779-130">Пример 2. Обновление типов несколько раз</span><span class="sxs-lookup"><span data-stu-id="5a779-130">Example 2: Update types multiple times</span></span>

<span data-ttu-id="5a779-131">В этом примере показано, как обновить типы в файле типа несколько раз в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5a779-131">This example shows how to update the types in a type file multiple times in the same session.</span></span>

<span data-ttu-id="5a779-132">Первая команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, сначала обрабатывая `TypesA.types.ps1xml` файлы и `TypesB.types.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="5a779-132">The first command updates the extended type configuration from the `Types.ps1xml` files, processing the `TypesA.types.ps1xml` and `TypesB.types.ps1xml` files first.</span></span>

<span data-ttu-id="5a779-133">Вторая команда показывает `TypesA.types.ps1xml` , как выполнить повторное обновление, например, если вы добавили или изменили тип в файле.</span><span class="sxs-lookup"><span data-stu-id="5a779-133">The second command shows how to update the `TypesA.types.ps1xml` again, such as you might do if you added or changed a type in the file.</span></span> <span data-ttu-id="5a779-134">Можно либо повторить предыдущую команду для `TypesA.types.ps1xml` файла, либо выполнить `Update-TypeData` команду без параметров, поскольку `TypesA.types.ps1xml` уже существует в списке файлов типов для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5a779-134">You can either repeat the previous command for the `TypesA.types.ps1xml` file, or run an `Update-TypeData` command without parameters, because `TypesA.types.ps1xml` is already in the type file list for the current session.</span></span>

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### <span data-ttu-id="5a779-135">Пример 3. Добавление свойства скрипта в объекты DateTime</span><span class="sxs-lookup"><span data-stu-id="5a779-135">Example 3: Add a script property to DateTime objects</span></span>

<span data-ttu-id="5a779-136">В этом примере используется `Update-TypeData` для добавления свойства сценария **Quarter** в объекты **System. DateTime** в текущем сеансе, например, возвращаемые `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="5a779-136">This example uses `Update-TypeData` to add the **Quarter** script property to **System.DateTime** objects in the current session, such as those returned by the `Get-Date` cmdlet.</span></span>

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

<span data-ttu-id="5a779-137">`Update-TypeData`Команда использует параметр **TypeName** для указания типа **System. DateTime** , параметр **MemberName** для указания имени нового свойства, свойство **MemberType** для указания типа **ScriptProperty** , а параметр **value** — для указания скрипта, определяющего ежегодный квартал.</span><span class="sxs-lookup"><span data-stu-id="5a779-137">The `Update-TypeData` command uses the **TypeName** parameter to specify **the System.DateTime** type, the **MemberName** parameter to specify a name for the new property, the **MemberType** property to specify the **ScriptProperty** type, and the **Value** parameter to specify the script that determines the annual quarter.</span></span>

<span data-ttu-id="5a779-138">Значение свойства **Value** — это сценарий, вычисляющий текущий годовой квартал.</span><span class="sxs-lookup"><span data-stu-id="5a779-138">The value of the **Value** property is a script that calculates the current annual quarter.</span></span> <span data-ttu-id="5a779-139">Блок скрипта использует `$this` автоматическую переменную для представления текущего экземпляра объекта и оператор in для определения того, отображается ли значение месяца в каждом массиве целых чисел.</span><span class="sxs-lookup"><span data-stu-id="5a779-139">The script block uses the `$this` automatic variable to represent the current instance of the object and the In operator to determine whether the month value appears in each integer array.</span></span> <span data-ttu-id="5a779-140">Дополнительные сведения об `-in` операторе см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="5a779-140">For more information about the `-in` operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span></span>

<span data-ttu-id="5a779-141">Вторая команда возвращает новое свойство Quarter текущей даты.</span><span class="sxs-lookup"><span data-stu-id="5a779-141">The second command gets the new Quarter property of the current date.</span></span>

### <span data-ttu-id="5a779-142">Пример 4. Обновление типа, который по умолчанию отображает в списках</span><span class="sxs-lookup"><span data-stu-id="5a779-142">Example 4: Update a type that displays in lists by default</span></span>

<span data-ttu-id="5a779-143">В этом примере показано, как задать свойства типа, который по умолчанию отображает в списках, то есть если свойства не заданы.</span><span class="sxs-lookup"><span data-stu-id="5a779-143">This example shows how to set the properties of a type that displays in lists by default, that is, when no properties are specified.</span></span> <span data-ttu-id="5a779-144">Поскольку данные типа не указываются в `Types.ps1xml` файле, они вступают в силу только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5a779-144">Because the type data is not specified in a `Types.ps1xml` file, it is effective only in the current session.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

<span data-ttu-id="5a779-145">Первая команда использует `Update-TypeData` командлет для задания свойств списка по умолчанию для типа **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="5a779-145">The first command uses the `Update-TypeData` cmdlet to set the default list properties for the **System.DateTime** type.</span></span> <span data-ttu-id="5a779-146">С помощью параметра **TypeName** она определяет тип, а с помощью параметра **DefaultDisplayPropertySet** — свойства списка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5a779-146">The command uses the **TypeName** parameter to specify the type and the **DefaultDisplayPropertySet** parameter to specify the default properties for a list.</span></span> <span data-ttu-id="5a779-147">Выбранные свойства включают новое свойство **четвертого** сценария, добавленное в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="5a779-147">The selected properties include the new **Quarter** script property that was added in a previous example.</span></span>

<span data-ttu-id="5a779-148">Вторая команда использует `Get-Date` командлет для получения объекта **System. DateTime** , представляющего текущую дату.</span><span class="sxs-lookup"><span data-stu-id="5a779-148">The second command uses the `Get-Date` cmdlet to get a **System.DateTime** object that represents the current date.</span></span> <span data-ttu-id="5a779-149">Команда использует оператор конвейера ( `|` ) для отправки объекта **DateTime** в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="5a779-149">The command uses a pipeline operator (`|`) to send the **DateTime** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="5a779-150">Поскольку `Format-List` команда не указывает свойства, которые должны отображаться в списке, PowerShell использует значения по умолчанию, установленные `Update-TypeData` командой.</span><span class="sxs-lookup"><span data-stu-id="5a779-150">Because the `Format-List` command does not specify the properties to display in the list, PowerShell uses the default values that were established by the `Update-TypeData` command.</span></span>

### <span data-ttu-id="5a779-151">Пример 5. обновление данных типа для поконвейерного объекта</span><span class="sxs-lookup"><span data-stu-id="5a779-151">Example 5: Update type data for a piped object</span></span>

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

<span data-ttu-id="5a779-152">В этом примере показано, что при передаче объекта в `Update-TypeData` объект `Update-TypeData` добавляет Расширенные данные типа для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="5a779-152">This example demonstrates that when you pipe an object to `Update-TypeData`, `Update-TypeData` adds extended type data for the object type.</span></span>

<span data-ttu-id="5a779-153">Этот метод быстрее, чем использование `Get-Member` командлета или `Get-Type` метода для получения типа объекта.</span><span class="sxs-lookup"><span data-stu-id="5a779-153">This technique is quicker than using the `Get-Member` cmdlet or the `Get-Type` method to get the object type.</span></span> <span data-ttu-id="5a779-154">Однако при передаче коллекции объектов в `Update-TypeData` объект обновляет данные типа первого типа объектов, а затем возвращает ошибку для всех остальных объектов в коллекции, поскольку этот элемент уже определен в типе.</span><span class="sxs-lookup"><span data-stu-id="5a779-154">However, if you pipe a collection of objects to `Update-TypeData`, it updates the type data of the first object type and then returns an error for all other objects in the collection because the member is already defined on the type.</span></span>

<span data-ttu-id="5a779-155">Первая команда использует `Get-Module` командлет для получения модуля PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="5a779-155">The first command uses the `Get-Module` cmdlet to get the PSScheduledJob module.</span></span> <span data-ttu-id="5a779-156">Команда передает объект Module в `Update-TypeData` командлет, который обновляет данные типа для типа **System. Management. Automation. PSModuleInfo** и производных от него типов, например тип модулеинфограупинг, `Get-Module` возвращаемый при использовании параметра **ListAvailable** в команде.</span><span class="sxs-lookup"><span data-stu-id="5a779-156">The command pipes the module object to the `Update-TypeData` cmdlet, which updates the type data for the **System.Management.Automation.PSModuleInfo** type and the types derived from it, such as the ModuleInfoGrouping type that `Get-Module` returns when you use the **ListAvailable** parameter in the command.</span></span>

<span data-ttu-id="5a779-157">`Update-TypeData`Команды добавляют свойство скрипта **SupportsUpdatableHelp** во все импортированные модули.</span><span class="sxs-lookup"><span data-stu-id="5a779-157">The `Update-TypeData` commands adds the **SupportsUpdatableHelp** script property to all imported modules.</span></span> <span data-ttu-id="5a779-158">Значением параметра **value** является скрипт, который возвращает значение, `$True` Если свойство **HelpInfoUri** модуля заполнено и `$False` в противном случае —.</span><span class="sxs-lookup"><span data-stu-id="5a779-158">The value of the **Value** parameter is a script that returns `$True` if the **HelpInfoUri** property of the module is populated and `$False` otherwise.</span></span>

<span data-ttu-id="5a779-159">Вторая команда передает объекты модуля из `Get-Module` в `Format-Table` командлет, который отображает свойства **Name** и **SupportsUpdatableHelp** всех модулей в списке.</span><span class="sxs-lookup"><span data-stu-id="5a779-159">The second command pipes the module objects from `Get-Module` to the `Format-Table` cmdlet, which displays the **Name** and **SupportsUpdatableHelp** properties of all modules in a list.</span></span>

## <span data-ttu-id="5a779-160">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a779-160">Parameters</span></span>

### <span data-ttu-id="5a779-161">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="5a779-161">-AppendPath</span></span>

<span data-ttu-id="5a779-162">Указывает путь к необязательным `.ps1xml` файлам.</span><span class="sxs-lookup"><span data-stu-id="5a779-162">Specifies the path to optional `.ps1xml` files.</span></span> <span data-ttu-id="5a779-163">Эти файлы загружаются в том порядке, в котором они были указаны, после загрузки встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="5a779-163">The specified files are loaded in the order that they are listed after the built-in files are loaded.</span></span> <span data-ttu-id="5a779-164">Можно также передать значение **AppendPath** в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5a779-164">You can also pipe an **AppendPath** value to `Update-TypeData`.</span></span>

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

### <span data-ttu-id="5a779-165">-DefaultDisplayProperty</span><span class="sxs-lookup"><span data-stu-id="5a779-165">-DefaultDisplayProperty</span></span>

<span data-ttu-id="5a779-166">Указывает свойство типа, отображаемое `Format-Wide` командлетом, если другие свойства не указаны.</span><span class="sxs-lookup"><span data-stu-id="5a779-166">Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="5a779-167">Введите имя стандартного или расширенного свойства типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-167">Type the name of a standard or extended property of the type.</span></span> <span data-ttu-id="5a779-168">В качестве значения этого параметра может выступать имя типа, добавленного в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="5a779-168">The value of this parameter can be the name of a type that is added in the same command.</span></span>

<span data-ttu-id="5a779-169">Это значение вступает в силу только в том случае, если для типа в файле не определены широкие представления `Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="5a779-169">This value is effective only when there are no wide views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="5a779-170">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-170">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-171">-DefaultDisplayPropertySet</span><span class="sxs-lookup"><span data-stu-id="5a779-171">-DefaultDisplayPropertySet</span></span>

<span data-ttu-id="5a779-172">Определяет одно или несколько свойств типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-172">Specifies one or more properties of the type.</span></span> <span data-ttu-id="5a779-173">Эти свойства отображаются `Format-List` командлетом, если не заданы другие свойства.</span><span class="sxs-lookup"><span data-stu-id="5a779-173">These properties are displayed by the `Format-List` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="5a779-174">Введите имена стандартных или расширенных свойств типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-174">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="5a779-175">В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="5a779-175">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="5a779-176">Это значение вступает в силу только при отсутствии представлений списков, определенных для типа в `Format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="5a779-176">This value is effective only when there are no list views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="5a779-177">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-177">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-178">-DefaultKeyPropertySet</span><span class="sxs-lookup"><span data-stu-id="5a779-178">-DefaultKeyPropertySet</span></span>

<span data-ttu-id="5a779-179">Определяет одно или несколько свойств типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-179">Specifies one or more properties of the type.</span></span> <span data-ttu-id="5a779-180">Эти свойства используются `Group-Object` командлетами и, `Sort-Object` если другие свойства не указаны.</span><span class="sxs-lookup"><span data-stu-id="5a779-180">These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.</span></span>

<span data-ttu-id="5a779-181">Введите имена стандартных или расширенных свойств типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-181">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="5a779-182">В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.</span><span class="sxs-lookup"><span data-stu-id="5a779-182">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="5a779-183">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-184">-Force</span><span class="sxs-lookup"><span data-stu-id="5a779-184">-Force</span></span>

<span data-ttu-id="5a779-185">Указывает, что командлет использует указанные данные типа, даже если данные типа уже указаны для этого типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-185">Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.</span></span>

<span data-ttu-id="5a779-186">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-186">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-187">-InheritPropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="5a779-187">-InheritPropertySerializationSet</span></span>

<span data-ttu-id="5a779-188">Указывает, унаследован ли набор сериализованных свойств.</span><span class="sxs-lookup"><span data-stu-id="5a779-188">Indicates whether the set of properties that are serialized is inherited.</span></span> <span data-ttu-id="5a779-189">Значение по умолчанию — `$Null`.</span><span class="sxs-lookup"><span data-stu-id="5a779-189">The default value is `$Null`.</span></span> <span data-ttu-id="5a779-190">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5a779-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5a779-191">`$True`.</span><span class="sxs-lookup"><span data-stu-id="5a779-191">`$True`.</span></span> <span data-ttu-id="5a779-192">набор свойств наследуется.</span><span class="sxs-lookup"><span data-stu-id="5a779-192">The property set is inherited.</span></span>
- <span data-ttu-id="5a779-193">`$False`.</span><span class="sxs-lookup"><span data-stu-id="5a779-193">`$False`.</span></span> <span data-ttu-id="5a779-194">набор свойств не наследуется.</span><span class="sxs-lookup"><span data-stu-id="5a779-194">The property set is not inherited.</span></span>
- <span data-ttu-id="5a779-195">`$Null`.</span><span class="sxs-lookup"><span data-stu-id="5a779-195">`$Null`.</span></span> <span data-ttu-id="5a779-196">наследование не определено.</span><span class="sxs-lookup"><span data-stu-id="5a779-196">Inheritance is not defined.</span></span>

<span data-ttu-id="5a779-197">Этот параметр допустим только в том случае, если значение параметра **метод serializationmethod** равно `SpecificProperties` .</span><span class="sxs-lookup"><span data-stu-id="5a779-197">This parameter is valid only when the value of the **SerializationMethod** parameter is `SpecificProperties`.</span></span> <span data-ttu-id="5a779-198">Если значение этого параметра равно `$False` , параметр **пропертисериализатионсет** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5a779-198">When the value of this parameter is `$False`, the **PropertySerializationSet** parameter is required.</span></span>

<span data-ttu-id="5a779-199">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-200">-MemberName</span><span class="sxs-lookup"><span data-stu-id="5a779-200">-MemberName</span></span>

<span data-ttu-id="5a779-201">Определяет имя свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="5a779-201">Specifies the name of a property or method.</span></span>

<span data-ttu-id="5a779-202">Вместе с параметрами **TypeName**, **MemberType**, **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-202">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5a779-203">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-204">-MemberType</span><span class="sxs-lookup"><span data-stu-id="5a779-204">-MemberType</span></span>

<span data-ttu-id="5a779-205">Определяет тип элемента для добавления или изменения.</span><span class="sxs-lookup"><span data-stu-id="5a779-205">Specifies the type of the member to add or change.</span></span>

<span data-ttu-id="5a779-206">Вместе с параметрами **TypeName**, **MemberType**, **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-206">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span> <span data-ttu-id="5a779-207">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5a779-207">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5a779-208">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="5a779-208">AliasProperty</span></span>
- <span data-ttu-id="5a779-209">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="5a779-209">CodeMethod</span></span>
- <span data-ttu-id="5a779-210">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="5a779-210">CodeProperty</span></span>
- <span data-ttu-id="5a779-211">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="5a779-211">Noteproperty</span></span>
- <span data-ttu-id="5a779-212">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="5a779-212">ScriptMethod</span></span>
- <span data-ttu-id="5a779-213">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="5a779-213">ScriptProperty</span></span>

<span data-ttu-id="5a779-214">Дополнительные сведения об этих значениях см. в разделе [Псмембертипес enumeration](/dotnet/api/system.management.automation.psmembertypes).</span><span class="sxs-lookup"><span data-stu-id="5a779-214">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="5a779-215">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-216">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="5a779-216">-PrependPath</span></span>

<span data-ttu-id="5a779-217">Указывает путь к необязательным `.ps1xml` файлам.</span><span class="sxs-lookup"><span data-stu-id="5a779-217">Specifies the path to the optional `.ps1xml` files.</span></span> <span data-ttu-id="5a779-218">Эти файлы загружаются в том порядке, в котором они были указаны, до загрузки встроенных файлов.</span><span class="sxs-lookup"><span data-stu-id="5a779-218">The specified files are loaded in the order that they are listed before the built-in files are loaded.</span></span>

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

### <span data-ttu-id="5a779-219">-PropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="5a779-219">-PropertySerializationSet</span></span>

<span data-ttu-id="5a779-220">Определяет имена сериализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="5a779-220">Specifies the names of properties that are serialized.</span></span> <span data-ttu-id="5a779-221">Используйте этот параметр, если параметр **SerializationMethod** имеет значение **SpecificProperties**.</span><span class="sxs-lookup"><span data-stu-id="5a779-221">Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties**.</span></span>

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

### <span data-ttu-id="5a779-222">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="5a779-222">-SecondValue</span></span>

<span data-ttu-id="5a779-223">Определяет дополнительные значения для элементов **AliasProperty**, **ScriptProperty**, **CodeProperty**, или **CodeMethod**.</span><span class="sxs-lookup"><span data-stu-id="5a779-223">Specifies additional values for **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.</span></span>

<span data-ttu-id="5a779-224">Используйте этот параметр с параметрами **TypeName**, **MemberType**, **value** и **SecondValue** для добавления или изменения свойства или метода типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-224">Use this parameter with the **TypeName**, **MemberType**, **Value**, and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5a779-225">Если значение параметра **MemberType** равно `AliasProperty` , значение параметра **SecondValue** должно быть типом данных.</span><span class="sxs-lookup"><span data-stu-id="5a779-225">When the value of the **MemberType** parameter is `AliasProperty`, the value of the **SecondValue** parameter must be a data type.</span></span> <span data-ttu-id="5a779-226">PowerShell преобразует значение свойства Alias в указанный тип (то есть приводит).</span><span class="sxs-lookup"><span data-stu-id="5a779-226">PowerShell converts (that is, casts) the value of the alias property to the specified type.</span></span> <span data-ttu-id="5a779-227">Например, если добавить свойство Alias, которое предоставляет альтернативное имя для свойства строки, можно также указать **SecondValue** для **System. Int32** , чтобы преобразовать строковое значение с псевдонимом в целое число.</span><span class="sxs-lookup"><span data-stu-id="5a779-227">For example, if you add an alias property that provides an alternate name for a string property, you can also specify a **SecondValue** of **System.Int32** to convert the aliased string value to an integer.</span></span>

<span data-ttu-id="5a779-228">Если значение параметра **MemberType** равно `ScriptProperty` , можно использовать параметр **SecondValue** , чтобы указать дополнительный блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="5a779-228">When the value of the **MemberType** parameter is `ScriptProperty`, you can use the **SecondValue** parameter to specify an additional script block.</span></span> <span data-ttu-id="5a779-229">Блок скрипта в значении параметра **Value** получает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="5a779-229">The script block in the value of the **Value** parameter gets the value of a variable.</span></span> <span data-ttu-id="5a779-230">Блок скрипта в значении параметра **SecondValue** устанавливает значение переменной.</span><span class="sxs-lookup"><span data-stu-id="5a779-230">The script block in the value of the **SecondValue** parameter set the value of the variable.</span></span>

<span data-ttu-id="5a779-231">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-232">-SerializationDepth</span><span class="sxs-lookup"><span data-stu-id="5a779-232">-SerializationDepth</span></span>

<span data-ttu-id="5a779-233">Определяет, сколько уровней объектов типа будут сериализованы как строки.</span><span class="sxs-lookup"><span data-stu-id="5a779-233">Specifies how many levels of type objects are serialized as strings.</span></span> <span data-ttu-id="5a779-234">Значение по умолчанию `1` сериализует объект и его свойства.</span><span class="sxs-lookup"><span data-stu-id="5a779-234">The default value `1` serializes the object and its properties.</span></span> <span data-ttu-id="5a779-235">Значение `0` сериализует объект, но не его свойства.</span><span class="sxs-lookup"><span data-stu-id="5a779-235">A value of `0` serializes the object, but not its properties.</span></span> <span data-ttu-id="5a779-236">Значение `2` сериализует объект, его свойства и все объекты в значениях свойств.</span><span class="sxs-lookup"><span data-stu-id="5a779-236">A value of `2` serializes the object, its properties, and any objects in property values.</span></span>

<span data-ttu-id="5a779-237">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-237">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-238">-SerializationMethod</span><span class="sxs-lookup"><span data-stu-id="5a779-238">-SerializationMethod</span></span>

<span data-ttu-id="5a779-239">Указывает метод сериализации для типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-239">Specifies a serialization method for the type.</span></span> <span data-ttu-id="5a779-240">Метод сериализации определяет сериализуемые свойства типа и метод сериализации.</span><span class="sxs-lookup"><span data-stu-id="5a779-240">A serialization method determines which properties of the type are serialized and the technique that is used to serialize them.</span></span> <span data-ttu-id="5a779-241">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5a779-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5a779-242">`AllPublicProperties`.</span><span class="sxs-lookup"><span data-stu-id="5a779-242">`AllPublicProperties`.</span></span> <span data-ttu-id="5a779-243">сериализуются все открытые свойства типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-243">Serialize all public properties of the type.</span></span> <span data-ttu-id="5a779-244">Можно использовать параметр **SerializationDepth**, позволяющий включить сериализацию дочерних свойств.</span><span class="sxs-lookup"><span data-stu-id="5a779-244">You can use the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>
- <span data-ttu-id="5a779-245">`String`.</span><span class="sxs-lookup"><span data-stu-id="5a779-245">`String`.</span></span> <span data-ttu-id="5a779-246">типа сериализуется в виде строки.</span><span class="sxs-lookup"><span data-stu-id="5a779-246">Serialize the type as a string.</span></span> <span data-ttu-id="5a779-247">Можно использовать параметр **StringSerializationSource**, позволяющий указать свойство типа для использования в результате сериализации.</span><span class="sxs-lookup"><span data-stu-id="5a779-247">You can use the **StringSerializationSource** to specify a property of the type to use as the serialization result.</span></span> <span data-ttu-id="5a779-248">В противном случае тип сериализуется с использованием метода объекта **ToString**.</span><span class="sxs-lookup"><span data-stu-id="5a779-248">Otherwise, the type is serialized by using the **ToString** method of the object.</span></span>
- <span data-ttu-id="5a779-249">`SpecificProperties`.</span><span class="sxs-lookup"><span data-stu-id="5a779-249">`SpecificProperties`.</span></span> <span data-ttu-id="5a779-250">Сериализация только указанных свойств этого типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-250">Serialize only the specified properties of this type.</span></span> <span data-ttu-id="5a779-251">Параметр **PropertySerializationSet** позволяет указать, какие свойства типа требуют сериализации.</span><span class="sxs-lookup"><span data-stu-id="5a779-251">Use the **PropertySerializationSet** parameter to specify the properties of the type that are serialized.</span></span>
  <span data-ttu-id="5a779-252">Можно также использовать параметр **InheritPropertySerializationSet**, определяющий наследование набора свойств, и параметр **SerializationDepth**, определяющий сериализацию дочерних свойств.</span><span class="sxs-lookup"><span data-stu-id="5a779-252">You can also use the **InheritPropertySerializationSet** parameter to determine whether the property set is inherited and the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>

<span data-ttu-id="5a779-253">В PowerShell методы сериализации хранятся в внутренних объектах **псстандардмемберс** .</span><span class="sxs-lookup"><span data-stu-id="5a779-253">In PowerShell, serialization methods are stored in **PSStandardMembers** internal objects.</span></span>

<span data-ttu-id="5a779-254">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-254">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-255">-StringSerializationSource</span><span class="sxs-lookup"><span data-stu-id="5a779-255">-StringSerializationSource</span></span>

<span data-ttu-id="5a779-256">Определяет имя свойства типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-256">Specifies the name of a property of the type.</span></span> <span data-ttu-id="5a779-257">Значение указанного свойства используется в качестве результате сериализации.</span><span class="sxs-lookup"><span data-stu-id="5a779-257">The value of specified property is used as the serialization result.</span></span> <span data-ttu-id="5a779-258">Этот параметр допустим только в том случае, если параметр **метод serializationmethod** имеет значение String.</span><span class="sxs-lookup"><span data-stu-id="5a779-258">This parameter is valid only when the value of the **SerializationMethod** parameter is String.</span></span>

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

### <span data-ttu-id="5a779-259">-TargetTypeForDeserialization</span><span class="sxs-lookup"><span data-stu-id="5a779-259">-TargetTypeForDeserialization</span></span>

<span data-ttu-id="5a779-260">Определяет, в какой типа должны конвертироваться объекты данного типа при десериализации.</span><span class="sxs-lookup"><span data-stu-id="5a779-260">Specifies the type to which object of this type are converted when they are deserialized.</span></span>

<span data-ttu-id="5a779-261">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-262">-TypeAdapter</span><span class="sxs-lookup"><span data-stu-id="5a779-262">-TypeAdapter</span></span>

<span data-ttu-id="5a779-263">Указывает тип адаптера типа, например **Microsoft. PowerShell. CIM. Циминстанцеадаптер**.</span><span class="sxs-lookup"><span data-stu-id="5a779-263">Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter**.</span></span> <span data-ttu-id="5a779-264">Адаптер типов позволяет PowerShell получать члены типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-264">A type adapter enables PowerShell to get the members of a type.</span></span>

<span data-ttu-id="5a779-265">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-265">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-266">-TypeConverter</span><span class="sxs-lookup"><span data-stu-id="5a779-266">-TypeConverter</span></span>

<span data-ttu-id="5a779-267">Определяет преобразователь типов для конвертации значений из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="5a779-267">Specifies a type converter to convert values between different types.</span></span> <span data-ttu-id="5a779-268">Если для типа определен преобразователь, для конвертации используется экземпляр этого преобразователя.</span><span class="sxs-lookup"><span data-stu-id="5a779-268">If a type converter is defined for a type, an instance of the type converter is used for the conversion.</span></span>

<span data-ttu-id="5a779-269">Введите значение **System.Type**, которое является производным от класса **System.ComponentModel.TypeConverter** или **System.Management.Automation.PSTypeConverter**.</span><span class="sxs-lookup"><span data-stu-id="5a779-269">Enter a **System.Type** value that is derived from the **System.ComponentModel.TypeConverter** or **System.Management.Automation.PSTypeConverter** classes.</span></span>

<span data-ttu-id="5a779-270">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-271">-TypeData</span><span class="sxs-lookup"><span data-stu-id="5a779-271">-TypeData</span></span>

<span data-ttu-id="5a779-272">Указывает массив данных типа, который этот командлет добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="5a779-272">Specifies an array of type data that this cmdlet adds to the session.</span></span> <span data-ttu-id="5a779-273">Введите переменную, содержащую объект **TypeData** , или команду, которая получает объект **TypeData** , например `Get-TypeData` команду.</span><span class="sxs-lookup"><span data-stu-id="5a779-273">Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="5a779-274">Можно также передать объект **TypeData** в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5a779-274">You can also pipe a **TypeData** object to `Update-TypeData`.</span></span>

<span data-ttu-id="5a779-275">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-276">-TypeName</span><span class="sxs-lookup"><span data-stu-id="5a779-276">-TypeName</span></span>

<span data-ttu-id="5a779-277">Определяет имя типа для расширения.</span><span class="sxs-lookup"><span data-stu-id="5a779-277">Specifies the name of the type to extend.</span></span>

<span data-ttu-id="5a779-278">Для типов в пространстве имен **System** необходимо указывать короткое имя.</span><span class="sxs-lookup"><span data-stu-id="5a779-278">For types in the **System** namespace, enter the short name.</span></span> <span data-ttu-id="5a779-279">В остальных случаях требуется полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-279">Otherwise, the full type name is required.</span></span> <span data-ttu-id="5a779-280">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5a779-280">Wildcards are not supported.</span></span>

<span data-ttu-id="5a779-281">Можно передать имена типов в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5a779-281">You can pipe type names to `Update-TypeData`.</span></span> <span data-ttu-id="5a779-282">При передаче объекта в `Update-TypeData` `Update-TypeData` возвращает имя типа объекта и тип данных в тип объекта.</span><span class="sxs-lookup"><span data-stu-id="5a779-282">When you pipe an object to `Update-TypeData`, `Update-TypeData` gets the type name of the object and type data to the object type.</span></span>

<span data-ttu-id="5a779-283">Вместе с параметрами **MemberName**, **MemberType**, **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-283">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5a779-284">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-285">-Value</span><span class="sxs-lookup"><span data-stu-id="5a779-285">-Value</span></span>

<span data-ttu-id="5a779-286">Определяет значение свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="5a779-286">Specifies the value of the property or method.</span></span>

<span data-ttu-id="5a779-287">При добавлении `AliasProperty` члена,, `CodeProperty` `ScriptProperty` или `CodeMethod` можно использовать параметр **SecondValue** для добавления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="5a779-287">If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional information.</span></span>

<span data-ttu-id="5a779-288">Вместе с параметрами **MemberName**, **MemberType**, **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.</span><span class="sxs-lookup"><span data-stu-id="5a779-288">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="5a779-289">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5a779-289">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a779-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a779-290">-Confirm</span></span>

<span data-ttu-id="5a779-291">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5a779-291">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a779-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a779-292">-WhatIf</span></span>

<span data-ttu-id="5a779-293">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5a779-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5a779-294">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5a779-294">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a779-295">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5a779-295">CommonParameters</span></span>

<span data-ttu-id="5a779-296">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a779-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a779-297">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a779-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a779-298">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5a779-298">Inputs</span></span>

### <span data-ttu-id="5a779-299">System.String</span><span class="sxs-lookup"><span data-stu-id="5a779-299">System.String</span></span>

<span data-ttu-id="5a779-300">Строку, содержащую значения параметров **AppendPath**, **TypeName** или **TypeData** , можно передать в `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="5a779-300">You can pipe a string that contains the values of the **AppendPath**, **TypeName**, or **TypeData** parameters to `Update-TypeData`.</span></span>

## <span data-ttu-id="5a779-301">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5a779-301">Outputs</span></span>

### <span data-ttu-id="5a779-302">None</span><span class="sxs-lookup"><span data-stu-id="5a779-302">None</span></span>

<span data-ttu-id="5a779-303">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5a779-303">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="5a779-304">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a779-304">Notes</span></span>

## <span data-ttu-id="5a779-305">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5a779-305">Related links</span></span>

[<span data-ttu-id="5a779-306">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="5a779-306">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="5a779-307">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="5a779-307">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="5a779-308">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="5a779-308">Remove-TypeData</span></span>](Remove-TypeData.md)

