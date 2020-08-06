---
title: Элемент Label для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 07b4d037472a9dd2329e94576ec10f5b82f46b34
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785784"
---
# <a name="label-element-for-groupby-format"></a>Элемент Label для элемента GroupBy (формат)

Указывает метку, которая отображается при обнаружении новой группы.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента метки представления (Format) для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается новая группа объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, который будет отображаться каждый раз, когда Windows PowerShell встречает новое значение свойства или скрипта.

## <a name="remarks"></a>Примечания

В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает новое значение, которое запускает группу, и добавляет пустую строку до и после группы.

## <a name="example"></a>Пример

В следующем примере показана метка для новой группы. Отображаемая метка будет выглядеть примерно так:`Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
