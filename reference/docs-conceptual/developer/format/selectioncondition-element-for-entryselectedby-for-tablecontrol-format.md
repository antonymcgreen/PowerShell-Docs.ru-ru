---
title: Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368393"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Определяет условие, которое должно существовать для использования в этом определении табличного представления. Количество условий выбора, которое можно указать для определения таблицы, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента Селектионкондитион.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые активируют условие.|
|[Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Таблеровентри (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.|

## <a name="remarks"></a>Замечания

Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Ентриселектедби (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
