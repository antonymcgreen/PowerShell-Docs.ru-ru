---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 78b977548243b6f3a658f15a0249d8cad12e2f1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664928"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется определение. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) ошибка customcontrol элемента для для с представления (Format) кустомитем для кустоментри для ошибка customcontrol для представления (Format) селектионкондитион для EntrySelectedBy для ошибка customcontrol для представления (формат).

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
|[Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Комментарии

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
