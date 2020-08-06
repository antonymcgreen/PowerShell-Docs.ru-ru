---
title: Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 52858dba5c7a5222b5410835f3374546ce8b88a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785359"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)

Определяет условие, которое должно существовать для использования определения элемента управления. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) кустомитем для кустоментри для ошибка customcontrol для представления (Format) ошибка customcontrol элемент для для, чтобы просмотреть (Format) ентриселектедби для CustomEntry для ошибка customcontrol для представления (формат).

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
|[Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.|

## <a name="remarks"></a>Примечания

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент TypeName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
