---
title: Элемент TypeName для Виевселектедби (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361443"
---
# <a name="typename-element-for-viewselectedby-format"></a>Элемент TypeName для элемента ViewSelectedBy (формат)

Задает объект .NET, отображаемый представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Виевселектедби Element (Format) TypeName для Виевселектедби (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `TypeName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Виевселектедби (Format)](./viewselectedby-element-format.md)|Определяет объекты .NET, отображаемые представлением.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

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

[Создание табличного представления](./creating-a-table-view.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент Виевселектедби (Format)](./viewselectedby-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
