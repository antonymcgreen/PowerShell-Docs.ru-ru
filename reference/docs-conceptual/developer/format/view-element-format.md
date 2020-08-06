---
title: View, элемент (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785036"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `View` элемента. Необходимо указать один и только один из дочерних элементов элемента управления, а также указать имя представления и объекты, использующие это представление. Определение пользовательских элементов управления, Группировка объектов и указание, являются ли представление внешними, являются необязательными.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Controls для элемента View (формат)](./controls-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет набор элементов управления, на которые в представлении можно ссылаться по именам.|
|[Элемент ошибка customcontrol (Format)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет формат пользовательского элемента управления для представления.|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет, как группируются элементы объектов .NET.|
|[Элемент ListControl (формат)](./listcontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат списка для представления.|
|[Элемент Name для элемента View (формат)](./name-element-for-view-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на представление.|
|[Элемент TableControl (формат)](./tablecontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет формат таблицы для представления.|
|[Элемент Виевселектедби для представления (формат)](./viewselectedby-element-format.md)|Обязательный элемент.<br /><br /> Определяет объекты .NET, отображаемые в этом представлении.|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Необязательный элемент.<br /><br /> Определяет для представления широкий формат списка (одно значение).|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)|Определяет представления, используемые для отображения объектов.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о компонентах различных представлений и пользовательских элементов управления см. в следующих разделах:

- [Компоненты табличного представления](./creating-a-table-view.md)

- [Компоненты представления списка](./creating-a-list-view.md)

- [Компоненты расширенного представления](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

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

[Элемент Name для элемента View (формат)](./name-element-for-view-format.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Элемент Controls для элемента View (формат)](./controls-element-for-view-format.md)

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Элемент TableControl (формат)](./tablecontrol-element-format.md)

[Элемент ListControl (формат)](./listcontrol-element-format.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Элемент ошибка customcontrol (Format)](./customcontrol-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
