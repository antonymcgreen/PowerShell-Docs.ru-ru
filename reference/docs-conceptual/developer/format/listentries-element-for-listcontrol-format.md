---
title: Элемент Листентриес для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0fe07e739c2d2fec153599ec6c0c0b3ecc14df18
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785716"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListEntries` элемента. Необходимо указать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListControl (формат)](./listcontrol-element-format.md)|Определяет формат списка для представления.|

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Элемент ListControl (формат)](./listcontrol-element-format.md)

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
