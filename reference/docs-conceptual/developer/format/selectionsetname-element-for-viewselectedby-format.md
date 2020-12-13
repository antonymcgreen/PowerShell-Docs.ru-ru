---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента ViewSelectedBy (формат)
description: Элемент SelectionSetName для элемента ViewSelectedBy (формат)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654903"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>Элемент SelectionSetName для элемента ViewSelectedBy (формат)

Задает набор объектов .NET, отображаемых представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби элемент (Format) Селектионсетнаме для Виевселектедби (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)|Определяет объекты .NET, отображаемые представлением.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора, который определяется `Name` элементом для набора выбора.

## <a name="remarks"></a>Комментарии

Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование. Дополнительные сведения об определении и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показано, как задать набор выбора для представления списка. Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также:

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
