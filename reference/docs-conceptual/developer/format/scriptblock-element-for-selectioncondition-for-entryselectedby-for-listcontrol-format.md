---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368593"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта в `true` условие выполняется, и используется запись списка.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион элемент для Ентриселектедби для Листентри (Format) элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)

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
|[Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи списка.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Замечания

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. (Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md).)

Дополнительные сведения о других компонентах представления списка см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также:

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
