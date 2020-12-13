---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 5e4368a9546307c5ff223ae42ecaa1d2872bc587
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665963"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) контролирует элемент элемента управления конфигурации (Format) для элементов управления для элемента конфигурации (Format) ошибка customcontrol для элемента управления в элементе конфигурации (Format) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления для элемента конфигурации (Format) Селектионкондитион для Ентриселектедби для CustomEntry для элемента конфигурации (Format) PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования определения общего элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Комментарии

Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
