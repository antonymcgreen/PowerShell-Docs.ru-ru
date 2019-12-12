---
title: Элемент Кустоментриес для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368823"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определения общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomEntries`. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение общего элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Определяет общий элемент управления.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, которое определено в одном элементе `CustomEntry`. Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
