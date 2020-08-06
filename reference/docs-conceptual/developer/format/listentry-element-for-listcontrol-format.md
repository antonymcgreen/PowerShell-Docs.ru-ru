---
title: Элемент Листентри для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d98f0b5215eea7668f866d2733214ade79d748f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785699"
---
# <a name="listentry-element-for-listcontrol-format"></a>Элемент ListEntry для элемента ListControl (формат)

Предоставляет определение представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListEntry` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет объекты .NET, использующие это определение представления списка, или условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойства и скрипты, значения которых отображаются в представлении списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентриес (Format)](./listentries-element-for-listcontrol-format.md)|Предоставляет определения представления списка.|

## <a name="remarks"></a>Примечания

Представление списка — это формат списка, который отображает значения свойств или значения скриптов для каждого объекта. Дополнительные сведения о представлениях списков см. [в разделе Создание представления списка](./creating-a-list-view.md).

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

[Создание представления списка](./creating-a-list-view.md)

[Элемент Ентриселектедби для Листентри (Format)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[Элемент Листентриес (Format)](./listentries-element-for-listcontrol-format.md)

[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
