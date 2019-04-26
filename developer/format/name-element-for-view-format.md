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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065076"
---
# <a name="name-element-for-view-format"></a>Элемент Name для элемента View (формат)

Указывает имя, которое используется для идентификации представления.

Имя элемента (формат) элемента (формат) для конфигурации элемента (формат) элемент ViewDefinitions (формат) представления

## <a name="syntax"></a>Синтаксис

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент. Только один `Name` элемент допускается для каждого представления.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое используется для отображения элементов из одного или нескольких объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите уникальное понятное имя для представления. Это имя может содержать ссылку на тип представления (например, таблица или представление списка), объект или набор объектов, который следует использовать представление, какая команда возвращает объекты или их сочетание.

## <a name="remarks"></a>Замечания

Дополнительные сведения о различных типах представлений см. в разделах: [Табличное представление](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [широкое представление](./creating-a-wide-view.md), и [пользовательское представление](./creating-custom-controls.md).

## <a name="example"></a>Пример

В следующем примере показан `View` элемент, который определяет представление таблицы для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта. Представление называется «служба».

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

[Создание широкое представление](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент представления (формат)](./view-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
