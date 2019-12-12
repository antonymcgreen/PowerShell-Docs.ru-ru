---
title: Элемент Селектионсетнаме для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361863"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy для Кустоментри для GroupBy (Format) Селектионкондитион элемента для Ентриселектедби для элемента селектионсетнаме в SelectionCondition для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Если этот элемент указан, нельзя указать элемент [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) . Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент TypeName для Селектионкондитион для GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выбора](./defining-selection-sets.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
