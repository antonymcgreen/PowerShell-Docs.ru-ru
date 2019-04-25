---
title: Элемент ListEntry для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065229"
---
# <a name="listentry-element-for-listcontrol-format"></a>Элемент ListEntry для элемента ListControl (формат)

Предоставляет определение представления "list".

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) элемент ListEntries (формат) ListEntry элемент конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListEntry` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для ListEntry (формат)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет объекты .NET, которые используют это определение представления списка или условие, которое должен существовать для данного определения для использования.|
|[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойства и скрипты, значения которых отображаются в представлении списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntries (формат)](./listentries-element-for-listcontrol-format.md)|Предоставляет определения представления "list".|

## <a name="remarks"></a>Замечания

Представление списка — формат списка, в которой отображаются значения свойств или значения скриптов для каждого объекта. Дополнительные сведения о списках см. в разделе [Создание представления списка](./creating-a-list-view.md).

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

[Создание представления списка](./creating-a-list-view.md)

[Элемент EntrySelectedBy для ListEntry (формат)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Элемент ListEntries (формат)](./listentries-element-for-listcontrol-format.md)

[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
