---
title: Элемент ScriptBlock для Селектионкондитион для элементов управления Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785444"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется определение. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) контролирует элемент элемента управления конфигурации (Format) для элементов управления для элемента конфигурации (Format) ошибка customcontrol для элемента управления в элементе конфигурации (Format) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления в элементе конфигурации (Format) Селектионкондитион для Ентриселектедби для элементов управления для элемента конфигурации (Format) элемент ScriptBlock для SelectionCondition для элементов управления конфигурации (Format)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования определения общего элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
