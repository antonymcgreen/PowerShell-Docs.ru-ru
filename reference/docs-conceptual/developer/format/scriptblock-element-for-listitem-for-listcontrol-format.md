---
title: Элемент ScriptBlock для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785461"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)

Указывает скрипт, значение которого отображается в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес в ListControl (Format) элемент ListItem для листентри для элемента списка элементов ListControl в ListControl (Format).

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите скрипт, значение которого отображается в строке.

## <a name="remarks"></a>Примечания

Если этот элемент указан, нельзя указать элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .

Дополнительные сведения об указании скриптов в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать свойство, значение которого отображается.

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента ListItem для элемента ListControl (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
