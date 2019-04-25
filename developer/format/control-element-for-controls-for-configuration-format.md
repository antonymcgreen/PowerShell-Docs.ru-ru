---
title: Элемент Control для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066799"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Элемент Control для элемента Controls для элемента Configuration (формат)

Определяет общий элемент управления, который может использоваться все представления файла форматирования и имя, которое используется для ссылки на элемент управления.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент для `Control` элемент. Необходимо указать только один из каждого дочернего элемента.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Пользовательский элемент управления элемент для элемента управления для элементов управления для конфигурации (формат)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления.|
|[Элемент Name описания для элемента управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Указывает имя, используемое для ссылки на элемент управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элементы управления элемента конфигурации (формат)](./controls-element-for-configuration-format.md)|Определяет общие элементы управления, которые могут использоваться все представления файла форматирования или других элементов управления.|

## <a name="remarks"></a>Замечания

Имя, присвоенное этот элемент управления можно ссылаться в следующие элементы:

- [Элемент ExpressionBinding для CustomItem (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [GroupBy-элемент для View(Format)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>См. также

[Элементы управления элемента конфигурации (формат)](./controls-element-for-configuration-format.md)

[Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для CustomItem (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[GroupBy-элемент для View(Format)](./groupby-element-for-view-format.md)

[Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
