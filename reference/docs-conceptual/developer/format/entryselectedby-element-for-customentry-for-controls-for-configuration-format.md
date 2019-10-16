---
title: Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368773"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
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
|[Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования определения общего элемента управления.|
|[Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, использующих это определение общего элемента управления.|
|[Элемент TypeName для Ентриселектедби для элементов управления конфигурации (Format)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение общего элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение общего элемента управления.|

## <a name="remarks"></a>Замечания

Как минимум, каждому определению должно быть назначено по крайней мере один тип .NET, набор выбора или условие выбора. Максимальное число типов, наборов выбора или условий выбора, которые можно указать, не ограничено.

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Элемент TypeName для Ентриселектедби для элементов управления конфигурации (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
