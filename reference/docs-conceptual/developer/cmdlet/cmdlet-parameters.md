---
title: Параметры командлета | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.openlocfilehash: 98b1d5fd0e7ffbf2d4d161f1bed73fb96a737bd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774768"
---
# <a name="cmdlet-parameters"></a>Параметры командлета

Параметры командлета предоставляют механизм, позволяющий командлету принимать входные данные. Параметры могут принимать входные данные непосредственно из командной строки или из объектов, передаваемых в командлет через конвейер, аргументы (также называемые *значениями*) этих параметров могут указывать входные данные, принимаемые командлетом, то, как командлет должен выполнять свои действия и данные, возвращаемые командлетом в конвейер.

## <a name="in-this-section"></a>В этом разделе

[Объявление свойств как параметров](./declaring-properties-as-parameters.md) Предоставляет основные сведения, которые необходимо понимать перед объявлением параметров командлета.

[Типы параметров командлета](./types-of-cmdlet-parameters.md) Описывает различные типы параметров, которые можно объявить в командлетах.

[Имя параметра командлета и рекомендации по функциональности](./standard-cmdlet-parameter-names-and-types.md) Описывает имена, Рекомендуемые типы данных и функциональные возможности стандартных параметров.

[Псевдонимы параметров](./parameter-aliases.md) Описывает псевдонимы, которые можно определить для параметров.

[Общие имена параметров](./common-parameter-names.md) В этом разделе описаны параметры, которые Windows PowerShell добавляет в командлеты.

[Наборы параметров командлета](./cmdlet-parameter-sets.md) Описывает, как наборы параметров позволяют создавать один командлет, который может выполнять различные действия в различных сценариях.

[Динамические параметры командлета](./cmdlet-dynamic-parameters.md) Обсуждаются параметры, доступные пользователю при особых условиях.

[Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md) Описывает, как обеспечить поддержку подстановочных знаков при проектировании командлета, который будет выполняться для группы ресурсов.

[Проверка входных параметров](./validating-parameter-input.md) Описывает, как Windows PowerShell проверяет аргументы, передаваемые в параметры командлета.

[Параметры входного фильтра](./input-filter-parameters.md) Описывает `Filter` `Include` Параметры, и `Exclude` , которые фильтруют набор входных объектов, на которые влияет командлет.

## <a name="related-sections"></a>Связанные разделы

[Как проверить входные параметры](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>См. также

[Объявление атрибута параметра](./parameter-attribute-declaration.md)

[Командлеты Windows PowerShell](./cmdlet-overview.md)
