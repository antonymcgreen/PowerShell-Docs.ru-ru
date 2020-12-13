---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для WideItem для WideControl (формат)
description: Элемент ScriptBlock для WideItem для WideControl (формат)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659869"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Элемент ScriptBlock для WideItem для WideControl (формат)

Задает скрипт, значение которого отображается в расширенном представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) элемент ScriptBlock для Видеитем (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
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
|[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или блок скрипта, значение которого отображается в расширенном представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите скрипт, значение которого отображается.

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В этом примере показан `WideItem` элемент, определяющий скрипт, значение которого отображается в представлении.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>См. также:

[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
