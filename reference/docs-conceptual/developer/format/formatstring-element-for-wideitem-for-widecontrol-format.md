---
title: Элемент FormatString для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363033"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>Элемент FormatString для элемента WideItem для элемента WideControl (формат)

Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент для видеконтрол (Format) Видеитем для элемента видеконтрол (Format) FormatString для Видеитем для Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `FormatString`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеитем для Видеконтрол (Format)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите шаблон, используемый для форматирования данных. Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.

## <a name="remarks"></a>Замечания

Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений. Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).

Дополнительные сведения об использовании строк формата в широких представлениях см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>См. также:

[Создание расширенного представления](./creating-a-wide-view.md)

[Элемент Видеитем для Видеконтрол (Format)](./wideitem-element-for-widecontrol-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
