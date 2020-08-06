---
title: Элемент Name для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 670b089f850fa4b39b7b100ca1e1ce45b05ea72d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773238"
---
# <a name="name-element-for-view-format"></a>Элемент Name для элемента View (формат)

Задает имя, используемое для указания представления.

Элемент Configuration (Format) Виевдефинитионс элемент (Format) View элемент (Format) имя элемента (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента. `Name`Для каждого представления допускается только один элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения элементов одного или нескольких объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите уникальное понятное имя для представления. Это имя может включать ссылку на тип представления (например, представление таблицы или представление списка), какой объект или набор объектов использует представление, какая команда возвращает объекты или их сочетание.

## <a name="remarks"></a>Примечания

Дополнительные сведения о различных типах представлений см. в следующих разделах: [представление таблицы](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [Расширенное представление](./creating-a-wide-view.md)и [пользовательское представление](./creating-custom-controls.md).

## <a name="example"></a>Пример

В следующем примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . Имя представления — "служба".

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент View (формат)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
