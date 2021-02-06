---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3b2db400c5a8a1c61ec30ecee07f91d29b5eb3c1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604372"
---
# <span data-ttu-id="cb1e2-102">New-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-102">New-Object</span></span>

## <span data-ttu-id="cb1e2-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cb1e2-103">SYNOPSIS</span></span>
<span data-ttu-id="cb1e2-104">Создает экземпляр объекта Microsoft .NET Framework или COM.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-104">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="cb1e2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb1e2-105">SYNTAX</span></span>

### <span data-ttu-id="cb1e2-106">NET (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cb1e2-106">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="cb1e2-107">-</span><span class="sxs-lookup"><span data-stu-id="cb1e2-107">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="cb1e2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb1e2-108">DESCRIPTION</span></span>

<span data-ttu-id="cb1e2-109">`New-Object`Командлет создает экземпляр платформа .NET Framework или COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-109">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="cb1e2-110">Можно указать тип класса .NET Framework или идентификатор ProgID объекта COM.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-110">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="cb1e2-111">По умолчанию вводится полное имя класса .NET Framework, и командлет возвращает ссылку на экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-111">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="cb1e2-112">Чтобы создать экземпляр COM-объекта, используйте параметр **ComObject** и укажите ProgID объекта в качестве его значения.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-112">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="cb1e2-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="cb1e2-113">EXAMPLES</span></span>

### <span data-ttu-id="cb1e2-114">Пример 1. Создание объекта System. Version</span><span class="sxs-lookup"><span data-stu-id="cb1e2-114">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="cb1e2-115">В этом примере создается объект **System. Version** с использованием строки "1.2.3.4" в качестве конструктора.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-115">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="cb1e2-116">Пример 2. Создание COM-объекта Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="cb1e2-116">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="cb1e2-117">В этом примере создаются два экземпляра COM-объекта, представляющего приложение Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-117">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="cb1e2-118">Первый экземпляр использует хэш-таблицу параметра **Свойства** для вызова метода **Navigate2** и устанавливает свойство **Visible** объекта в значение `$True` , чтобы сделать приложение видимым.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-118">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="cb1e2-119">Второй экземпляр получает те же результаты с отдельными командами.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-119">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="cb1e2-120">Пример 3. Использование параметра with для создания устранимой ошибки</span><span class="sxs-lookup"><span data-stu-id="cb1e2-120">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="cb1e2-121">В этом примере показано, что при **добавлении параметра с параметром «** явное» `New-Object` командлет создает неустранимую ошибку, когда COM-объект использует сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-121">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

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

### <span data-ttu-id="cb1e2-122">Пример 4. Создание COM-объекта для управления рабочим столом Windows</span><span class="sxs-lookup"><span data-stu-id="cb1e2-122">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="cb1e2-123">В этом примере показано, как создать и использовать COM-объект для управления рабочим столом Windows.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-123">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="cb1e2-124">Первая команда использует параметр **ComObject** `New-Object` командлета для создания com-объекта с **оболочкой. ProgID приложения** .</span><span class="sxs-lookup"><span data-stu-id="cb1e2-124">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="cb1e2-125">Он сохраняет полученный объект в `$ObjShell` переменной.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-125">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="cb1e2-126">Вторая команда передает `$ObjShell` переменную в `Get-Member` командлет, который отображает свойства и методы COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-126">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="cb1e2-127">Между методами используется метод **тоггледесктоп** .</span><span class="sxs-lookup"><span data-stu-id="cb1e2-127">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="cb1e2-128">Третья команда вызывает метод **ToggleDesktop** объекта, чтобы свести к минимуму число открытых окон на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-128">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

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

### <span data-ttu-id="cb1e2-129">Пример 5. Передача нескольких аргументов в конструктор</span><span class="sxs-lookup"><span data-stu-id="cb1e2-129">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="cb1e2-130">В этом примере показано, как создать объект с конструктором, который принимает несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-130">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="cb1e2-131">Параметры должны быть размещены в массиве при использовании параметра **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="cb1e2-131">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="cb1e2-132">PowerShell привязывает каждый член массива к параметру конструктора.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-132">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="cb1e2-133">В этом примере для удобства чтения используется параметр Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-133">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="cb1e2-134">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="cb1e2-134">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="cb1e2-135">Пример 6. вызов конструктора, принимающего массив в качестве одного параметра</span><span class="sxs-lookup"><span data-stu-id="cb1e2-135">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="cb1e2-136">В этом примере показано, как создать объект с конструктором, принимающим параметр, который является массивом или коллекцией.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-136">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="cb1e2-137">Параметр массива должен быть помещен в оболочку внутри другого массива.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-137">The array parameter must be put in wrapped inside another array.</span></span>

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

<span data-ttu-id="cb1e2-138">Первая попытка создать объект в этом примере завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-138">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="cb1e2-139">PowerShell попытался привязать три члена `$array` к параметрам конструктора, но конструктор не принимает три параметра.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-139">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="cb1e2-140">Перенос `$array` в другой массив предотвращает попытку PowerShell выполнить привязку трех членов `$array` к параметрам конструктора.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-140">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="cb1e2-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb1e2-141">PARAMETERS</span></span>

### <span data-ttu-id="cb1e2-142">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="cb1e2-142">-ArgumentList</span></span>

<span data-ttu-id="cb1e2-143">Задает массив аргументов для передачи конструктору класса платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-143">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="cb1e2-144">Если конструктор принимает один параметр, который является массивом, этот параметр необходимо заключить в другой массив.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-144">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="cb1e2-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="cb1e2-145">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="cb1e2-146">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="cb1e2-146">For more information about the behavior of **ArgumentList**, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="cb1e2-147">Псевдоним для **ArgumentList** — **Args**.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-147">The alias for **ArgumentList** is **Args**.</span></span>

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

### <span data-ttu-id="cb1e2-148">-ComObject</span><span class="sxs-lookup"><span data-stu-id="cb1e2-148">-ComObject</span></span>

<span data-ttu-id="cb1e2-149">Указывает программный идентификатор (ProgID) объекта COM.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-149">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

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

### <span data-ttu-id="cb1e2-150">-Property</span><span class="sxs-lookup"><span data-stu-id="cb1e2-150">-Property</span></span>

<span data-ttu-id="cb1e2-151">Задает значения свойств и вызывает методы нового объекта.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-151">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="cb1e2-152">Введите хэш-таблицу, в которой ключи — это имена свойств или методов, а значения — это значения свойств или аргументы методов.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-152">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="cb1e2-153">`New-Object` Создает объект и задает каждое значение свойства и вызывает каждый метод в том порядке, в котором они отображаются в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-153">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="cb1e2-154">Если новый объект является производным от класса **PSObject** и вы указали свойство, которое не существует в объекте, `New-Object` добавляет указанное свойство в объект в качестве NoteProperty.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-154">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="cb1e2-155">Если объект не является **PSObject**, команда создает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-155">If the object is not a **PSObject**, the command generates a non-terminating error.</span></span>

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

### <span data-ttu-id="cb1e2-156">— Не ограничивать</span><span class="sxs-lookup"><span data-stu-id="cb1e2-156">-Strict</span></span>

<span data-ttu-id="cb1e2-157">Указывает, что командлет создает неустранимую ошибку, когда COM-объект, который вы пытаетесь создать, использует сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-157">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="cb1e2-158">Эта функция отличает настоящие COM-объекты от объектов .NET Framework с вызываемыми оболочками COM.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-158">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

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

### <span data-ttu-id="cb1e2-159">-TypeName</span><span class="sxs-lookup"><span data-stu-id="cb1e2-159">-TypeName</span></span>

<span data-ttu-id="cb1e2-160">Указывает полное имя класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-160">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="cb1e2-161">Нельзя указать и параметр **TypeName** , и параметр **ComObject** .</span><span class="sxs-lookup"><span data-stu-id="cb1e2-161">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

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

### <span data-ttu-id="cb1e2-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cb1e2-162">CommonParameters</span></span>

<span data-ttu-id="cb1e2-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb1e2-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cb1e2-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb1e2-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cb1e2-165">INPUTS</span></span>

### <span data-ttu-id="cb1e2-166">None</span><span class="sxs-lookup"><span data-stu-id="cb1e2-166">None</span></span>

<span data-ttu-id="cb1e2-167">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="cb1e2-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cb1e2-168">OUTPUTS</span></span>

### <span data-ttu-id="cb1e2-169">Объект</span><span class="sxs-lookup"><span data-stu-id="cb1e2-169">Object</span></span>

<span data-ttu-id="cb1e2-170">`New-Object` Возвращает созданный объект.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-170">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="cb1e2-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cb1e2-171">NOTES</span></span>

- <span data-ttu-id="cb1e2-172">`New-Object` предоставляет наиболее часто используемые функциональные возможности функции CreateObject VBScript.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-172">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="cb1e2-173">Инструкция, подобная `Set objShell = CreateObject("Shell.Application")` в VBScript, может быть переведена в `$objShell = New-Object -COMObject "Shell.Application"` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-173">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="cb1e2-174">`New-Object` расширяет функциональные возможности, доступные в среде сервера сценариев Windows, облегчая работу с платформа .NET Framework объектами из командной строки и в скриптах.</span><span class="sxs-lookup"><span data-stu-id="cb1e2-174">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="cb1e2-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cb1e2-175">RELATED LINKS</span></span>

[<span data-ttu-id="cb1e2-176">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="cb1e2-176">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="cb1e2-177">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-177">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="cb1e2-178">Group-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-178">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="cb1e2-179">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="cb1e2-179">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="cb1e2-180">Select-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-180">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="cb1e2-181">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-181">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="cb1e2-182">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="cb1e2-182">Tee-Object</span></span>](Tee-Object.md)

