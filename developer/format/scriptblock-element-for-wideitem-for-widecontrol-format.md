---
title: Элемент ScriptBlock для WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064209"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a>Элемент ScriptBlock для WideItem для WideControl (формат)

Указывает сценарий, значение которого отображается в широком представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) элемент WideItem (формат) ScriptBlock элемент конфигурации для WideItem (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)|Определяет блок свойство или скрипта, значение которого отображается в широком представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, значение которого отображается.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="example"></a>Пример

В этом примере показано `WideItem` элемент, который определяет скрипт, значение которого отображается в представлении.

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a>См. также

[Элемент WideItem (формат)](./wideitem-element-for-widecontrol-format.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
