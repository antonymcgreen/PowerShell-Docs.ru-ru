---
title: Элемент Листентриес для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362763"
---
# <a name="listentries-element-for-listcontrol-format"></a>Элемент ListEntries для элемента ListControl (формат)

Предоставляет определения представления списка. В представлении списка должно быть указано одно или несколько определений.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl элемент (Format) Листентриес (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListEntries`. Необходимо указать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListControl (Format)](./listcontrol-element-format.md)|Определяет формат списка для представления.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о представлениях списков см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

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

## <a name="see-also"></a>См. также:

[Элемент ListControl (Format)](./listcontrol-element-format.md)

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
