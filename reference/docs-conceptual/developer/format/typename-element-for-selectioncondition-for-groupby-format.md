---
title: Элемент TypeName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ea1e0cb50c3a749f6c26d13fff4b001240ce6b95
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772558"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a>Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)

Указывает тип .NET, который запускает условие. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format). селектионкондитион для EntrySelectedBy for GroupBy в SelectionCondition для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Примечания

Если этот элемент указан, нельзя указать `SelectionSetName` элемент. Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
