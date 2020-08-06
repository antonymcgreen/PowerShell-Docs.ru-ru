---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772864"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта выполняется `true` условие, и используется запись списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)

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
|[Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи списка.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. (Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md).)

Дополнительные сведения о других компонентах представления списка см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
