---
title: Элемент Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363333"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>Элемент EntrySelectedBy для элемента WideEntry (формат)

Определяет типы .NET, которые используют это определение расширенного представления или условие, которое должно существовать, чтобы использовать это определение.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования в этом расширенном определении представления.|
|[Элемент Селектионсетнаме для Ентриселектедби для Видинтри (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, использующих это определение в масштабах представления.|
|[Элемент TypeName для Ентриселектедби для Видинтри (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение в масштабе представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение расширенного представления.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для расширенного определения представления. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если объект имеет определенное свойство или значение конкретного свойства или значения скрипта, равное `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также:

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Видинтри (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент TypeName для Ентриселектедби для Видинтри (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
