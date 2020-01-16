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
ms.openlocfilehash: c1d8984f4aad7bae6f9be66a2222e2c74c8afa3d
ms.sourcegitcommit: cab4e4e67dbed024864887c7f8984abb4db3a78b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "76022208"
---
# <a name="cmdlet-parameters"></a>Параметры командлета

Параметры командлета предоставляют механизм, позволяющий командлету принимать входные данные. Параметры могут принимать входные данные непосредственно из командной строки или из объектов, передаваемых в командлет через конвейер, аргументы (также называемые *значениями*) этих параметров могут указывать входные данные, принимаемые командлетом, то, как командлет должен выполнять свои действия и данные, возвращаемые командлетом в конвейер.

## <a name="in-this-section"></a>Содержание

[Объявление свойств как параметров](./declaring-properties-as-parameters.md) Предоставляет основные сведения, которые необходимо понимать перед объявлением параметров командлета.

[Типы параметров командлета](./types-of-cmdlet-parameters.md) Описывает различные типы параметров, которые можно объявить в командлетах.

[Имя параметра командлета и рекомендации по функциональности](./standard-cmdlet-parameter-names-and-types.md) Описывает имена, Рекомендуемые типы данных и функциональные возможности стандартных параметров.

[Псевдонимы параметров](./parameter-aliases.md) Описывает псевдонимы, которые можно определить для параметров.

[Общие имена параметров](./common-parameter-names.md) В этом разделе описаны параметры, которые Windows PowerShell добавляет в командлеты.

[Наборы параметров командлета](./cmdlet-parameter-sets.md) Описывает, как наборы параметров позволяют создавать один командлет, который может выполнять различные действия в различных сценариях.

[Динамические параметры командлета](./cmdlet-dynamic-parameters.md) Обсуждаются параметры, доступные пользователю при особых условиях.

[Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md) Описывает, как обеспечить поддержку подстановочных знаков при проектировании командлета, который будет выполняться для группы ресурсов.

[Проверка входных параметров](./validating-parameter-input.md) Описывает, как Windows PowerShell проверяет аргументы, передаваемые в параметры командлета.

[Параметры входного фильтра](./input-filter-parameters.md) Обсуждаются параметры `Filter`, `Include`и `Exclude`, которые фильтруют набор входных объектов, на которые влияет командлет.

## <a name="related-sections"></a>Связанные разделы

[Проверка входных параметров](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>См. также

[Объявление атрибута Parameter](./parameter-attribute-declaration.md)

[Командлеты Windows PowerShell](./cmdlet-overview.md)
