---
title: Элемент WideEntries для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083694"
---
# <a name="wideentries-element-for-widecontrol-format"></a>Элемент WideEntries для WideControl (формат)

Предоставляет определения широкое представление. Широкое представление необходимо указать одно или несколько определений.

Элемент WideControl элемент (формат) WideEntries ViewDefinitions элемент (формат) представление конфигурации элемента (формат) элемент (формат) (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideEntries` элемент. Необходимо указать хотя бы один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение широкое представление.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Большое (значение одно значение) определяет формат списка для представления.|

## <a name="remarks"></a>Замечания

Широкое представление — это формат списка, который отображает значение одного свойства или значение скрипта для каждого объекта. Дополнительные сведения о компонентах широкое представление, см. в разделе [расширенные компоненты представлений](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntries` элемент, который определяет одно `WideEntry` элемент. `WideEntry` Элемент содержит один `WideItem` элемент, который определяет, какое значение свойства или скрипт отображается в представлении.

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
