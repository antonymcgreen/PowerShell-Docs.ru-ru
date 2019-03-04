---
title: Элемент ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863190"
---
# <a name="viewselectedby-element-format"></a>Элемент ViewSelectedBy (формат)

Определяет объекты .NET, которые отображаются в представлении. Каждое представление необходимо указать хотя бы один объект .NET.

Элемент ViewDefinitions (формат) представления (формат) ViewSelectedBy элемента (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ViewSelectedBy` элемент. Этот элемент должен содержать по крайней мере один `TypeName` или `SelectionSetName` дочерний элемент. Нет ограничений на количество дочерних элементов, которые могут быть указаны и не важен их порядок.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[TypeName-элемент для ViewSelectedBy (формат)](./typename-element-for-viewselectedby-format.md)|Необязательный элемент.<br /><br /> Указывает объект .NET, который отображается в представлении.|
|[Элемент SelectionSetName для ViewSelectedBy (формат)](./selectionsetname-element-for-viewselectedby-format.md)|Необязательный элемент.<br /><br /> Задает набор объектов .NET, которые отображаются в представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое отображает один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о том, как этот элемент используется в различных представлениях см. в разделе [компоненты представлений таблицы](./creating-a-table-view.md), [компоненты представлений списка](./creating-a-list-view.md), [расширенные компоненты представлений](./creating-a-wide-view.md)и [Компоненты пользовательского элемента управления](./creating-custom-controls.md).

`SelectionSetName` Элемент используется в том случае, если файл форматирования определяет набор объектов, которые отображаются по несколько представлений. Дополнительные сведения о как определенные или используемые наборы выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект для представления списка. Ту же схему используется для таблицы, расширенных и настраиваемых представлений.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент SelectionSetName для ViewSelectedBy (формат)](./selectionsetname-element-for-viewselectedby-format.md)

[Имя типа элемента (формат)](./typename-element-for-viewselectedby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
