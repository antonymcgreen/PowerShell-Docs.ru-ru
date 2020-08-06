---
title: Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3bfd3efe916b4d88c024de8f959482cab515f777
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781228"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента Configuration (Format) Кустомитем для Кустоментри для элементов управления элемента Configuration ExpressionBinding для Кустомитем для элементов управления для элемента конфигурации (Format) Итемселектионкондитион для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Примечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также

[Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
