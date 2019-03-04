---
title: Ширина элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: a38fcbef457e69e3ea08d25ba3a9843621036f1e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853110"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)

Определяет ширину (в символах) столбца.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableHeaders элемент конфигурации для TableHeaders элемент TableColumnHeader TableControl (формат) для элемента ширины TableControl (формат) TableColumnHeader для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Width` элемент, используемый при определении заголовки столбцов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader для TableHeaders для TbleControl (формат)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивания данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Если на все возможные следует укажите ширину (в символах), больше, чем длина значения отображаемого свойства.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableColumnHeader` элемента, ширина которого составляет 16 символов.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnHeader для TableHeader для TableControl (формат)](./tablecolumnheader-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
