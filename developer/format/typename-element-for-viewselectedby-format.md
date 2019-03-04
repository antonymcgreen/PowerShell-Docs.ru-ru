---
title: TypeName-элемент для ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857900"
---
# <a name="typename-element-for-viewselectedby-format"></a>Элемент TypeName для элемента ViewSelectedBy (формат)

Указывает объект .NET, который отображается в представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент ViewSelectedBy (формат) TypeName элемент конфигурации для ViewSelectedBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние и родительские элементы из `TypeName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)|Определяет объекты .NET, которые отображаются в представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Дополнительные сведения о том, как этот элемент используется в различных представлениях см. в разделе [Создание представления таблицы](./creating-a-table-view.md), [Создание представления списка](./creating-a-list-view.md), [Создание широкое представление](./creating-a-wide-view.md), и [ Пользовательское представление компонентов](./creating-custom-controls.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект для представления списка. Ту же схему используется для таблицы, расширенных и настраиваемых представлений.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Элемент ViewSelectedBy (формат)](./viewselectedby-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
