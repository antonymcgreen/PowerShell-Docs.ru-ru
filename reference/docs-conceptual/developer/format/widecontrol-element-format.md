---
title: Элемент Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b6f19cf94dcb440eeaf53547db407287e5462520
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784985"
---
# <a name="widecontrol-element-format"></a>Элемент WideControl (формат)

Определяет для представления широкий формат списка (одно значение). В этом представлении отображается одно значение свойства или значение скрипта для каждого объекта.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideControl` элемента. Нельзя `AutoSize` одновременно указать элементы и `ColumnNumber` .

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент AutoSize для WideControl (формат)](./autosize-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.|
|[Элемент ColumnNumber для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает число столбцов, отображаемых в расширенном представлении.|
|[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения расширенного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

## <a name="remarks"></a>Примечания

При определении расширенного представления можно добавить `AutoSize` элемент или, `ColumnNumber` но нельзя добавить оба.

В большинстве случаев для каждого расширенного представления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideControl` элемент, используемый для отображения свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)

[Элемент ColumnNumber для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)

[Элемент View (формат)](./view-element-format.md)

[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)

[Широкое представление (базовое)](./wide-view-basic.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
