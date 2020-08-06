---
title: Элемент TypeName для типов (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 40fad73c66124d6c3b0d969b4268713a492c963a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772541"
---
# <a name="typename-element-for-types-format"></a>Элемент TypeName для элемента Types (формат)

Указывает тип .NET объекта, который принадлежит к набору выбора.

Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types элемент (Format) имя_типа Types (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента. `TypeName`В набор выбора необходимо добавить хотя бы один элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Types (Format)](./types-element-for-selectionset-format.md)|Определяет объекты .NET, которые находятся в наборе выбора.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя для типа .NET.

## <a name="remarks"></a>Примечания

Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование. При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.

Стандартные наборы выбора задаются по имени при определении представлений файла форматирования. В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` элемента для представления задает набор. Однако в разных записях представления также можно указать набор выбора, который применяется только к этой записи представления. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.

```
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

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Элемент Types (Format)](./types-element-for-selectionset-format.md)

[Написание файла форматирования Windows PowerShell](./writing-a-powershell-formatting-file.md)
