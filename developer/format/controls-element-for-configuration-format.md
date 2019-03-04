---
title: Элемент Controls для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861180"
---
# <a name="controls-element-for-configuration-format"></a>Элемент Controls для элемента Configuration (формат)

Определяет общие элементы управления, которые могут использоваться все представления файла форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Controls` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления для элементов управления для конфигурации (формат)](./control-element-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет общего элемента управления, который может использоваться все представления файла форматирования.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент конфигурации (формат)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

Можно создать любое количество общих элементов управления. Для каждого элемента управления необходимо указать имя, которое используется для ссылки на элемент управления и компоненты элемента управления.

## <a name="see-also"></a>См. также

[Элемент конфигурации (формат)](./configuration-element-format.md)

[Элемент управления для элементов управления для конфигурации (формат)](./control-element-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
