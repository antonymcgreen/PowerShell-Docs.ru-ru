---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideEntries для WideControl (формат)
description: Элемент WideEntries для WideControl (формат)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651243"
---
# <a name="wideentries-element-for-widecontrol-format"></a>Элемент WideEntries для WideControl (формат)

Предоставляет определения расширенного представления. В расширенном представлении должно быть указано одно или несколько определений.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntries` элемента. Необходимо указать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение расширенного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="remarks"></a>Комментарии

Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта. Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntries` элемент, определяющий один `WideEntry` элемент. `WideEntry`Элемент содержит единственный `WideItem` элемент, который определяет, какое свойство или значение скрипта отображается в представлении.

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Создание широкого представления](./creating-a-wide-view.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
