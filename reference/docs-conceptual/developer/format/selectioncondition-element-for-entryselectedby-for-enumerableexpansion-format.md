---
title: Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d5858145e092dc962174a776889a4f62db366d71
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785342"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента. Необходимо указать один `PropertyName` `ScriptBlock` элемент или. `SelectionSetName`Элементы и `TypeName` являются необязательными. Можно указать один из этих элементов.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)|Определяет, какие объекты коллекции .NET разворачиваются этим определением.|

## <a name="remarks"></a>Примечания

Каждое определение должно иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для воспроизведения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
