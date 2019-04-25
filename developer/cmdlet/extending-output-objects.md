---
title: Расширение объектов выходных данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a252e0ec-d456-42d7-bd49-d6b8bc57f388
caps.latest.revision: 11
ms.openlocfilehash: 9c9d50c880f843e21621e5735c800e3afb48b2ad
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068170"
---
# <a name="extending-output-objects"></a><span data-ttu-id="d9ad8-102">Расширение объектов выходных данных</span><span class="sxs-lookup"><span data-stu-id="d9ad8-102">Extending Output Objects</span></span>

<span data-ttu-id="d9ad8-103">Вы можете расширять объекты .NET Framework, возвращаемые командлеты, функции и сценарии, используя файлы типов (ps1xml).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="d9ad8-104">Типы файлов, XML-файлы, которые позволяют добавлять свойства и методы в существующие объекты.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="d9ad8-105">Например Windows PowerShell предоставляет файл Types.ps1xml, который добавляет элементы в нескольких существующих объектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="d9ad8-106">Файл Types.ps1xml находится в каталоге установки Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="d9ad8-107">Можно создать собственный файл типов для дальнейшего расширения этих объектов или для расширения других объектов.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="d9ad8-108">При расширении объекта с помощью файла типов, любой экземпляр объекта расширяется с помощью новых элементов.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="d9ad8-109">Расширение System.Array объекта</span><span class="sxs-lookup"><span data-stu-id="d9ad8-109">Extending the System.Array Object</span></span>

<span data-ttu-id="d9ad8-110">В следующем примере показано, как Windows PowerShell расширяет [System.Array](/dotnet/api/System.Array) объекта в файле Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="d9ad8-111">По умолчанию [System.Array](/dotnet/api/System.Array) объекты имеют `Length` свойство, которое указывает число объектов в массиве.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="d9ad8-112">Тем не менее, поскольку имя «длина» не четко описывает свойство, Windows PowerShell добавляет `Count` свойства псевдонима, который отображает то же значение, что `Length` свойство.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="d9ad8-113">Следующий XML-код добавляет `Count` свойства [System.Array](/dotnet/api/System.Array) типа.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="d9ad8-114">Чтобы просмотреть это новое свойство псевдонима, используйте [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) команду на любой массив, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="d9ad8-115">Эта команда возвращает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-115">The command returns the following results.</span></span>
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
<span data-ttu-id="d9ad8-116">Можно использовать либо `Count` свойство или `Length` свойство, чтобы определить, сколько объектов в массиве.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="d9ad8-117">Например:</span><span class="sxs-lookup"><span data-stu-id="d9ad8-117">For example:</span></span>

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

## <a name="custom-types-files"></a><span data-ttu-id="d9ad8-118">Пользовательские типы файлов</span><span class="sxs-lookup"><span data-stu-id="d9ad8-118">Custom Types Files</span></span>

<span data-ttu-id="d9ad8-119">Чтобы создать файл пользовательских типов, запустите путем копирования существующего файла типов.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="d9ad8-120">Новый файл может иметь любое имя, но он должен иметь расширение ps1xml-файлы.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="d9ad8-121">При копировании файла, можно поместить новый файл в любом каталоге, который доступен в Windows PowerShell, но желательно поместить файлы в каталоге установки Windows PowerShell (`$pshome`) или в подкаталоге каталога установки.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="d9ad8-122">Чтобы добавить собственные расширенные типы в файл, добавьте элемент типов для каждого объекта, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="d9ad8-123">В следующих разделах приводятся примеры.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-123">The following topics provide examples.</span></span>

- <span data-ttu-id="d9ad8-124">Дополнительные сведения о добавлении и наборах свойств, см. в разделе [расширенные свойства](./extending-properties-for-objects.md)</span><span class="sxs-lookup"><span data-stu-id="d9ad8-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="d9ad8-125">Дополнительные сведения о добавлении методов см. в разделе [расширенных методов](./defining-default-methods-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="d9ad8-126">Дополнительные сведения о добавлении наборы элементов, см. в разделе [расширенные наборы элементов](./defining-default-member-sets-for-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="d9ad8-127">После определения расширенных типов, используйте один из следующих методов для предоставления расширенных объектов:</span><span class="sxs-lookup"><span data-stu-id="d9ad8-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="d9ad8-128">Чтобы сделать файл расширенные типы, доступные в текущий сеанс, используйте [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) командлет, чтобы добавить новый файл.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="d9ad8-129">Если вы хотите типов имеют приоритет над типами, которые определены в другие типы файлов (включая файл Types.ps1xml), используйте `PrependData` параметр [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) командлета.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="d9ad8-130">Чтобы сделать файл расширенные типы доступными для всех будущих сеансов, добавьте файл типов в модуль экспорта текущего сеанса и добавить [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) команду в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="d9ad8-131">Подписание файлов типов</span><span class="sxs-lookup"><span data-stu-id="d9ad8-131">Signing Types Files</span></span>

<span data-ttu-id="d9ad8-132">Типы файлов должны иметь цифровую подпись для предотвращения мошенничества, так как XML могут включать блоки скриптов.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="d9ad8-133">Дополнительные сведения о добавлении цифровых подписей, см. в разделе [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="d9ad8-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="d9ad8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d9ad8-134">See Also</span></span>

[<span data-ttu-id="d9ad8-135">Определение свойств по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="d9ad8-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="d9ad8-136">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="d9ad8-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="d9ad8-137">Определение наборов элементов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="d9ad8-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="d9ad8-138">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9ad8-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
