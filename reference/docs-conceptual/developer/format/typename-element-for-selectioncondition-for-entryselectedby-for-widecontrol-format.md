---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5021f665b994581f9ff982e13af922d7940ebf2b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783319"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Указывает тип .NET, который запускает условие. При наличии этого типа используется определение.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition (Format).

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
|[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Определяет условие, которое должно существовать для использования этой широкой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Примечания

Условие выбора может указывать тип .NET или набор выбора, но не может указывать и то, и другое. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкого представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
