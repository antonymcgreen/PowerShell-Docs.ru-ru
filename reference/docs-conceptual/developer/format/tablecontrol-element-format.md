---
title: Элемент Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368203"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableControl`. Необходимо указать строки таблицы. Все остальные дочерние элементы являются необязательными.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент AutoSize для Таблеконтрол (Format)](./autosize-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.|
|[Элемент Хидетаблехеадерс для Таблеконтрол (Format)](./hidetableheaders-element-format.md)|Необязательный элемент.<br /><br /> Указывает, не отображается ли заголовок таблицы.|
|[Элемент Таблехеадерс для Таблеконтрол (Format)](./tableheaders-element-format.md)|Обязательный элемент.<br /><br /> Определяет метки, ширину и выравнивание данных для столбцов табличного представления.|
|[Элемент Таблеровентриес для Таблеконтрол (Format)](./tablerowentries-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Предоставляет определения табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, используемое для отображения элементов одного или нескольких объектов.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `TableControl`, используемый для отображения свойств объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

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

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[View, элемент (Format)](./view-element-format.md)

[Элемент AutoSize для Таблеконтрол (Format)](./autosize-element-for-tablecontrol-format.md)

[Элемент Хидетаблехеадерс (Format)](./hidetableheaders-element-format.md)

[Элемент Таблехеадерс (Format)](./tableheaders-element-format.md)

[Элемент Таблеровентриес (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
