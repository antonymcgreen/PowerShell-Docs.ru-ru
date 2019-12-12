---
title: Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368453"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должно существовать для использования определения общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элементов управления для Элемент конфигурации (Format) Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри элементов управления для элемента конфигурации (Format) Селектионкондитион для Ентриселектедби для Кустоментри для Конфигурация (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион для элементов управления конфигурации (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Определяет типы .NET, которые используют эту запись определения общего элемента управления.|

## <a name="remarks"></a>Замечания

При определении условия выбора необходимо следовать приведенным ниже рекомендациям.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для Селектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент TypeName для Селектионкондитион для элементов управления конфигурации (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
