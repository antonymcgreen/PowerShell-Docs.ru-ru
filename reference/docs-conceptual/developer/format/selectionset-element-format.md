---
title: Элемент набора выбора (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783404"
---
# <a name="selectionset-element-format"></a>Элемент SelectionSet (формат)

Определяет набор объектов .NET, на которые может ссылаться имя набора.

Элемент Configuration (Format) Селектионсетс элемент (Format) набор выбора (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSet` элемента. Каждый набор выбора должен иметь имя и должен указывать объекты .NET набора.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name для элемента SelectionSet (формат)](./name-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на набор выбора.|
|[Элемент Types (Format)](./types-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Определяет объекты .NET, которые находятся в наборе выбора.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Формат элемента Селектионсетс](./selectionsets-element-format.md)|Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.|

## <a name="remarks"></a>Примечания

Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование. При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.

Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений. В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` `EntrySelectedBy` элементов и указывает используемый набор. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.

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

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент Name набора выбора (Format)](./name-element-for-selectionset-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Элемент Types (Format)](./types-element-for-selectionset-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
