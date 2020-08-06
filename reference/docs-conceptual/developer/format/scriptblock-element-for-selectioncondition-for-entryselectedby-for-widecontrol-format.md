---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787620"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется расширенное определение записи.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition в EntrySelectedBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Определяет условие, которое должно существовать, чтобы использовать это определение.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкого представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
