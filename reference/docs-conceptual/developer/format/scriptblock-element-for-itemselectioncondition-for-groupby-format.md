---
title: Элемент ScriptBlock для Итемселектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787654"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется элемент управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента GroupBy для элемента Ошибка customcontrol представления (Format) элемент Кустоментриес для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для ошибка customcontrol для элемента GroupBy (Format) Кустомитем для элемента Кустоментри для GroupBy (Format) ExpressionBinding для Кустомитем для элемента итемселектионкондитион в ExpressionBinding для GroupBy (Format) элемент ScriptBlock для ItemSelectionCondition для GroupBy (Format)

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
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также

[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
