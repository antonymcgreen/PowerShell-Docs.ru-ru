---
title: Элемент Name для набора выбора (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362673"
---
# <a name="name-element-for-selectionset-format"></a>Элемент Name для элемента SelectionSet (формат)

Задает имя, используемое для ссылки на набор выбора.

Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (формат) имя элемента набора выбора (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент набора выбора (Format)](./selectionset-element-format.md)|Определяет один набор объектов .NET, на который может ссылаться имя набора.|

## <a name="text-value"></a>Текстовое значение

Укажите имя для ссылки на набор выбора. Никаких ограничений на то, какие символы можно использовать, не существует.

## <a name="remarks"></a>Замечания

Указанное здесь имя используется в элементе `SelectionSetName`. Набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показан элемент `SelectionSet`, определяющий четыре типа .NET. Имя набора выбора — "Филесистемтипес".

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

[Определение наборов выбора](./defining-selection-sets.md)

[Элемент набора выбора (Format)](./selectionset-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
