---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideItem для WideControl (формат)
description: Элемент WideItem для WideControl (формат)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647797"
---
# <a name="wideitem-element-for-widecontrol-format"></a>Элемент WideItem для WideControl (формат)

Определяет свойство или скрипт, значение которого отображается.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideItem` элемента. Элемент `FormatString` является необязательным. Однако необходимо указать `PropertyName` `ScriptBlock` элемент или, но нельзя указать и то, и другое.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для элемента WideItem для элемента WideControl (формат)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.|
|[Элемент PropertyName для Видеитем (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Указывает свойство объекта, значение которого отображается в расширенном представлении.|
|[Элемент ScriptBlock для Видеитем (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Задает скрипт, значение которого отображается в расширенном представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение расширенного представления.|

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент. `WideItem`Элемент определяет свойство или скрипт, значение которого отображается в представлении.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент FormatString для элемента WideItem для элемента WideControl (формат)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Элемент PropertyName для Видеитем (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Элемент ScriptBlock для Видеитем (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
