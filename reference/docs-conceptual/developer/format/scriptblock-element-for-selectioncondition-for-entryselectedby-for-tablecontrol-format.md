---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368583"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает блок скрипта, который запускает условие. При вычислении этого скрипта в `true` условие выполняется, и используется запись таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) Элемент Селектионкондитион для Ентриселектедби для элемента ScriptBlock Таблеровентри (Format) для Селектионкондитион для ентриселектедби в TableRowEntry (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Замечания

Условие выбора должно указывать по крайней мере один блок скрипта или имя свойства, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
