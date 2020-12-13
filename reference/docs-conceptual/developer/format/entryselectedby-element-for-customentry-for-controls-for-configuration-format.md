---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
description: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666677"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для элемента Ошибка customcontrol для элемента Configuration (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для кустоментри для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования определения общего элемента управления.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, использующих это определение общего элемента управления.|
|[Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение общего элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение общего элемента управления.|

## <a name="remarks"></a>Комментарии

Как минимум, каждому определению должно быть назначено по крайней мере один тип .NET, набор выбора или условие выбора. Максимальное число типов, наборов выбора или условий выбора, которые можно указать, не ограничено.

## <a name="see-also"></a>См. также:

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
