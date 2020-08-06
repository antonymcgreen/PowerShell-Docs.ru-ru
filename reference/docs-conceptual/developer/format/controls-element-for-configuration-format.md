---
title: Элемент Controls для конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783795"
---
# <a name="controls-element-for-configuration-format"></a>Элемент Controls для элемента Configuration (формат)

Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.

Элемент Configuration (Format) управляет элементом конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Controls` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration (формат)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Примечания

Можно создать любое количество стандартных элементов управления. Для каждого элемента управления необходимо указать имя, которое используется для ссылки на элемент управления и компоненты элемента управления.

## <a name="see-also"></a>См. также

[Элемент Configuration (формат)](./configuration-element-format.md)

[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
