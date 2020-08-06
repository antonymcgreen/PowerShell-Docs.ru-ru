---
title: Элемент Types для набора выбора (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772524"
---
# <a name="types-element-for-selectionset-format"></a>Элемент Types для элемента SelectionSet (формат)

Определяет объекты .NET, которые находятся в наборе выбора.

Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types (формат) элемент (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Types` элемента. Должен существовать хотя бы один дочерний элемент, но максимальное количество дочерних элементов, которое можно добавить, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TypeName типов (Format)](./typename-element-for-types-format.md)|Обязательный элемент.<br /><br /> Указывает объект .NET, который принадлежит набору выбора.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionSet (формат)](./selectionset-element-format.md)|Определяет набор объектов .NET, на которые может ссылаться имя набора.|

## <a name="remarks"></a>Примечания

Объекты, определенные этим элементом, составляют набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.  Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET.

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>См. также

[Определение наборов объектов](./defining-selection-sets.md)

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Элемент TypeName типов (Format)](./typename-element-for-types-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
