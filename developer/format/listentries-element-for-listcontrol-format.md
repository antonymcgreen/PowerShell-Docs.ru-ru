---
title: Элемент ListEntries для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065399"
---
# <a name="listentries-element-for-listcontrol-format"></a>Элемент ListEntries для элемента ListControl (формат)

Предоставляет определения представления "list". В представлении списка необходимо указать одно или несколько определений.

Элемент элемента ListControl (формат) ListEntries ViewDefinitions элемент (формат) представление конфигурации элемента (формат) элемент (формат) (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListEntries` элемент. Необходимо указать хотя бы один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntry (формат)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления "list".|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListControl (формат)](./listcontrol-element-format.md)|Определяет формат для представления списка.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о списках см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны элементы XML, которые определяют представление списка для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>См. также

[Элемент ListControl (формат)](./listcontrol-element-format.md)

[Элемент ListEntry (формат)](./listentry-element-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
