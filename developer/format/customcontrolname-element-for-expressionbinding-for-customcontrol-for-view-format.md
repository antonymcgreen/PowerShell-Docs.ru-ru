---
title: Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066623"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a>Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)

Указывает имя общего элемента управления или элемент управления. Этот элемент используется при определении представления пользовательского элемента управления.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для CustomItem представление (формат) Элемент для CustomEntry элемента ExpressionBinding представления (формат) для элемента CustomControlName CustomItem (формат) для привязки выражения для CustomItem (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControlName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя элемента управления.

## <a name="remarks"></a>Замечания

Можно создавать стандартные элементы управления, которые могут использоваться все представления файл форматирования, и можно создать элементы управления представления, которые могут использоваться по определенному представлению. Имена этих элементов управления задаются следующие элементы.

- [Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Элемент Name описания для элемента управления для элементов управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также

[Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Элемент Name описания для элемента управления для элементов управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Элемент ExpressionBinding для CustomItem (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
