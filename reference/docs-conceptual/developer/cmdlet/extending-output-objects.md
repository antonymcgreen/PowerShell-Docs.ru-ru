---
title: Расширение выходных объектов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 48f4f2996159d84257ad72d499e3a796aeaa9116
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784322"
---
# <a name="extending-output-objects"></a><span data-ttu-id="0847d-102">Расширение объектов выходных данных</span><span class="sxs-lookup"><span data-stu-id="0847d-102">Extending Output Objects</span></span>

<span data-ttu-id="0847d-103">.NET Framework объекты, возвращаемые командлетами, функциями и скриптами, можно расширить с помощью файлов типов (. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="0847d-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="0847d-104">Файлы типов — это файлы на основе XML, которые позволяют добавлять свойства и методы в существующие объекты.</span><span class="sxs-lookup"><span data-stu-id="0847d-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="0847d-105">Например, Windows PowerShell предоставляет Types.ps1XML-файл, который добавляет элементы в несколько существующих объектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0847d-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="0847d-106">Types.ps1XML-файл находится в каталоге установки Windows PowerShell ( `$pshome` ).</span><span class="sxs-lookup"><span data-stu-id="0847d-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="0847d-107">Вы можете создать собственный файл типов, чтобы расширить эти объекты или расширить другие объекты.</span><span class="sxs-lookup"><span data-stu-id="0847d-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="0847d-108">При расширении объекта с помощью файла типов любой экземпляр объекта расширяется с помощью новых элементов.</span><span class="sxs-lookup"><span data-stu-id="0847d-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="0847d-109">Расширение объекта System. Array</span><span class="sxs-lookup"><span data-stu-id="0847d-109">Extending the System.Array Object</span></span>

<span data-ttu-id="0847d-110">В следующем примере показано, как Windows PowerShell расширяет объект [System. Array](/dotnet/api/System.Array) в Types.ps1XML-файле.</span><span class="sxs-lookup"><span data-stu-id="0847d-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="0847d-111">По умолчанию объекты [System. Array](/dotnet/api/System.Array) имеют `Length` свойство, которое перечисляет количество объектов в массиве.</span><span class="sxs-lookup"><span data-stu-id="0847d-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="0847d-112">Однако, поскольку имя "Length" явно не описывает свойство, Windows PowerShell добавляет `Count` свойство Alias, которое отображает то же значение, что и `Length` свойство.</span><span class="sxs-lookup"><span data-stu-id="0847d-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="0847d-113">Следующий XML-код добавляет `Count` свойство в тип [System. Array](/dotnet/api/System.Array) .</span><span class="sxs-lookup"><span data-stu-id="0847d-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="0847d-114">Чтобы просмотреть это новое свойство псевдонима, используйте команду [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) для любого массива, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0847d-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="0847d-115">Команда возвращает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="0847d-115">The command returns the following results.</span></span>

```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```

<span data-ttu-id="0847d-116">`Count` `Length` Для определения количества объектов в массиве можно использовать свойство или свойство.</span><span class="sxs-lookup"><span data-stu-id="0847d-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="0847d-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="0847d-117">For example:</span></span>

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a><span data-ttu-id="0847d-118">Файлы пользовательских типов</span><span class="sxs-lookup"><span data-stu-id="0847d-118">Custom Types Files</span></span>

<span data-ttu-id="0847d-119">Чтобы создать файл пользовательских типов, начните с копирования существующего файла типов.</span><span class="sxs-lookup"><span data-stu-id="0847d-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="0847d-120">Новый файл может иметь любое имя, но его имя должно иметь расширение ps1xml.</span><span class="sxs-lookup"><span data-stu-id="0847d-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="0847d-121">При копировании файла можно поместить новый файл в любой каталог, доступный для Windows PowerShell, но это полезно для размещения файлов в каталоге установки Windows PowerShell ( `$pshome` ) или в подкаталоге каталога установки.</span><span class="sxs-lookup"><span data-stu-id="0847d-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="0847d-122">Чтобы добавить в файл собственные расширенные типы, добавьте элемент Types для каждого объекта, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="0847d-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="0847d-123">В следующих разделах приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="0847d-123">The following topics provide examples.</span></span>

- <span data-ttu-id="0847d-124">Дополнительные сведения о добавлении свойств и наборов свойств см. в разделе [Расширенные свойства](./extending-properties-for-objects.md) .</span><span class="sxs-lookup"><span data-stu-id="0847d-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="0847d-125">Дополнительные сведения о добавлении методов см. в разделе [Расширенные методы](./defining-default-methods-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="0847d-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="0847d-126">Дополнительные сведения о добавлении наборов элементов см. в разделе [расширенные наборы элементов](./defining-default-member-sets-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="0847d-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="0847d-127">После определения собственных расширенных типов используйте один из следующих методов, чтобы сделать доступными расширенные объекты:</span><span class="sxs-lookup"><span data-stu-id="0847d-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="0847d-128">Чтобы сделать файл расширенных типов доступным для текущего сеанса, используйте командлет [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) , чтобы добавить новый файл.</span><span class="sxs-lookup"><span data-stu-id="0847d-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="0847d-129">Если требуется, чтобы типы применялись к типам, определенным в файлах других типов (включая файл Types.ps1XML), используйте `PrependData` параметр командлета [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) .</span><span class="sxs-lookup"><span data-stu-id="0847d-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="0847d-130">Чтобы сделать файл расширенных типов доступным для всех будущих сеансов, добавьте файл типов в модуль, экспортируйте текущий сеанс или добавьте команду [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0847d-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="0847d-131">Файлы типов подписывания</span><span class="sxs-lookup"><span data-stu-id="0847d-131">Signing Types Files</span></span>

<span data-ttu-id="0847d-132">Файлы типов должны иметь цифровую подпись, чтобы предотвратить незаконное изменение, так как XML может включать блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="0847d-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="0847d-133">Дополнительные сведения о добавлении цифровых подписей см. в разделе [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="0847d-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="0847d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0847d-134">See Also</span></span>

[<span data-ttu-id="0847d-135">Определение свойств по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="0847d-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="0847d-136">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="0847d-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="0847d-137">Определение наборов элементов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="0847d-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="0847d-138">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0847d-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
