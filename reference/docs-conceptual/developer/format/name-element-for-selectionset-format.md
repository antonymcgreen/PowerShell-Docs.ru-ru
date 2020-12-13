---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента SelectionSet (формат)
description: Элемент Name для элемента SelectionSet (формат)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666470"
---
# <a name="name-element-for-selectionset-format"></a>Элемент Name для элемента SelectionSet (формат)

Задает имя, используемое для ссылки на набор выбора.

Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (формат) имя элемента набора выбора (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionSet (формат)](./selectionset-element-format.md)|Определяет один набор объектов .NET, на который может ссылаться имя набора.|

## <a name="text-value"></a>Текстовое значение

Укажите имя для ссылки на набор выбора. Никаких ограничений на то, какие символы можно использовать, не существует.

## <a name="remarks"></a>Комментарии

Указанное здесь имя используется в `SelectionSetName` элементе. Набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET. Имя набора выбора — "Филесистемтипес".

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

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
