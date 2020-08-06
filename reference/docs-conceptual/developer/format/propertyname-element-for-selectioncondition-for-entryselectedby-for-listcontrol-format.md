---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785563"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)

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
|[Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи списка.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Примечания

Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
