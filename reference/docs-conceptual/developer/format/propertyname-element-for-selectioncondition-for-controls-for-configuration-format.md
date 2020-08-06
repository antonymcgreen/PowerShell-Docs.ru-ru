---
title: Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7730951a840fcfcd8bf819fff5182049bd6b6c23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773136"
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

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
