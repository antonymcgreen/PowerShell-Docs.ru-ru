---
title: Элемент ExpressionBinding для Кустомитем для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363153"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента представления (Format) Кустоментриес для ошибка customcontrol для элемента View (Format) Кустоментри для Кустоментриес для ошибка customcontrol View ( Формат) элемент Кустомитем для Кустоментри для ошибка customcontrol для представления (Format) ExpressionBinding для Кустомитем для ошибка customcontrol для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ExpressionBinding`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomControl Element`|Необязательный элемент.<br /><br /> Определяет элемент управления, используемый этим элементом управления.|
|[Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент Енумератеколлектион для ExpressionBinding для ошибка customcontrol для представления (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, что отображаются элементы коллекций.|
|[Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для ExpressionBinding для ошибка customcontrol в представлении (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для Кустомкустомконтрол для представления (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для ошибка customcontrol для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также:

[Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент Енумератеколлектион для ExpressionBinding для ошибка customcontrol для представления (Format)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Элемент PropertyName для ExpressionBinding для ошибка customcontrol в представлении (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для ExpressionBinding для ошибка customcontrol для представления (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент Кустомитем для Кустоментри для ошибка customcontrol для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
