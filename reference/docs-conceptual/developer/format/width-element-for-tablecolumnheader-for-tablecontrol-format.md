---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)
description: Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658250"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)

Определяет ширину (в символах) столбца.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемент Таблехеадерс для TableControl (формат) элемент TableColumnHeader для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Width` элемента, используемого при определении заголовков столбцов.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Когда это возможно, укажите ширину (в символах), превышающую длину отображаемых значений свойств.

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableColumnHeader` элемент, ширина которого составляет 16 символов.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Таблеколумнхеадер для Таблехеадер для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
