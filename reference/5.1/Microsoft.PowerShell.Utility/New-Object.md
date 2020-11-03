---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: a21fadd58ba566edfc6e484d753b53548f2b519b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227569"
---
# <span data-ttu-id="7fa38-103">New-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-103">New-Object</span></span>

## <span data-ttu-id="7fa38-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7fa38-104">SYNOPSIS</span></span>
<span data-ttu-id="7fa38-105">Создает экземпляр объекта Microsoft .NET Framework или COM.</span><span class="sxs-lookup"><span data-stu-id="7fa38-105">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="7fa38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7fa38-106">SYNTAX</span></span>

### <span data-ttu-id="7fa38-107">NET (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7fa38-107">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="7fa38-108">-</span><span class="sxs-lookup"><span data-stu-id="7fa38-108">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="7fa38-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7fa38-109">DESCRIPTION</span></span>

<span data-ttu-id="7fa38-110">`New-Object`Командлет создает экземпляр .NET Framework или COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="7fa38-110">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="7fa38-111">Можно указать тип класса .NET Framework или идентификатор ProgID объекта COM.</span><span class="sxs-lookup"><span data-stu-id="7fa38-111">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="7fa38-112">По умолчанию вводится полное имя класса .NET Framework, и командлет возвращает ссылку на экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="7fa38-112">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="7fa38-113">Чтобы создать экземпляр COM-объекта, используйте параметр **ComObject** и укажите ProgID объекта в качестве его значения.</span><span class="sxs-lookup"><span data-stu-id="7fa38-113">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="7fa38-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="7fa38-114">EXAMPLES</span></span>

### <span data-ttu-id="7fa38-115">Пример 1. Создание объекта System. Version</span><span class="sxs-lookup"><span data-stu-id="7fa38-115">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="7fa38-116">В этом примере создается объект **System. Version** с использованием строки "1.2.3.4" в качестве конструктора.</span><span class="sxs-lookup"><span data-stu-id="7fa38-116">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="7fa38-117">Пример 2. Создание COM-объекта Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="7fa38-117">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="7fa38-118">В этом примере создаются два экземпляра COM-объекта, представляющего приложение Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7fa38-118">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="7fa38-119">Первый экземпляр использует хэш-таблицу параметра **Свойства** для вызова метода **Navigate2** и устанавливает свойство **Visible** объекта в значение `$True` , чтобы сделать приложение видимым.</span><span class="sxs-lookup"><span data-stu-id="7fa38-119">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="7fa38-120">Второй экземпляр получает те же результаты с отдельными командами.</span><span class="sxs-lookup"><span data-stu-id="7fa38-120">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="7fa38-121">Пример 3. Использование параметра with для создания устранимой ошибки</span><span class="sxs-lookup"><span data-stu-id="7fa38-121">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="7fa38-122">В этом примере показано, что при **добавлении параметра с параметром «** явное» `New-Object` командлет создает неустранимую ошибку, когда COM-объект использует сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7fa38-122">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### <span data-ttu-id="7fa38-123">Пример 4. Создание COM-объекта для управления рабочим столом Windows</span><span class="sxs-lookup"><span data-stu-id="7fa38-123">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="7fa38-124">В этом примере показано, как создать и использовать COM-объект для управления рабочим столом Windows.</span><span class="sxs-lookup"><span data-stu-id="7fa38-124">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="7fa38-125">Первая команда использует параметр **ComObject** `New-Object` командлета для создания com-объекта с **оболочкой. ProgID приложения** .</span><span class="sxs-lookup"><span data-stu-id="7fa38-125">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="7fa38-126">Он сохраняет полученный объект в `$ObjShell` переменной.</span><span class="sxs-lookup"><span data-stu-id="7fa38-126">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="7fa38-127">Вторая команда передает `$ObjShell` переменную в `Get-Member` командлет, который отображает свойства и методы COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="7fa38-127">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="7fa38-128">Между методами используется метод **тоггледесктоп** .</span><span class="sxs-lookup"><span data-stu-id="7fa38-128">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="7fa38-129">Третья команда вызывает метод **ToggleDesktop** объекта, чтобы свести к минимуму число открытых окон на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="7fa38-129">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### <span data-ttu-id="7fa38-130">Пример 5. Передача нескольких аргументов в конструктор</span><span class="sxs-lookup"><span data-stu-id="7fa38-130">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="7fa38-131">В этом примере показано, как создать объект с конструктором, который принимает несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="7fa38-131">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="7fa38-132">Параметры должны быть размещены в массиве при использовании параметра **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="7fa38-132">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="7fa38-133">PowerShell привязывает каждый член массива к параметру конструктора.</span><span class="sxs-lookup"><span data-stu-id="7fa38-133">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="7fa38-134">В этом примере для удобства чтения используется параметр Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="7fa38-134">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="7fa38-135">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="7fa38-135">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="7fa38-136">Пример 6. вызов конструктора, принимающего массив в качестве одного параметра</span><span class="sxs-lookup"><span data-stu-id="7fa38-136">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="7fa38-137">В этом примере показано, как создать объект с конструктором, принимающим параметр, который является массивом или коллекцией.</span><span class="sxs-lookup"><span data-stu-id="7fa38-137">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="7fa38-138">Параметр массива должен быть помещен в оболочку внутри другого массива.</span><span class="sxs-lookup"><span data-stu-id="7fa38-138">The array parameter must be put in wrapped inside another array.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

<span data-ttu-id="7fa38-139">Первая попытка создать объект в этом примере завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7fa38-139">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="7fa38-140">PowerShell попытался привязать три члена `$array` к параметрам конструктора, но конструктор не принимает три параметра.</span><span class="sxs-lookup"><span data-stu-id="7fa38-140">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="7fa38-141">Перенос `$array` в другой массив предотвращает попытку PowerShell выполнить привязку трех членов `$array` к параметрам конструктора.</span><span class="sxs-lookup"><span data-stu-id="7fa38-141">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="7fa38-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7fa38-142">PARAMETERS</span></span>

### <span data-ttu-id="7fa38-143">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="7fa38-143">-ArgumentList</span></span>

<span data-ttu-id="7fa38-144">Задает массив аргументов для передачи конструктору класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fa38-144">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="7fa38-145">Если конструктор принимает один параметр, который является массивом, этот параметр необходимо заключить в другой массив.</span><span class="sxs-lookup"><span data-stu-id="7fa38-145">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="7fa38-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="7fa38-146">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="7fa38-147">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="7fa38-147">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="7fa38-148">Псевдоним для **ArgumentList** — **Args**.</span><span class="sxs-lookup"><span data-stu-id="7fa38-148">The alias for **ArgumentList** is **Args**.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fa38-149">-ComObject</span><span class="sxs-lookup"><span data-stu-id="7fa38-149">-ComObject</span></span>

<span data-ttu-id="7fa38-150">Указывает программный идентификатор (ProgID) объекта COM.</span><span class="sxs-lookup"><span data-stu-id="7fa38-150">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fa38-151">-Property</span><span class="sxs-lookup"><span data-stu-id="7fa38-151">-Property</span></span>

<span data-ttu-id="7fa38-152">Задает значения свойств и вызывает методы нового объекта.</span><span class="sxs-lookup"><span data-stu-id="7fa38-152">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="7fa38-153">Введите хэш-таблицу, в которой ключи — это имена свойств или методов, а значения — это значения свойств или аргументы методов.</span><span class="sxs-lookup"><span data-stu-id="7fa38-153">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="7fa38-154">`New-Object` Создает объект и задает каждое значение свойства и вызывает каждый метод в том порядке, в котором они отображаются в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="7fa38-154">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="7fa38-155">Если новый объект является производным от класса **PSObject** и вы указали свойство, которое не существует в объекте, `New-Object` добавляет указанное свойство в объект в качестве NoteProperty.</span><span class="sxs-lookup"><span data-stu-id="7fa38-155">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="7fa38-156">Если объект не является **PSObject** , команда создает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="7fa38-156">If the object is not a **PSObject** , the command generates a non-terminating error.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fa38-157">— Не ограничивать</span><span class="sxs-lookup"><span data-stu-id="7fa38-157">-Strict</span></span>

<span data-ttu-id="7fa38-158">Указывает, что командлет создает неустранимую ошибку, когда COM-объект, который вы пытаетесь создать, использует сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7fa38-158">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="7fa38-159">Эта функция отличает настоящие COM-объекты от объектов .NET Framework с вызываемыми оболочками COM.</span><span class="sxs-lookup"><span data-stu-id="7fa38-159">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fa38-160">-TypeName</span><span class="sxs-lookup"><span data-stu-id="7fa38-160">-TypeName</span></span>

<span data-ttu-id="7fa38-161">Указывает полное имя класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fa38-161">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="7fa38-162">Нельзя указать и параметр **TypeName** , и параметр **ComObject** .</span><span class="sxs-lookup"><span data-stu-id="7fa38-162">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fa38-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7fa38-163">CommonParameters</span></span>

<span data-ttu-id="7fa38-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7fa38-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7fa38-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7fa38-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7fa38-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7fa38-166">INPUTS</span></span>

### <span data-ttu-id="7fa38-167">Нет</span><span class="sxs-lookup"><span data-stu-id="7fa38-167">None</span></span>

<span data-ttu-id="7fa38-168">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="7fa38-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7fa38-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7fa38-169">OUTPUTS</span></span>

### <span data-ttu-id="7fa38-170">Объект</span><span class="sxs-lookup"><span data-stu-id="7fa38-170">Object</span></span>

<span data-ttu-id="7fa38-171">`New-Object` Возвращает созданный объект.</span><span class="sxs-lookup"><span data-stu-id="7fa38-171">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="7fa38-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7fa38-172">NOTES</span></span>

- <span data-ttu-id="7fa38-173">`New-Object` предоставляет наиболее часто используемые функциональные возможности функции CreateObject VBScript.</span><span class="sxs-lookup"><span data-stu-id="7fa38-173">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="7fa38-174">Инструкция, подобная `Set objShell = CreateObject("Shell.Application")` в VBScript, может быть переведена в `$objShell = New-Object -COMObject "Shell.Application"` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fa38-174">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="7fa38-175">`New-Object` расширяет функциональные возможности, доступные в среде сервера сценариев Windows, облегчая работу с .NET Framework объектами из командной строки и в скриптах.</span><span class="sxs-lookup"><span data-stu-id="7fa38-175">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="7fa38-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7fa38-176">RELATED LINKS</span></span>

[<span data-ttu-id="7fa38-177">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="7fa38-177">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="7fa38-178">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-178">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="7fa38-179">Group-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-179">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="7fa38-180">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="7fa38-180">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="7fa38-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-181">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="7fa38-182">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-182">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="7fa38-183">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="7fa38-183">Tee-Object</span></span>](Tee-Object.md)
