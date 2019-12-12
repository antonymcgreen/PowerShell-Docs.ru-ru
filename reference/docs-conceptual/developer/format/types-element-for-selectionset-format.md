---
title: Элемент Types для набора выбора (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367963"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Types`. Должен существовать хотя бы один дочерний элемент, но максимальное количество дочерних элементов, которое можно добавить, не ограничено.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TypeName типов (Format)](./typename-element-for-types-format.md)|Обязательный элемент.<br /><br /> Указывает объект .NET, который принадлежит набору выбора.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент набора выбора (Format)](./selectionset-element-format.md)|Определяет набор объектов .NET, на которые может ссылаться имя набора.|

## <a name="remarks"></a>Замечания

Объекты, определенные этим элементом, составляют набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.  Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показан элемент `SelectionSet`, определяющий четыре типа .NET.

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

[Определение наборов объектов](./defining-selection-sets.md)

[Элемент набора выбора (Format)](./selectionset-element-format.md)

[Элемент TypeName типов (Format)](./typename-element-for-types-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
