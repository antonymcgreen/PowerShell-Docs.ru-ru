---
title: Элемент WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862630"
---
# <a name="wideitem-element-for-widecontrol-format"></a>Элемент WideItem для WideControl (формат)

Определяет свойство или скрипта, значение которого отображается.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) WideItem элемент конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideItem` элемент. Элемент `FormatString` является необязательным. Тем не менее, необходимо указать `PropertyName` или `ScriptBlock` элемент, но нельзя одновременно задать.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для WideItem для WideControl (формат)](./formatstring-element-for-wideitem-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.|
|[Элемент PropertyName для WideItem (формат)](./propertyname-element-for-wideitem-for-widecontrol-format.md)|Задает свойство объекта, значение которого отображается в широком представлении.|
|[Элемент ScriptBlock для WideItem (формат)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|Указывает сценарий, значение которого отображается в широком представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение широкое представление.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах широкое представление, см. в разделе [широкое представление](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В следующем примере показан `WideEntry` элемент, который определяет одно `WideItem` элемент. `WideItem` Элемент определяет свойства или скрипта, значение которого отображается в представлении.

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[Элемент FormatString для WideItem для WideControl (формат)](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[Элемент PropertyName для WideItem (формат)](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[Элемент ScriptBlock для WideItem (формат)](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
