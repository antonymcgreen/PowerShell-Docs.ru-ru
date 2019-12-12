---
title: Элемент Ентриселектедби для Листентри для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363833"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)

Определяет типы .NET, которые используют это определение представления списка или условие, которое должно существовать, чтобы использовать это определение. В большинстве случаев для представления списка требуется только одно определение. Однако можно указать несколько определений для представления списка, если вы хотите использовать одно и то же представление списка для отображения различных данных для разных объектов.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентри для ListControl (Format) Ентриселектедби элемент для Листентри для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение представления списка.|
|[Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение представления списка.|
|[Элемент TypeName для Ентриселектедби для ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентри для ListControl (Format)](./listentry-element-for-listcontrol-format.md)|Определяет, как отображаются строки списка.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения представления списка. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта оценивается как `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как определить объекты для представления списка с помощью имени типа .NET.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>См. также:

[Элемент Листентри для ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент TypeName для Ентриселектедби для ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
