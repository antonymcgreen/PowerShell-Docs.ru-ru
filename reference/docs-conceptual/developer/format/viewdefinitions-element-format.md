---
title: Элемент Виевдефинитионс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361423"
---
# <a name="viewdefinitions-element-format"></a>Элемент ViewDefinitions (формат)

Определяет представления, используемые для отображения объектов .NET. Эти представления могут отображать свойства и значения скриптов объекта в формате таблицы, формате списка, расширенном формате и пользовательском формате элемента управления.

Элемент конфигурации (Format) Виевдефинитионс (формат XML)

## <a name="syntax"></a>Синтаксис

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ViewDefinitions`. Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration (Format)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:

- [Создание табличного представления](./creating-a-table-view.md)

- [Создание представления списка](./creating-a-list-view.md)

- [Создание расширенного представления](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показан элемент `ViewDefinitions`, содержащий родительские элементы для табличного представления и представления списка.

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>См. также:

[Элемент Configuration (Format)](./configuration-element-format.md)

[View, элемент (Format)](./view-element-format.md)

[Создание табличного представления](./creating-a-table-view.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Пользовательские элементы управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
