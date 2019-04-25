---
title: TypeName-элемент для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083966"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)

Указывает тип .NET, который использует эту операцию представления таблицы. Нет ограничений на число типов, которые могут быть указаны для записи таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент EntrySelectedBy (формат) TypeName элемент конфигурации для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, использующих эту запись или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя типа .NET.

## <a name="remarks"></a>Замечания

Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент EntrySelectedBy (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
