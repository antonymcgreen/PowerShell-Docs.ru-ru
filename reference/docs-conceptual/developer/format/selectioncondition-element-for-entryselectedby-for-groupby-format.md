---
title: Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0930d8076c314c12cac6cdfa2b33716b7efeb6a9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772847"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)

Определяет условие, которое должно существовать для использования определения элемента управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format) селектионкондитион для EntrySelectedBy for GroupBy (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)](./propertyname-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для GroupBy (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион для GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.|

## <a name="remarks"></a>Примечания

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент TypeName для Селектионкондитион для GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
