---
title: Элемент Виевдефинитионс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772490"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ViewDefinitions` элемента. Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration (формат)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:

- [Создание представления таблицы](./creating-a-table-view.md)

- [Создание представления списка](./creating-a-list-view.md)

- [Создание широкого представления](./creating-a-wide-view.md)

- [Пользовательские элементы управления](./creating-custom-controls.md)

## <a name="example"></a>Пример

В этом примере показан `ViewDefinitions` элемент, содержащий родительские элементы для табличного представления и представления списка.

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

[Элемент Configuration (формат)](./configuration-element-format.md)

[Элемент View (формат)](./view-element-format.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Пользовательские элементы управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
