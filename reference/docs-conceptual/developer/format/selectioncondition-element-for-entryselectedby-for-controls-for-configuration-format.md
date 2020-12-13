---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645783"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должно существовать для использования определения общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) ентриселектедби для кустоментри для элементов управления конфигурации (Format) селектионкондитион для ентриселектедби для CustomEntry для конфигурации (Format).

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Определяет типы .NET, которые используют эту запись определения общего элемента управления.|

## <a name="remarks"></a>Комментарии

При определении условия выбора необходимо следовать приведенным ниже рекомендациям.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
