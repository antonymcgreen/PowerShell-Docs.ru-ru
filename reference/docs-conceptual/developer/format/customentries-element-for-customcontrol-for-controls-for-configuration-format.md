---
title: Элемент Кустоментриес для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785988"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определения общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntries` элемента. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение общего элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Определяет общий элемент управления.|

## <a name="remarks"></a>Примечания

В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе. Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
