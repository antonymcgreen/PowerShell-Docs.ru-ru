---
title: Элемент набора выбора (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368383"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSet`. Каждый набор выбора должен иметь имя и должен указывать объекты .NET набора.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name для набора выбора (Format)](./name-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на набор выбора.|
|[Элемент Types (Format)](./types-element-for-selectionset-format.md)|Обязательный элемент.<br /><br /> Определяет объекты .NET, которые находятся в наборе выбора.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Формат элемента Селектионсетс](./selectionsets-element-format.md)|Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.|

## <a name="remarks"></a>Замечания

Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование. При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.

Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений. В таких случаях `SelectionSetName` дочерний элемент элементов `ViewSelectedBy` и `EntrySelectedBy` задает используемый набор. Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `SelectionSet`, определяющий четыре типа .NET.

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

[Элемент Name набора выбора (Format)](./name-element-for-selectionset-format.md)

[Элемент Селектионсетс (Format)](./selectionsets-element-format.md)

[Элемент Types (Format)](./types-element-for-selectionset-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
