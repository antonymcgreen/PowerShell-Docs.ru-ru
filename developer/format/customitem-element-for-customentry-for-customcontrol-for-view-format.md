---
title: Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856190"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a>Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)

Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается. Этот элемент используется при определении представления пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.|
|[Элемент новой строки для CustomItem для пользовательского элемента управления для представления (формат)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет пустой строки для отображения элемента управления.|
|[Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)](./text-element-for-customitem-for-customview-for-view-format.md)|Необязательный элемент.<br /><br /> Задает дополнительный текст для данных, отображаемых элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для CustomEntries для пользовательский элемент управления для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Предоставляет определение пользовательского элемента управления представления.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент CustomEntry для CustomEntries для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Элемент новой строки для CustomItem для пользовательский элемент управления для представления (формат)](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[Текстовый элемент для CustomItem для пользовательский элемент управления для представления (формат)](./text-element-for-customitem-for-customview-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
