---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 71fd969fd3e5c0a4e39762c9a026982a8ca2a9d1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785376"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает скрипт, который запускает условие.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format) элемент ScriptBlock для SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
