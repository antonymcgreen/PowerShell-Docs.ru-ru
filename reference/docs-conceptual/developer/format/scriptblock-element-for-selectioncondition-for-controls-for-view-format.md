---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)
ms.openlocfilehash: 7eed3b8a06bc45396026b8e2a7454447b3090d74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664945"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется определение. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) Кустоментри элемент для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления представления (Format) элемент ScriptBlock для SelectionCondition для элементов управления View (формат)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Комментарии

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
