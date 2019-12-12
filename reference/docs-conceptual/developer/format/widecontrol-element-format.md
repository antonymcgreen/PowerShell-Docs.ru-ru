---
title: Элемент Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367993"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideControl`. Нельзя одновременно указать элементы `AutoSize` и `ColumnNumber`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.|
|[Элемент ColumnNumber для Видеконтрол (Format)](./columnnumber-element-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает число столбцов, отображаемых в расширенном представлении.|
|[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения расширенного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

## <a name="remarks"></a>Замечания

При определении расширенного представления можно добавить элемент `AutoSize` или `ColumnNumber` но нельзя добавить оба.

В большинстве случаев для каждого расширенного представления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `WideControl`, который используется для отображения свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

## <a name="see-also"></a>См. также:

[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)

[Элемент ColumnNumber для Видеконтрол (Format)](./columnnumber-element-for-widecontrol-format.md)

[View, элемент (Format)](./view-element-format.md)

[Элемент Видинтриес (Format)](./wideentries-element-for-widecontrol-format.md)

[Широкой вид (базовый)](./wide-view-basic.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
