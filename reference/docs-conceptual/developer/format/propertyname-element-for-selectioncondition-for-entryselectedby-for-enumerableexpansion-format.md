---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783472"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) элемент PropertyName для SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
