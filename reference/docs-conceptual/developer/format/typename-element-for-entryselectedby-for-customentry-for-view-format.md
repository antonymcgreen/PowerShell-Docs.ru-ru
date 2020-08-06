---
title: Элемент TypeName для Ентриселектедби для Кустоментри для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: f8dc2c808e6eb3d6a7873cdbddc936b95d94c541
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785104"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)

Указывает тип .NET, который использует это определение представления пользовательского элемента управления. Количество типов, которое можно указать для определения, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления кустоментри для кустоментриес для представления (Format) ентриселектедби для кустоментри для EntrySelectedBy для представления (формат).

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
|[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, которые используют это определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Примечания

Для каждого определения представления пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
