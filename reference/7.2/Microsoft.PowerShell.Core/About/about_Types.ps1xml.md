---
description: Объясняется, как использовать `Types.ps1xml` файлы для расширения типов объектов, используемых в PowerShell.
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 9a87394631d3318f3fb3f4b2a0cb2ab8d25408d0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599799"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="d7a0c-103">Сведения о Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="d7a0c-103">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="d7a0c-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d7a0c-104">Short description</span></span>
<span data-ttu-id="d7a0c-105">Объясняется, как использовать `Types.ps1xml` файлы для расширения типов объектов, используемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-105">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d7a0c-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d7a0c-106">Long description</span></span>

<span data-ttu-id="d7a0c-107">Расширенные данные типа определяют дополнительные свойства и методы ("члены") типов объектов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-107">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="d7a0c-108">Существует два способа добавления данных расширенного типа в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-108">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="d7a0c-109">`Types.ps1xml` файл: XML-файл, определяющий Расширенные данные типа.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-109">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="d7a0c-110">`Update-TypeData`: Командлет, который перезагружает `Types.ps1xml` файлы и определяет Расширенные данные для типов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-110">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="d7a0c-111">В этом разделе описываются `Types.ps1xml` файлы.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-111">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="d7a0c-112">Дополнительные сведения об использовании `Update-TypeData` командлета для добавления динамических данных расширенного типа в текущий сеанс см. в разделе [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-112">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="d7a0c-113">Сведения о расширенных типах данных</span><span class="sxs-lookup"><span data-stu-id="d7a0c-113">About extended type data</span></span>

<span data-ttu-id="d7a0c-114">Расширенные данные типа определяют дополнительные свойства и методы ("члены") типов объектов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-114">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="d7a0c-115">Можно расширить любой тип, поддерживаемый PowerShell, и использовать добавленные свойства и методы так же, как и свойства, определенные для типов объектов.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-115">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="d7a0c-116">Например, PowerShell добавляет свойство **DateTime** во все `System.DateTime` объекты, например те, которые `Get-Date` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-116">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="d7a0c-117">Свойство **DateTime** не будет найдено в описании структуры [System. DateTime](/dotnet/api/system.datetime) , так как PowerShell добавляет свойство, и оно видимо только в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-117">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="d7a0c-118">PowerShell внутренне определяет набор расширенных типов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-118">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="d7a0c-119">Эти сведения о типе загружаются в каждом сеансе PowerShell при запуске.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-119">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="d7a0c-120">Свойство **DateTime** является частью этого набора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-120">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="d7a0c-121">До выхода версии PowerShell 6 определения типов сохраняли `Types.ps1xml` файл в каталоге установки PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-121">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="d7a0c-122">Добавление данных расширенного типа в PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7a0c-122">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="d7a0c-123">В сеансах PowerShell есть три источника данных расширенного типа.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-123">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="d7a0c-124">Объект, определенный PowerShell и автоматически загружаемый в каждый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-124">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="d7a0c-125">Начиная с PowerShell 6, эта информация компилируется в PowerShell и больше не отправляется в `Types.ps1xml` файл.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-125">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="d7a0c-126">`Types.ps1xml`Файлы, экспортируемые модулями, загружаются при импорте модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-126">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="d7a0c-127">Данные расширенного типа, определенные с помощью `Update-TypeData` командлета, добавляются только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-127">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="d7a0c-128">Он не сохраняется в файле.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-128">It is not saved in a file.</span></span>

<span data-ttu-id="d7a0c-129">В сеансе данные расширенного типа из трех источников применяются к объектам одинаковым образом и доступны для всех объектов указанных типов.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-129">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="d7a0c-130">Командлеты TypeData</span><span class="sxs-lookup"><span data-stu-id="d7a0c-130">The TypeData cmdlets</span></span>

<span data-ttu-id="d7a0c-131">Следующие командлеты включены в модуль **Microsoft. PowerShell. Utility** в PowerShell 3,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-131">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="d7a0c-132">`Get-TypeData`: Получает данные расширенного типа в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-132">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="d7a0c-133">`Update-TypeData`: Перезагружает `Types.ps1xml` файлы.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-133">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="d7a0c-134">Добавляет данные расширенного типа в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-134">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="d7a0c-135">`Remove-TypeData`: Удаляет данные расширенного типа из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-135">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="d7a0c-136">Дополнительные сведения об этих командлетах см. в разделе справки для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-136">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="d7a0c-137">Встроенные Types.ps1XML-файлы</span><span class="sxs-lookup"><span data-stu-id="d7a0c-137">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="d7a0c-138">`Types.ps1xml`Файлы в `$PSHOME` каталоге добавляются в каждый сеанс автоматически.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-138">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="d7a0c-139">`Types.ps1xml`Файл в каталоге установки PowerShell ( `$PSHOME` ) является текстовым файлом на основе XML, который позволяет добавлять свойства и методы в объекты, используемые в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-139">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="d7a0c-140">В PowerShell есть встроенные `Types.ps1xml` файлы, которые добавляют несколько элементов в типы .NET, но `Types.ps1xml` для дальнейшего расширения типов можно создать дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-140">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="d7a0c-141">Например, по умолчанию объекты Array ( `System.Array` ) имеют свойство **length** , которое содержит количество объектов в массиве.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-141">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="d7a0c-142">Однако, поскольку **Длина** имени не содержит четкого описания свойства, PowerShell добавляет свойство Alias с именем **Count** , которое отображает то же значение.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-142">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="d7a0c-143">Следующий XML-код добавляет свойство **Count** к `System.Array` типу.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-143">The following XML adds the **Count** property to the `System.Array` type.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-144">Чтобы получить новый **AliasProperty**, используйте `Get-Member` команду в любом массиве, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-144">To get the new **AliasProperty**, use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="d7a0c-145">Команда возвращает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-145">The command returns the following results.</span></span>

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

<span data-ttu-id="d7a0c-146">В результате вы можете использовать свойство **Count** либо свойство **length** массивов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-146">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="d7a0c-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="d7a0c-147">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="d7a0c-148">Создание новых Types.ps1XML-файлов</span><span class="sxs-lookup"><span data-stu-id="d7a0c-148">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="d7a0c-149">`.ps1xml`Файлы, устанавливаемые с помощью PowerShell, имеют цифровую подпись, чтобы предотвратить незаконное изменение, так как форматирование может включать блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-149">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="d7a0c-150">Поэтому, чтобы добавить свойство или метод в тип .NET, создайте собственные `Types.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-150">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="d7a0c-151">Чтобы создать новый файл, начните с копирования существующего `Types.ps1xml` файла.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-151">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="d7a0c-152">Новый файл может иметь любое имя, но он должен иметь `.ps1xml` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-152">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="d7a0c-153">Новый файл можно поместить в любой каталог, доступный для PowerShell, но он удобен для размещения файлов в каталоге установки PowerShell () или в подкаталоге `$PSHOME` каталога установки.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-153">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="d7a0c-154">После сохранения нового файла используйте `Update-TypeData` командлет, чтобы добавить новый файл в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-154">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="d7a0c-155">Если вы хотите, чтобы типы применялись к определенным встроенным типам, используйте параметр **препенддата** `Update-TypeData` командлета.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-155">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="d7a0c-156">`Update-TypeData` влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-156">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="d7a0c-157">Чтобы внести изменения во все будущие сеансы, экспортируйте консоль или добавьте `Update-TypeData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-157">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="d7a0c-158">Types.ps1XML и Add-Member</span><span class="sxs-lookup"><span data-stu-id="d7a0c-158">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="d7a0c-159">`Types.ps1xml`Файлы добавляют свойства и методы ко всем экземплярам объектов указанного типа .NET в затронутом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-159">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="d7a0c-160">Однако если необходимо добавить свойства или методы только в один экземпляр объекта, используйте `Add-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-160">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="d7a0c-161">Дополнительные сведения см. в разделе [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-161">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="d7a0c-162">Пример. Добавление элемента Age в объекты FileInfo</span><span class="sxs-lookup"><span data-stu-id="d7a0c-162">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="d7a0c-163">В этом примере показано, как добавить свойство **Age** в объекты **System. IO. FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-163">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="d7a0c-164">Возраст файла — это разница между временем создания и текущим временем в днях.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-164">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="d7a0c-165">Так как свойство **Age** вычисляется с помощью блока скрипта, найдите `<ScriptProperty>` тег, который будет использоваться в качестве модели для нового свойства **Age** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-165">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="d7a0c-166">Сохраните следующий XML-код в файле `$PSHOME\MyTypes.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-166">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

<span data-ttu-id="d7a0c-167">Выполните команду `Update-TypeData` , чтобы добавить новый `Types.ps1xml` файл в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-167">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="d7a0c-168">Команда использует параметр **препенддата** для размещения нового файла в порядке очередности выше исходных определений.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-168">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="d7a0c-169">Дополнительные сведения о `Update-TypeData` см. в разделе [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-169">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="d7a0c-170">Чтобы проверить изменение, выполните команду, `Get-ChildItem` чтобы получить файл PowerShell.exe в `$PSHOME` каталоге, а затем передайте файл в `Format-List` командлет, чтобы вывести список всех свойств файла.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-170">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="d7a0c-171">В результате изменения в списке появится свойство **Age** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-171">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="d7a0c-172">XML-файлы в Types.ps1XML-файлах</span><span class="sxs-lookup"><span data-stu-id="d7a0c-172">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="d7a0c-173">Полное определение схемы можно найти в файле [types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) в репозитории исходного кода PowerShell на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-173">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="d7a0c-174">`<Types>`Тег включает все типы, определенные в файле.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-174">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="d7a0c-175">Должен быть только один `<Types>` тег.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-175">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="d7a0c-176">Каждый тип .NET, упомянутый в файле, должен быть представлен `<Type>` тегом.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-176">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="d7a0c-177">Теги типа должны содержать следующие Теги:</span><span class="sxs-lookup"><span data-stu-id="d7a0c-177">The type tags must contain the following tags:</span></span>

<span data-ttu-id="d7a0c-178">`<Name>`: Заключает имя затронутого типа .NET.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-178">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="d7a0c-179">`<Members>`: Заключает теги для новых свойств и методов, определенных для типа .NET.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-179">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="d7a0c-180">Любой из следующих тегов элементов может находиться внутри `<Members>` тега.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-180">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="d7a0c-181">`<AliasProperty>`: Определяет новое имя для существующего свойства.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-181">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="d7a0c-182">`<AliasProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<ReferencedMemberName>` тег, указывающий существующее свойство.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-182">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="d7a0c-183">Например, свойство псевдонима **Count** является псевдонимом для свойства **length** объектов Array.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-183">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-184">`<CodeMethod>`: Ссылается на статический метод класса .NET.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-184">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="d7a0c-185">`<CodeMethod>`Тег должен иметь `<Name>` тег, указывающий имя нового метода и `<GetCodeReference>` тег, указывающий код, в котором определен метод.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-185">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="d7a0c-186">Например, свойство **mode** `System.IO.DirectoryInfo` объектов — это свойство Code, определенное в поставщике файловой системы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-186">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-187">`<CodeProperty>`: Ссылается на статический метод класса .NET.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-187">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="d7a0c-188">`<CodeProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<GetCodeReference>` тег, указывающий код, в котором определено свойство.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-188">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="d7a0c-189">Например, свойство **mode** `System.IO.DirectoryInfo` объектов — это свойство Code, определенное в поставщике файловой системы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-189">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-190">`<MemberSet>`: Определяет коллекцию элементов (свойства и методы).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-190">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="d7a0c-191">`<MemberSet>`Теги отображаются в первичных `<Members>` тегах.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-191">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="d7a0c-192">Теги должны заключать `<Name>` тег в окружающее имя набора элементов и дополнительный `<Members>` тег, охватывающий элементы (свойства и методы) в наборе.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-192">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="d7a0c-193">Любой из тегов, которые создают свойство (например, `<NoteProperty>` или `<ScriptProperty>` ) или метод (например, `<Method>` или), `<ScriptMethod>` может быть членом набора.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-193">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="d7a0c-194">В `Types.ps1xml` файлах `<MemberSet>` тег используется для определения представлений по умолчанию для объектов .NET в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-194">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="d7a0c-195">В этом случае имя набора элементов (значение в `<Name>` тегах) всегда равно **псстандардмемберс**, а имена свойств (значение `<Name>` тега) являются одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="d7a0c-195">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers**, and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="d7a0c-196">`DefaultDisplayProperty`: Отдельное свойство объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-196">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="d7a0c-197">`DefaultDisplayPropertySet`: Одно или несколько свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-197">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="d7a0c-198">`DefaultKeyPropertySet`: Одно или несколько ключевых свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-198">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="d7a0c-199">Ключевое свойство определяет экземпляры значений свойств, такие как ИДЕНТИФИКАТОРы элементов в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-199">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="d7a0c-200">Например, следующий XML-код определяет отображение служб (объектов) по умолчанию `System.ServiceProcess.ServiceController` , возвращаемое `Get-Service` командлетом.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-200">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="d7a0c-201">Он определяет набор элементов с именем **псстандардмемберс** , который состоит из набора свойств по умолчанию со свойствами **Status**, **Name** и **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-201">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status**, **Name**, and **DisplayName** properties.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-202">`<Method>`: Ссылается на собственный метод базового объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-202">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="d7a0c-203">`<Methods>`: Коллекция методов объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-203">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="d7a0c-204">`<NoteProperty>`: Определяет свойство со статическим значением.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-204">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="d7a0c-205">`<NoteProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<Value>` тег, указывающий значение свойства.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-205">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="d7a0c-206">Например, следующий XML-код создает свойство **Status** для объектов **System. IO. DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-206">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="d7a0c-207">Значение свойства **Status** всегда равно **Success**.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-207">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-208">`<ParameterizedProperty>`: Свойства, принимающие аргументы и возвращающие значение.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-208">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="d7a0c-209">`<Properties>`: Коллекция свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-209">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="d7a0c-210">`<Property>`: Свойство базового объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-210">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="d7a0c-211">`<PropertySet>`: Определяет коллекцию свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-211">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="d7a0c-212">`<PropertySet>`Тег должен иметь `<Name>` тег, указывающий имя набора свойств, и `<ReferencedProperty>` тег, указывающий свойства.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-212">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="d7a0c-213">Имена свойств заключаются в `<Name>` тег.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-213">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="d7a0c-214">В `Types.ps1xml` `<PropertySet>` теги используются для определения наборов свойств для отображаемого по умолчанию объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-214">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="d7a0c-215">Можно задать отображение по умолчанию по значению **псстандардмемберс** в `<Name>` теге `<MemberSet>` тега.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-215">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="d7a0c-216">Например, следующий XML-код создает свойство **Status** для `System.IO.DirectoryInfo` объекта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-216">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="d7a0c-217">Значение свойства **Status** всегда равно **Success**.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-217">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-218">`<ScriptMethod>`: Определяет метод, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-218">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="d7a0c-219">`<ScriptMethod>`Тег должен иметь `<Name>` тег, указывающий имя нового метода и `<Script>` тег, который заключает в себя блок скрипта, который возвращает результат метода.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-219">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="d7a0c-220">Например, `ConvertToDateTime` `ConvertFromDateTime` методы и объектов управления ( `System.System.Management.ManagementObject` ) являются методами скриптов, которые используют `ToDateTime` `ToDmtfDateTime` статические методы `System.Management.ManagementDateTimeConverter` класса.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-220">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

<span data-ttu-id="d7a0c-221">`<ScriptProperty>`: Определяет свойство, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-221">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="d7a0c-222">`<ScriptProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<GetScriptBlock>` тег, который заключает в себя блок скрипта, возвращающий значение свойства.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-222">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="d7a0c-223">Например, свойство **versionInfo** объекта **System. IO. FileInfo** представляет собой свойство скрипта, полученное в результате использования свойства **FullName** статического метода **жетверсионинфо** объектов **System. Diagnostics. FileVersionInfo** .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-223">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

<span data-ttu-id="d7a0c-224">Дополнительные сведения см. в разделе [пакет средств разработки программного обеспечения Windows PowerShell (SDK)](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-224">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="d7a0c-225">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="d7a0c-225">Update-TypeData</span></span>

<span data-ttu-id="d7a0c-226">Чтобы загрузить `Types.ps1xml` файлы в сеанс PowerShell, выполните `Update-TypeData` командлет.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-226">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="d7a0c-227">Если требуется, чтобы типы в файле применялись к типам во встроенном `Types.ps1xml` файле, добавьте параметр **препенддата** из `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-227">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="d7a0c-228">`Update-TypeData` влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-228">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="d7a0c-229">Чтобы внести изменения во все будущие сеансы, экспортируйте сеанс или добавьте `Update-TypeData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-229">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="d7a0c-230">Исключения, возникающие в свойствах или при добавлении свойств в `Update-TypeData` команду, не сообщают об ошибках `StdErr` .</span><span class="sxs-lookup"><span data-stu-id="d7a0c-230">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="d7a0c-231">Это необходимо для подавления исключений, которые могут возникнуть во многих распространенных типах в процессе форматирования и вывода.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-231">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="d7a0c-232">Если вы получаете свойства .NET, подавление исключений можно обойти с помощью синтаксиса метода, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d7a0c-232">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="d7a0c-233">Обратите внимание, что синтаксис метода можно использовать только со свойствами .NET.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-233">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="d7a0c-234">Свойства, которые добавляются путем запуска `Update-TypeData` командлета, не могут использовать синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-234">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="d7a0c-235">Подписывание Types.ps1XML-файла</span><span class="sxs-lookup"><span data-stu-id="d7a0c-235">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="d7a0c-236">Чтобы защитить пользователей `Types.ps1xml` файла, можно подписать файл с помощью цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="d7a0c-236">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="d7a0c-237">Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="d7a0c-237">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7a0c-238">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a0c-238">See also</span></span>

[<span data-ttu-id="d7a0c-239">about_Signing</span><span class="sxs-lookup"><span data-stu-id="d7a0c-239">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="d7a0c-240">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d7a0c-240">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="d7a0c-241">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d7a0c-241">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="d7a0c-242">Get-Member</span><span class="sxs-lookup"><span data-stu-id="d7a0c-242">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="d7a0c-243">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="d7a0c-243">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="d7a0c-244">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="d7a0c-244">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="d7a0c-245">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="d7a0c-245">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)

