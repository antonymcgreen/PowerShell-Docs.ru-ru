---
title: Элемент Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361403"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideItem`. Элемент `FormatString` является необязательным. Однако необходимо указать элемент `PropertyName` или `ScriptBlock`, но нельзя указать и то и другое.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для Видеитем для Видеконтрол (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.|
|[Элемент PropertyName для Видеитем (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Указывает свойство объекта, значение которого отображается в расширенном представлении.|
|[Элемент ScriptBlock для Видеитем (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Задает скрипт, значение которого отображается в расширенном представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение расширенного представления.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `WideEntry`, определяющий один элемент `WideItem`. Элемент `WideItem` определяет свойство или скрипт, значение которого отображается в представлении.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент FormatString для Видеитем для Видеконтрол (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Элемент PropertyName для Видеитем (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Элемент ScriptBlock для Видеитем (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
