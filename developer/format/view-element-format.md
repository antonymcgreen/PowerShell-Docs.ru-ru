---
title: Просмотреть элемент (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083728"
---
# <a name="view-element-format"></a>Элемент View (формат)

Определяет представление, которое отображает один или несколько объектов .NET. Нет ограничений на количество представлений, которые могут быть определены в файле форматирования.

Элемент представления ViewDefinitions элемент (формат) конфигурации элемент (формат) (формат)

## <a name="syntax"></a>Синтаксис

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `View` элемент. Необходимо указать один и только один из дочерних элементов управления, и необходимо указать имя представления и объекты, используемые представления. Определение пользовательских элементов управления, как группировать объекты и указание, если это представление является out of band являются необязательными.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления для представления (формат)](./controls-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет набор элементов управления, которые можно ссылаться по имени в представлении.|
|[Пользовательский элемент управления элемент (формат)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет формат для представления пользовательского элемента управления.|
|[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет, каким образом группируются члены объектов .NET.|
|[Элемент ListControl (формат)](./listcontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат для представления списка.|
|[Элемент Name описания представления (формат)](./name-element-for-view-format.md)|Обязательный элемент.<br /><br /> Указывает имя, используемое для ссылки на представление.|
|[TableControl-элемент (формат)](./tablecontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат таблицы для представления.|
|[Элемент ViewSelectedBy для представления (формат)](./viewselectedby-element-format.md)|Обязательный элемент.<br /><br /> Определяет, в этом представлении отображаются объекты .NET.|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Необязательный элемент.<br /><br /> Большое (значение одно значение) определяет формат списка для представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)|Определяет представления для отображения объектов.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах различные представления и пользовательские элементы управления см. в разделах:

- [Компоненты представлений таблицы](./creating-a-table-view.md)

- [Компоненты представлений списка](./creating-a-list-view.md)

- [Широкое представление компонентов](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показано `View` элемент, который определяет представление таблицы для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>См. также

[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)

[Элемент Name описания представления (формат)](./name-element-for-view-format.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Элемент управления для представления (формат)](./controls-element-for-view-format.md)

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[TableControl-элемент (формат)](./tablecontrol-element-format.md)

[Элемент ListControl (формат)](./listcontrol-element-format.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Пользовательский элемент управления элемент (формат)](./customcontrol-element-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
