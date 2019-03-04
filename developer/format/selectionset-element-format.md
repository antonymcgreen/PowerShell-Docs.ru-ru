---
title: Элемент SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861160"
---
# <a name="selectionset-element-format"></a>Элемент SelectionSet (формат)

Определяет набор объектов .NET, которые можно ссылаться по имени набора.

SelectionSet элемент SelectionSets (формат) элемент (формат) для конфигурации элемента (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSet` элемент. Каждого набора должны иметь имена, и он должен указать объекты .NET из набора.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name описания SelectionSet (формат)](./name-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Указывает имя, используемое для ссылки на наборе выбора.|
|[Типы элемента (формат)](./types-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Определяет объекты .NET, заданных в выделении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Формат SelectionSets элемент](./selectionsets-element-format.md)|Определяет общие наборы объектов .NET, которые могут использоваться все представления файла форматирования.|

## <a name="remarks"></a>Замечания

Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование. При определении представления, можно указать набор объектов, используя имя выбора вместо перечисления всех объектов в каждом представлении.

Общие наборы выбора указываются по имени, при определении представлений для форматирования файла или определения представления. В этих случаях `SelectionSetName` дочерний элемент элемента `ViewSelectedBy` и `EntrySelectedBy` элементов указывает набор, который требуется использовать. Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показан `SelectionSet` элемент, который определяет четыре типа .NET.

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

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент Name из SelectionSet (формат)](./name-element-for-selectionset-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Типы элемента (формат)](./types-element-for-selectionset-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
