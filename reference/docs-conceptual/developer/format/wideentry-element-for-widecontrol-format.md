---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideEntry для WideControl (формат)
description: Элемент WideEntry для WideControl (формат)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664540"
---
# <a name="wideentry-element-for-widecontrol-format"></a>Элемент WideEntry для WideControl (формат)

Предоставляет определение расширенного представления.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format)

## <a name="syntax"></a>Синтаксис

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntry` элемента. Необходимо указать один `WideItem` дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, которые используют определение расширенной записи или условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипт, значение которого отображается.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)|Предоставляет определения расширенного представления.|

## <a name="remarks"></a>Комментарии

Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта. В отличие от других типов представлений, для каждого определения представления можно указать только один элемент Item. Дополнительные сведения о других компонентах расширенного представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент. `WideItem`Элемент определяет свойство, значение которого отображается в представлении.

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Создание широкого представления](./creating-a-wide-view.md)

[Элемент Селектионкондитион для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент Селектионсетнаме для Видинтри (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент TypeName для Видинтри (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)

[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
