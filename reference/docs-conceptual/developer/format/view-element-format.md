---
title: View, элемент (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361463"
---
# <a name="view-element-format"></a>Элемент View (формат)

Определяет представление, в котором отображается один или несколько объектов .NET. Количество представлений, которые могут быть определены в файле форматирования, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `View`. Необходимо указать один и только один из дочерних элементов элемента управления, а также указать имя представления и объекты, использующие это представление. Определение пользовательских элементов управления, Группировка объектов и указание, являются ли представление внешними, являются необязательными.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Controls для представления (формат)](./controls-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет набор элементов управления, на которые в представлении можно ссылаться по именам.|
|[Элемент ошибка customcontrol (Format)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет формат пользовательского элемента управления для представления.|
|[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет, как группируются элементы объектов .NET.|
|[Элемент ListControl (Format)](./listcontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат списка для представления.|
|[Элемент Name для представления (формат)](./name-element-for-view-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на представление.|
|[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат таблицы для представления.|
|[Элемент Виевселектедби для представления (формат)](./viewselectedby-element-format.md)|Обязательный элемент.<br /><br /> Определяет объекты .NET, отображаемые в этом представлении.|
|[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет для представления широкий формат списка (одно значение).|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Виевдефинитионс (Format)](./viewdefinitions-element-format.md)|Определяет представления, используемые для отображения объектов.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах различных представлений и пользовательских элементов управления см. в следующих разделах:

- [Компоненты табличного представления](./creating-a-table-view.md)

- [Компоненты представления списка](./creating-a-list-view.md)

- [Компоненты расширенного представления](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показан элемент `View`, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

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

## <a name="see-also"></a>См. также:

[Элемент Виевдефинитионс (Format)](./viewdefinitions-element-format.md)

[Элемент Name для представления (формат)](./name-element-for-view-format.md)

[Элемент Виевселектедби (Format)](./viewselectedby-element-format.md)

[Элемент Controls для представления (формат)](./controls-element-for-view-format.md)

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)

[Элемент ListControl (Format)](./listcontrol-element-format.md)

[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)

[Элемент ошибка customcontrol (Format)](./customcontrol-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
