---
title: Элемент Control для элементов управления Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369013"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Элемент Control для элемента Controls для элемента Configuration (формат)

Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент для элемента `Control`. Необходимо указать только один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для элемента управления для элементов управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления.|
|[Элемент Name для элемента управления конфигурации (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на элемент управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления в конфигурации (формат)](./controls-element-for-configuration-format.md)|Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования или другими элементами управления.|

## <a name="remarks"></a>Замечания

На имя, присвоенное этому элементу управления, можно ссылаться в следующих элементах:

- [Элемент ExpressionBinding для Кустомитем (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>См. также:

[Элемент управления в конфигурации (формат)](./controls-element-for-configuration-format.md)

[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для Кустомитем (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент Name для элемента управления для элементов управления Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
