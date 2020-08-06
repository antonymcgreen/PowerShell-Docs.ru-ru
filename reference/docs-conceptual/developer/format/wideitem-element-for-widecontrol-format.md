---
title: Элемент Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779902"
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

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Элемент FormatString для элемента WideItem для элемента WideControl (формат)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Элемент PropertyName для Видеитем (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Элемент ScriptBlock для Видеитем (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Элемент Видинтри (Format)](./wideentry-element-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
