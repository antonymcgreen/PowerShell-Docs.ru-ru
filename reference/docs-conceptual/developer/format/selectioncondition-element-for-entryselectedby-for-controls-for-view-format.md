---
title: Элемент Селектионкондитион для Ентриселектедби элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362053"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)

Определяет условие, которое должно существовать для использования определения элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элементов управления для представления (Format) Кустоментри для Кустоментриес для элементов управления для представления (Format) Ентриселектедби элемента для Кустоментри для элементов управления для представления (формат) Селектионкондитион для элементов управления для представления ( Формат

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион элементов управления для представления (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион элементов управления для представления (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион элементов управления для представления (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.|

## <a name="remarks"></a>Замечания

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент PropertyName для Селектионкондитион элементов управления для представления (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для Селектионкондитион элементов управления для представления (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент TypeName для Селектионкондитион элементов управления для представления (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
