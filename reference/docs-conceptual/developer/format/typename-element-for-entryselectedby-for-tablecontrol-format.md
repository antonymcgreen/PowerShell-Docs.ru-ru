---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)
description: Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651420"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)

Указывает тип .NET, который использует эту запись табличного представления. Количество типов, которое можно указать для записи в таблице, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби элемент (Format) элемент TypeName для Ентриселектедби в TableRowEntry (Format)

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
|[Элемент Ентриселектедби (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, которые используют эту запись, или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя типа .NET.

## <a name="remarks"></a>Комментарии

Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Ентриселектедби (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
