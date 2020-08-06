---
title: Элемент PropertyName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 8ada9a8ca7fbfdba5b2fea1881b2670c56a71d4f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773085"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy для селектионкондитион для EntrySelectedBy for GroupBy (формат), для SelectionCondition в качестве элемента GroupBy (формат)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
