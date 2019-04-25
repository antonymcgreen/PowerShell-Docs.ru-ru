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
# <a name="extending-output-objects"></a>Расширение объектов выходных данных

Вы можете расширять объекты .NET Framework, возвращаемые командлеты, функции и сценарии, используя файлы типов (ps1xml). Типы файлов, XML-файлы, которые позволяют добавлять свойства и методы в существующие объекты. Например Windows PowerShell предоставляет файл Types.ps1xml, который добавляет элементы в нескольких существующих объектов .NET Framework. Файл Types.ps1xml находится в каталоге установки Windows PowerShell (`$pshome`). Можно создать собственный файл типов для дальнейшего расширения этих объектов или для расширения других объектов. При расширении объекта с помощью файла типов, любой экземпляр объекта расширяется с помощью новых элементов.

## <a name="extending-the-systemarray-object"></a>Расширение System.Array объекта

В следующем примере показано, как Windows PowerShell расширяет [System.Array](/dotnet/api/System.Array) объекта в файле Types.ps1xml. По умолчанию [System.Array](/dotnet/api/System.Array) объекты имеют `Length` свойство, которое указывает число объектов в массиве. Тем не менее, поскольку имя «длина» не четко описывает свойство, Windows PowerShell добавляет `Count` свойства псевдонима, который отображает то же значение, что `Length` свойство. Следующий XML-код добавляет `Count` свойства [System.Array](/dotnet/api/System.Array) типа.

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

Чтобы просмотреть это новое свойство псевдонима, используйте [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) команду на любой массив, как показано в следующем примере.

```powershell
Get-Member -InputObject (1,2,3,4)
```

Эта команда возвращает следующие результаты.
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
Можно использовать либо `Count` свойство или `Length` свойство, чтобы определить, сколько объектов в массиве. Например:

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

## <a name="custom-types-files"></a>Пользовательские типы файлов

Чтобы создать файл пользовательских типов, запустите путем копирования существующего файла типов. Новый файл может иметь любое имя, но он должен иметь расширение ps1xml-файлы. При копировании файла, можно поместить новый файл в любом каталоге, который доступен в Windows PowerShell, но желательно поместить файлы в каталоге установки Windows PowerShell (`$pshome`) или в подкаталоге каталога установки.

Чтобы добавить собственные расширенные типы в файл, добавьте элемент типов для каждого объекта, который требуется расширить. В следующих разделах приводятся примеры.

- Дополнительные сведения о добавлении и наборах свойств, см. в разделе [расширенные свойства](./extending-properties-for-objects.md)

- Дополнительные сведения о добавлении методов см. в разделе [расширенных методов](./defining-default-methods-for-objects.md).

- Дополнительные сведения о добавлении наборы элементов, см. в разделе [расширенные наборы элементов](./defining-default-member-sets-for-objects.md).

После определения расширенных типов, используйте один из следующих методов для предоставления расширенных объектов:

- Чтобы сделать файл расширенные типы, доступные в текущий сеанс, используйте [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) командлет, чтобы добавить новый файл. Если вы хотите типов имеют приоритет над типами, которые определены в другие типы файлов (включая файл Types.ps1xml), используйте `PrependData` параметр [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) командлета.
- Чтобы сделать файл расширенные типы доступными для всех будущих сеансов, добавьте файл типов в модуль экспорта текущего сеанса и добавить [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) команду в профиль Windows PowerShell.

## <a name="signing-types-files"></a>Подписание файлов типов

Типы файлов должны иметь цифровую подпись для предотвращения мошенничества, так как XML могут включать блоки скриптов. Дополнительные сведения о добавлении цифровых подписей, см. в разделе [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)

## <a name="see-also"></a>См. также

[Определение свойств по умолчанию для объектов](./extending-properties-for-objects.md)

[Определение методов по умолчанию для объектов](./defining-default-methods-for-objects.md)

[Определение наборов элементов по умолчанию для объектов](./defining-default-member-sets-for-objects.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
