---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e70e1555a8f2fe0d15d3e864d80d35527af81b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785393"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется определение. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (Format) ентриселектедби для кустоментри for GroupBy (формат). элемент селектионкондитион для для EntrySelectedBy для SelectionCondition for GroupBy (формат)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
