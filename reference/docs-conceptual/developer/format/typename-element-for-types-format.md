---
title: Элемент TypeName для типов (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368033"
---
# <a name="typename-element-for-types-format"></a>Элемент TypeName для элемента Types (формат)

Указывает тип .NET объекта, который принадлежит к набору выбора.

Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types элемент (Format) имя_типа Types (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`. В набор выбора необходимо включать по крайней мере один элемент `TypeName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Types (Format)](./types-element-for-selectionset-format.md)|Определяет объекты .NET, которые находятся в наборе выбора.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя для типа .NET.

## <a name="remarks"></a>Замечания

Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование. При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.

Стандартные наборы выбора задаются по имени при определении представлений файла форматирования. В этих случаях дочерний элемент `SelectionSetName` элемента `ViewSelectedBy` для представления задает набор. Однако в разных записях представления также можно указать набор выбора, который применяется только к этой записи представления. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `SelectionSet`, определяющий четыре типа .NET.

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

## <a name="see-also"></a>См. также:

[Определение наборов выбора](./defining-selection-sets.md)

[Элемент набора выбора (Format)](./selectionset-element-format.md)

[Элемент Селектионсетс (Format)](./selectionsets-element-format.md)

[Элемент Types (Format)](./types-element-for-selectionset-format.md)

[Запись файла форматирования Windows PowerShell](./writing-a-powershell-formatting-file.md)
