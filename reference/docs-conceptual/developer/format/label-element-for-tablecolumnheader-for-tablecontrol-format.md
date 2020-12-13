---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)
description: Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667799"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)

Определяет метку, отображаемую в верхней части столбца. Этот элемент используется при определении табличного представления.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс для TableControl (Format) элемент Label для TableColumnHeader в TableControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента. Для каждого столбца допускается только одна метка.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, отображаемый в верхней части столбца таблицы. Для метки столбца нет ограниченных символов.

## <a name="remarks"></a>Комментарии

Если метка не указана, то используется имя свойства, значение которого отображается в строках.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableColumnHeader` элемент, метка которого равна «Column 1».

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
