---
title: Элемент PropertyName для Итемселектионкондитион элементов управления в представлении (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c6517b8f63e0511ce071926ac3ac39ba82e7ed21
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783489"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется элемент управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элементов управления для элемента Control (формат). для элементов управления для элемента "View" (Format) Кустомитем для Кустоментри для элементов управления для элемента ExpressionBinding представления (Format) Кустомитем для элементов управления для элемента "View" (формат) ItemSelectionCondition в ExpressionBinding для элементов управления представления (Format) элемент "PropertyName" для ItemSelectionCondition для элементов управления представления (формат)

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
|[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое запускает условие.

## <a name="remarks"></a>Примечания

Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
