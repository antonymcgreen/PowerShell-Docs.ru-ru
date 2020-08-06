---
title: Элемент ScriptBlock для Итемселектионкондитион элементов управления для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787671"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется элемент управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элементов управления для элемента Control (формат). для элементов управления для элемента "View" (Format) Кустомитем для Кустоментри для элементов управления для элемента ExpressionBinding представления (Format) ItemSelectionCondition для Кустомитем элементов управления для элемента "View" (формат) элемент ExpressionBinding для элементов управления представления (Format).

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
