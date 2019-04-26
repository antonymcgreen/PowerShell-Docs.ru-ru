---
title: Элемент EntrySelectedBy для ListEntry для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066198"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)

Определяет типы .NET, использующих это определение представления списка или условие, которое должен существовать для данного определения для использования. В большинстве случаев требуется только одно определение представления списка. Тем не менее можно предоставить несколько определений для представления списка, если вы хотите использовать же представлении списка для отображения разных данных для различных объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntry для EntrySelectedBy элемента ListControl (формат) ListEntry для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения представления списка для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение представления списка.|
|[TypeName-элемент для EntrySelectedBy для ListControl (формат)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntry для ListControl (формат)](./listentry-element-for-listcontrol-format.md)|Определяет способ отображения списка строк.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, выбора или условию выбора определения представления списка. Не ограничено максимальное число дочерних элементов, которые можно использовать.

Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как для определения объектов для представления списка, используя их имя типа .NET.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>См. также

[Элемент ListEntry для ListControl (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[TypeName-элемент для EntrySelectedBy для ListControl (формат)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
