---
title: TableControl-элемент (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: dd48e82452e83f93e2e005c9db53bbc51d8b2eb4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858920"
---
# <a name="tablecontrol-element-format"></a>Элемент TableControl (формат)

Определяет формат таблицы для представления.

TableControl-элемент элемента (формат) элемент ViewDefinitions (формат) представления (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TableControl` элемент. Необходимо указать строки таблицы. Все дочерние элементы являются необязательными.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[AutoSize-элемент для TableControl (формат)](./autosize-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.|
|[Элемент HideTableHeaders для TableControl (формат)](./hidetableheaders-element-format.md)|Необязательный элемент.<br /><br /> Указывает, отображается ли заголовок таблицы.|
|[Элемент TableHeaders для TableControl (формат)](./tableheaders-element-format.md)|Обязательный элемент.<br /><br /> Определяет, метки, значения ширины и выравнивания данных для столбцов представления таблицы.|
|[Элемент TableRowEntries для TableCotrol (формат)](./tablerowentries-element-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Предоставляет определения представления таблицы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое используется для отображения элементов из одного или нескольких объектов.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показано `TableControl` элемент, который используется для отображения свойств [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.

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

[Элемент представления (формат)](./view-element-format.md)

[AutoSize-элемент для TableControl (формат)](./autosize-element-for-tablecontrol-format.md)

[Элемент HideTableHeaders (формат)](./hidetableheaders-element-format.md)

[Элемент TableHeaders (формат)](./tableheaders-element-format.md)

[Элемент TableRowEntries (формат)](./tablerowentries-element-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
