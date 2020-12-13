---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент FormatString для элемента ListItem для элемента ListControl (формат)
description: Элемент FormatString для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667918"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a>Элемент FormatString для элемента ListItem для элемента ListControl (формат)

Задает шаблон формата, определяющий способ отображения значения свойства или скрипта.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (формат) элемента ListItem для ListControl (Format) элемент списка (формат) для элемента списка (Format) ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите шаблон, используемый для форматирования данных. Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.

## <a name="remarks"></a>Комментарии

Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений. Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).

Дополнительные сведения об использовании строк форматирования в представлениях списков см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
