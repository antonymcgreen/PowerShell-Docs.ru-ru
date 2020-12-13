---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645558"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает тип .NET, который запускает условие. При наличии этого типа используется запись списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для листентриес для ListControl (Format) ентриселектедби для листентри for ListControl (формат) селектионкондитион элемента for EntrySelectedBy for ListControl для SelectionCondition (Format).

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи списка.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Комментарии

Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
