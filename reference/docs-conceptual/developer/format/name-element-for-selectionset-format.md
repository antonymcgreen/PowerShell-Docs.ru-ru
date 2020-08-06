---
title: Элемент Name для набора выбора (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1fc33eeb87a6912ed6793629ab1969cd65b5f0c5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773306"
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

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
