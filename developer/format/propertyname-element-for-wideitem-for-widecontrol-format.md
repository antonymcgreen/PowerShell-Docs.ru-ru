---
title: Элемент PropertyName для WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064651"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>Элемент PropertyName для элемента WideItem для элемента WideControl (формат)

Задает свойство объекта, значение которого отображается в широком представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) элемент WideItem (формат) PropertyName элемент конфигурации для WideItem (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в широком представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В этом примере показано широкое представление, которое отображает значение свойства ProcessName [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

## <a name="see-also"></a>См. также

[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
