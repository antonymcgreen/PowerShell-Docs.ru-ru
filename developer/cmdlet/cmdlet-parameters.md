---
title: Параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.assetid: 3f1cca5f-5b95-4bce-94a6-a22db1aefd47
caps.latest.revision: 23
ms.openlocfilehash: 914a10907bcf980eed8d7e2f819c382fe6b341ad
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853850"
---
# <a name="cmdlet-parameters"></a>Параметры командлета

Параметры командлета предоставляют механизм, позволяющий командлету, чтобы принимать входные данные. Параметры могут принимать входные данные, непосредственно из командной строки или из объектов передается командлету по конвейеру, аргументы (также называется *значения*) из этих параметров можно указать ввода, который принимает командлет, как командлет необходимо выполнить действия и данных, который возвращает командлет в конвейер.

## <a name="in-this-section"></a>Содержание

[Объявление свойств как параметры](./declaring-properties-as-parameters.md) содержит основные сведения, необходимо понимать, прежде чем объявить параметры командлета.

[Типы параметров командлета](./types-of-cmdlet-parameters.md) описываются различные типы параметров, которые можно объявить в командлетах.

[Имя параметра командлета и функциональные возможности инструкции](./standard-cmdlet-parameter-names-and-types.md) обсуждение имена, рекомендуется использовать тип данных и функциональных возможностей стандартные параметры.

[Псевдонимы параметра](./parameter-aliases.md) рассматриваются псевдонимы, которые можно определить для параметров.

[Имена общих параметров](./common-parameter-names.md) в этом разделе описываются параметры, которые добавляет командлеты Windows PowerShell.

[Задает параметр командлета](./cmdlet-parameter-sets.md) рассматриваются как наборы параметров, которые позволяют создавать один командлет, который может выполнять различные действия для различных сценариев.

[Динамические параметры командлета](./cmdlet-dynamic-parameters.md) рассматриваются параметры, доступные для пользователя в специальных условиях.

[Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md) описывает способ обеспечения поддержки подстановочные знаки, при проектировании командлет, который будет выполняться для группы ресурсов.

[Проверка входных данных параметра](./validating-parameter-input.md) показано, как Windows PowerShell проверяет аргументы, передаваемые параметры командлета.

[Входные параметры фильтра](./input-filter-parameters.md) описание `Filter`, `Include`, и `Exclude` параметры фильтрации набора входных значений объектов, на которые влияет на командлет.

## <a name="related-sections"></a>Связанные разделы

[Как проверки входных параметров](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>См. также

[Объявление параметра-атрибут](./parameter-attribute-declaration.md)

[Командлеты Windows PowerShell](./cmdlet-overview.md)
