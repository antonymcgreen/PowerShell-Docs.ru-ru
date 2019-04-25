---
title: Элемент WideEntry для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083677"
---
# <a name="wideentry-element-for-widecontrol-format"></a>Элемент WideEntry для WideControl (формат)

Предоставляет определение широкое представление.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideEntry` элемент. Необходимо указать один `WideItem` дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, которые используют это определение расширенных запись или условие, которое должен существовать для данного определения для использования.|
|[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипта, значение которого отображается.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideEntries (формат)](./wideentries-element-for-widecontrol-format.md)|Предоставляет определения широкое представление.|

## <a name="remarks"></a>Замечания

Широкое представление — это формат списка, который отображает значение одного свойства или значение скрипта для каждого объекта. В отличие от других типов представлений можно указать только один элемент для каждого определения представления. Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntry` элемент, который определяет одно `WideItem` элемент. `WideItem` Элемент определяет свойство, значение которого отображается в представлении.

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Элемент SelectionCondition для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для WideEntry (формат)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[TypeName-элемент для WideEntry (формат)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Элемент WideEntries (формат)](./wideentries-element-for-widecontrol-format.md)

[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
