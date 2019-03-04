---
title: Элемент WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859830"
---
# <a name="widecontrol-element-format"></a>Элемент WideControl (формат)

Большое (значение одно значение) определяет формат списка для представления. Это представление отображает значение одного свойства или значение скрипта для каждого объекта.

Элемент элемента (формат) WideControl для элемента (формат) элемент ViewDefinitions (формат) конфигурации представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideControl` элемент. Нельзя указать `AutoSize` и `ColumnNumber` элементы, в то же время.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[AutoSize-элемент для WideControl (формат)](./autosize-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.|
|[ColumnNumber-элемент для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает количество столбцов, отображаемых в широком представлении.|
|[Элемент WideEntries (формат)](./wideentries-element-for-widecontrol-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения широкое представление.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое используется для отображения один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

При определении широкое представление, можно добавить `AutoSize` элемент или `ColumnNumber` , но нельзя добавить одновременно.

В большинстве случаев только одно определение является обязательным для каждого широкое представление, но можно иметь несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET. В таком случае можно задать отдельный определение для каждого объекта или набора объектов.

Дополнительные сведения о компонентах широкое представление, см. в разделе [расширенные компоненты представлений](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideControl` элемент, который используется для отображения свойства [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[AutoSize-элемент для WideControl (формат)](./autosize-element-for-widecontrol-format.md)

[ColumnNumber-элемент для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)

[Элемент представления (формат)](./view-element-format.md)

[Элемент WideEntries (формат)](./wideentries-element-for-widecontrol-format.md)

[Широкое представление (Basic)](./wide-view-basic.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
