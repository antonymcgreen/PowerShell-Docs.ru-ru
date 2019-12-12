---
title: Элемент Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364783"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Определяет условие, которое должно существовать, чтобы использовать это определение. Количество условий выбора, которое можно указать для определения расширенной записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион элемент для Ентриселектедби для Видинтри (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`. Необходимо указать один элемент `PropertyName` или `ScriptBlock`. Элементы `SelectionSetName` и `TypeName` необязательны. Можно указать один из этих элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает блок скрипта, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Видинтри (Format)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.|

## <a name="remarks"></a>Замечания

Для каждой широкой записи должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также:

[Создание расширенного представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Ентриселектедби для Видинтри (Format)](./entryselectedby-element-for-wideentry-format.md)

[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
