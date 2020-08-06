---
title: Элемент Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 34e20006a7501650f2a22f71a3d7e999fb8b2337
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785138"
---
# <a name="tablecontrol-element-format"></a>Элемент TableControl (формат)

Определяет формат таблицы для представления.

Элемент Виевдефинитионс (Format) View элемент (Format) Таблеконтрол (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableControl` элемента. Необходимо указать строки таблицы. Все остальные дочерние элементы являются необязательными.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент AutoSize для TableControl (формат)](./autosize-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.|
|[Элемент Хидетаблехеадерс для Таблеконтрол (Format)](./hidetableheaders-element-format.md)|Необязательный элемент.<br /><br /> Указывает, не отображается ли заголовок таблицы.|
|[Элемент Таблехеадерс для Таблеконтрол (Format)](./tableheaders-element-format.md)|Обязательный элемент.<br /><br /> Определяет метки, ширину и выравнивание данных для столбцов табличного представления.|
|[Элемент TableRowEntries для элемента TableControl (формат)](./tablerowentries-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Предоставляет определения табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения элементов одного или нескольких объектов.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableControl` элемент, используемый для отображения свойств объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент View (формат)](./view-element-format.md)

[Элемент AutoSize для TableControl (формат)](./autosize-element-for-tablecontrol-format.md)

[Элемент HideTableHeaders (формат)](./hidetableheaders-element-format.md)

[Элемент TableHeaders (формат)](./tableheaders-element-format.md)

[Элемент Таблеровентриес (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
