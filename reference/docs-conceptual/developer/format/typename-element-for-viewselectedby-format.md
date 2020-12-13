---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента ViewSelectedBy (формат)
description: Элемент TypeName для элемента ViewSelectedBy (формат)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667731"
---
# <a name="typename-element-for-viewselectedby-format"></a>Элемент TypeName для элемента ViewSelectedBy (формат)

Задает объект .NET, отображаемый представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби Element (Format) TypeName для Виевселектедби (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TypeName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)|Определяет объекты .NET, отображаемые представлением.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .

## <a name="remarks"></a>Комментарии

Дополнительные сведения об использовании этого элемента в различных представлениях см. в статьях [Создание табличного представления](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание расширенного представления](./creating-a-wide-view.md)и [пользовательские компоненты представления](./creating-custom-controls.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка. Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
