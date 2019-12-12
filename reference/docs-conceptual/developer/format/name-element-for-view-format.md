---
title: Элемент Name для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362643"
---
# <a name="name-element-for-view-format"></a>Элемент Name для элемента View (формат)

Задает имя, используемое для указания представления.

Элемент Configuration (Format) Виевдефинитионс элемент (Format) View элемент (Format) имя элемента (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`. Для каждого представления допускается только один элемент `Name`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, используемое для отображения элементов одного или нескольких объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите уникальное понятное имя для представления. Это имя может включать ссылку на тип представления (например, представление таблицы или представление списка), какой объект или набор объектов использует представление, какая команда возвращает объекты или их сочетание.

## <a name="remarks"></a>Замечания

Дополнительные сведения о различных типах представлений см. в следующих разделах: [представление таблицы](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [Расширенное представление](./creating-a-wide-view.md)и [пользовательское представление](./creating-custom-controls.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `View`, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . Имя представления — "служба".

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Создание табличного представления](./creating-a-table-view.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[View, элемент (Format)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
