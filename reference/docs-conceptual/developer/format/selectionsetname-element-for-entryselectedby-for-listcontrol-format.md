---
title: Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4315d81da4ceeb7a5b171087434ae15fb09e6592
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785274"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)

Задает набор объектов .NET для записи списка. Количество наборов выбора, которые можно указать для записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионсетнаме для EntrySelectedBy в ListEntry (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
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
|[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как задать набор выбора для записи в представлении списка.

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
