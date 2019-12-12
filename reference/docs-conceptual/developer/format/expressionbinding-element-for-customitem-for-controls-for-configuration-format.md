---
title: Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363193"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format)

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
|[Элемент Кустомконтролнаме для ExpressionBinding для элементов управления конфигурации (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент Енумератеколлектион для ExpressionBinding для элементов управления конфигурации (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, что элементы коллекций отображаются элементом управления.|
|[Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого общего элемента управления.|
|[Элемент PropertyName для ExpressionBinding элементов управления в конфигурации (Format)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается общим элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding элементов управления в конфигурации (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, значение которого отображается общим элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также:

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
