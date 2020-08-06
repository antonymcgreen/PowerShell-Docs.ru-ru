---
title: Элемент ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785733"
---
# <a name="listcontrol-element-format"></a>Элемент ListControl (формат)

Определяет формат списка для представления.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListControl` элемента. Этот элемент должен содержать только один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентриес (Format)](./listentries-element-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения элементов одного или нескольких объектов.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о создании представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показано представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>См. также

[Элемент View (формат)](./view-element-format.md)

[Элемент Листентриес (Format)](./listentries-element-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
