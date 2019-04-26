---
title: Элемент SelectionSetName для ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076231"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>Элемент SelectionSetName для элемента ViewSelectedBy (формат)

Задает набор объектов .NET, которые отображаются в представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент ViewSelectedBy (формат) SelectionSetName элемент конфигурации для ViewSelectedBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)|Определяет объекты .NET, которые отображаются в представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора, который определяется `Name` элемент набора выбора.

## <a name="remarks"></a>Замечания

Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование. Дополнительные сведения об определении и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показано задание выбора представления списка. Ту же схему используется для таблицы, расширенных и настраиваемых представлений.

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
