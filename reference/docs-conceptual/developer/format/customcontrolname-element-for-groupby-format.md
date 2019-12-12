---
title: Элемент Кустомконтролнаме для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368883"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Элемент CustomControlName для элемента GroupBy (формат)

Задает имя пользовательского элемента управления, используемого для вывода новой группы. Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента представления (Format) Кустомконтролнаме в GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `CustomControlName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)|Определяет, как Windows PowerShell отображает новую группу объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите имя пользовательского элемента управления, используемого для вывода новой группы.

## <a name="remarks"></a>Замечания

Можно создавать стандартные элементы управления, которые могут использоваться всеми представлениями файла форматирования, а также создавать элементы управления представления, которые могут использоваться в определенном представлении. Следующие элементы определяют имена этих настраиваемых элементов управления:

- [Элемент Name для элемента управления для элементов управления Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Элемент Name для элемента управления для элементов управления в представлении (формат)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также:

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент Name для элемента управления для элементов управления Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Элемент Name для элемента управления для элементов управления в представлении (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
