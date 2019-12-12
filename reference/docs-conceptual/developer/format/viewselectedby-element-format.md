---
title: Элемент Виевселектедби (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367973"
---
# <a name="viewselectedby-element-format"></a>Элемент ViewSelectedBy (формат)

Определяет объекты .NET, отображаемые представлением. Каждое представление должно содержать по крайней мере один объект .NET.

Элемент Виевдефинитионс (Format) View элемент (Format) Виевселектедби (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ViewSelectedBy`. Этот элемент должен содержать по крайней мере один `TypeName` или `SelectionSetName` дочерний элемент. Количество дочерних элементов, которые можно указать, не ограничено, а их порядок не является значимым.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TypeName для Виевселектедби (Format)](./typename-element-for-viewselectedby-format.md)|Необязательный элемент.<br /><br /> Задает объект .NET, отображаемый представлением.|
|[Элемент Селектионсетнаме для Виевселектедби (Format)](./selectionsetname-element-for-viewselectedby-format.md)|Необязательный элемент.<br /><br /> Задает набор объектов .NET, отображаемых представлением.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, в котором отображается один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

Дополнительные сведения об использовании этого элемента в различных представлениях см. в разделе [компоненты табличного](./creating-a-table-view.md)представления, [Компоненты представления списка](./creating-a-list-view.md), [компоненты расширенного представления](./creating-a-wide-view.md)и [компоненты пользовательского элемента управления](./creating-custom-controls.md).

Элемент `SelectionSetName` используется, когда файл форматирования определяет набор объектов, отображаемых несколькими представлениями. Дополнительные сведения о том, как определяются и указываются наборы выбора, см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка. Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Создание табличного представления](./creating-a-table-view.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Определение наборов выбора](./defining-selection-sets.md)

[Элемент Селектионсетнаме для Виевселектедби (Format)](./selectionsetname-element-for-viewselectedby-format.md)

[Элемент TypeName (Format)](./typename-element-for-viewselectedby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
