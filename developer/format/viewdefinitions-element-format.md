---
title: Элемент ViewDefinitions (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083711"
---
# <a name="viewdefinitions-element-format"></a>Элемент ViewDefinitions (формат)

Определяет представления для отображения объектов .NET. Эти представления могут отображать свойства и значения объекта скрипта в табличном формате, формате списка, расширенном формате и формате пользовательского элемента управления.

Элемент ViewDefinitions (в формате XML) (формат) элемента конфигурации

## <a name="syntax"></a>Синтаксис

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ViewDefinitions` элемент. Нет ограничений на количество представлений, которые могут быть определены в файле форматирования, и могут быть добавлены в любом порядке.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое используется для отображения один или несколько объектов .NET.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент конфигурации (формат)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах различных типов представлений см. в разделах:

- [Создание представления таблицы](./creating-a-table-view.md)

- [Создание представления списка](./creating-a-list-view.md)

- [Создание широкое представление](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показано `ViewDefinitions` элемент, содержащий родительские элементы для представления таблицы и представления списка.

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

## <a name="see-also"></a>См. также

[Элемент конфигурации (формат)](./configuration-element-format.md)

[Элемент представления (формат)](./view-element-format.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Пользовательские элементы управления](./creating-custom-controls.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
