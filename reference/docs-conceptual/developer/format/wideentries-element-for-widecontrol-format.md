---
title: Элемент Видинтриес для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361433"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideEntries`. Необходимо указать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение расширенного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="remarks"></a>Замечания

Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта. Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `WideEntries`, определяющий один элемент `WideEntry`. Элемент `WideEntry` содержит один элемент `WideItem`, который определяет, какое свойство или значение скрипта отображается в представлении.

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

[Создание расширенного представления](./creating-a-wide-view.md)

[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
