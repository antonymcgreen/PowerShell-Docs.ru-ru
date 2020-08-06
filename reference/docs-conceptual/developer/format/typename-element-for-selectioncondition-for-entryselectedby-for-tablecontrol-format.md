---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b9367f0ea659b9dce8fe200a5a08873d53bc03a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772592"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает тип .NET, который запускает условие. При наличии этого типа условие выполняется, и используется строка таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition (Format).

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должно существовать для использования этой строки таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Примечания

Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
