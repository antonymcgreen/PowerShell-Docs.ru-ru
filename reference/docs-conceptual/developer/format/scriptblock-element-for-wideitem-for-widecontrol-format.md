---
title: Элемент ScriptBlock для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362033"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Элемент ScriptBlock для WideItem для WideControl (формат)

Задает скрипт, значение которого отображается в расширенном представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) элемент ScriptBlock для Видеитем (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или блок скрипта, значение которого отображается в расширенном представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите скрипт, значение которого отображается.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `WideItem`, определяющий скрипт, значение которого отображается в представлении.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>См. также:

[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
