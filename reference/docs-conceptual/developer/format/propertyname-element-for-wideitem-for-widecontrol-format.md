---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента WideItem для элемента WideControl (формат)
description: Элемент PropertyName для элемента WideItem для элемента WideControl (формат)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665623"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>Элемент PropertyName для элемента WideItem для элемента WideControl (формат)

Указывает свойство объекта, значение которого отображается в расширенном представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Видеитем элемент (Format) PropertyName для Видеитем (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в расширенном представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В этом примере показано расширенное представление, в котором отображается значение свойства ProcessName объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>См. также:

[Элемент Видеитем (Format)](./wideitem-element-for-widecontrol-format.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
