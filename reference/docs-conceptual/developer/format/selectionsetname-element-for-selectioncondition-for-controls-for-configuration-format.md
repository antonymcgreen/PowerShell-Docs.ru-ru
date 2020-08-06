---
title: Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 62f186be9e4b1dd5a297add0ce82011bc1ccdcd1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785240"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) контролирует элемент элемента управления конфигурации (Format) для элементов управления элемента конфигурации (Format) ошибка customcontrol для элемента управления для элемента Configuration (Format) Кустоментриес для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента Configuration (Format) Ентриселектедби для Кустоментри для элементов управления в элементе конфигурации (Format) Селектионкондитион для Ентриселектедби для элементов управления для элемента конфигурации (Format) SelectionSetName для SelectionCondition для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
