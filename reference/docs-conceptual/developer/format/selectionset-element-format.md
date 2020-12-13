---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSet (формат)
description: Элемент SelectionSet (формат)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647876"
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

## <a name="remarks"></a>Комментарии

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

## <a name="see-also"></a>См. также:

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент Name набора выбора (Format)](./name-element-for-selectionset-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Элемент Types (Format)](./types-element-for-selectionset-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
