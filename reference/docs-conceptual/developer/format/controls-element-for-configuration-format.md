---
title: Элемент Controls для конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369003"
---
# <a name="controls-element-for-configuration-format"></a>Элемент Controls для элемента Configuration (формат)

Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.

Элемент Configuration (Format) управляет элементом конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Controls`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элементов управления конфигурации (Format)](./control-element-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration (Format)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

Можно создать любое количество стандартных элементов управления. Для каждого элемента управления необходимо указать имя, которое используется для ссылки на элемент управления и компоненты элемента управления.

## <a name="see-also"></a>См. также:

[Элемент Configuration (Format)](./configuration-element-format.md)

[Элемент Control для элементов управления конфигурации (Format)](./control-element-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
