---
title: Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec048408-e1c6-41ef-b39b-72f4c2dcf2ac
caps.latest.revision: 6
ms.openlocfilehash: b4b2440fdb7171d09fdc16ac7cc4f25ed1a4bb78
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362403"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)

Указывает свойство .NET, которое запускает условие. Если это свойство имеется или если оно имеет значение `true`, условие выполняется и используется запись. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат). элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления для элемента конфигурации (Format) Селектионкондитион для Ентриселектедби для Кустоментри конфигурации ( Формат) элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования определения общего элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Замечания

Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
