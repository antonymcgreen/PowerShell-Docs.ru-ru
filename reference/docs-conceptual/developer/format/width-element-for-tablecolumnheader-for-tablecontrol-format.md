---
title: Элемент Width для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: 4a25c9d81df670dc10955065bfb66766cdb1bd33
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367873"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)

Определяет ширину (в символах) столбца.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемент Таблехеадерс для TableControl (формат) элемент Width для Таблеколумнхеадер для Таблеконтрол (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Width`, используемого при определении заголовков столбцов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Когда это возможно, укажите ширину (в символах), превышающую длину отображаемых значений свойств.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `TableColumnHeader`, ширина которого составляет 16 символов.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Таблеколумнхеадер для Таблехеадер для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
