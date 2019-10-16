---
title: Элемент Селектионсетнаме для Селектионкондитион для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368273"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри представления (Format)

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
|[Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выбора](./defining-selection-sets.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
