---
title: Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362013"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy Енумерабликспансион (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`. Необходимо указать один элемент `PropertyName` или `ScriptBlock`. Элементы `SelectionSetName` и `TypeName` необязательны. Можно указать один из этих элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Енумерабликспансион (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|Определяет, какие объекты коллекции .NET разворачиваются этим определением.|

## <a name="remarks"></a>Замечания

Каждое определение должно иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для воспроизведения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также:

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
