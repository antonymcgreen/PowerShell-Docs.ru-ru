---
title: Элемент Кустомконтролнаме для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783744"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Элемент CustomControlName для элемента GroupBy (формат)

Задает имя пользовательского элемента управления, используемого для вывода новой группы. Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента представления (Format) Кустомконтролнаме в GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomControlName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как Windows PowerShell отображает новую группу объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите имя пользовательского элемента управления, используемого для вывода новой группы.

## <a name="remarks"></a>Примечания

Можно создавать стандартные элементы управления, которые могут использоваться всеми представлениями файла форматирования, а также создавать элементы управления представления, которые могут использоваться в определенном представлении. Следующие элементы определяют имена этих настраиваемых элементов управления:

- [Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Элемент Name для элемента Control для элемента Controls для элемента View (формат)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента View (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
