---
title: TypeName-элемент для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 3f0c0ba1fe85d70557e67a30b3a9a59a33043475
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856110"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a>Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)

Указывает тип .NET, который использует эту операцию в представлении списка. Нет ограничений на число типов, которые могут быть указаны для записи в списке.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента TypeName ListEntry (формат) для EntrySelectedBy для ListControl (формат)

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
|[Элемент EntrySelectedBy для ListEntry (формат)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Определяет типы .NET, использующих этот элемент списка или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Дополнительные сведения о том, как этот элемент используется в виде списка, см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано задание выбора для записи представления списка.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Элемент EntrySelectedBy для ListEntry (формат)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Элемент SelectionSetName для EnrtySelectedBy для ListEntry (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
