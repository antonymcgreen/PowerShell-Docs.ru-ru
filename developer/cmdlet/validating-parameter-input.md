---
title: Проверка входных данных параметра | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.assetid: 3f15bf20-a068-4a7d-a170-bc43f755d1fe
caps.latest.revision: 14
ms.openlocfilehash: 171e3e974619e197a0bcc9dfc759297005e34568
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429845"
---
# <a name="validating-parameter-input"></a>Проверка входных данных параметра

PowerShell можно проверить аргументы, передаваемые параметры командлета несколькими способами.
PowerShell можно проверить длину, диапазон и шаблон символов, аргумента.
Он может проверять количество доступных аргументов (число).
Эти правила проверки определяются атрибуты проверки, объявленные с атрибутом параметр на открытые свойства класса cmdlet.

Чтобы проверить аргумента параметра, среда выполнения PowerShell использует сведения, предоставляемые атрибуты проверки для подтвердить значение параметра, перед выполнением командлета.
Если входные данные параметра не является допустимым, то пользователь получает сообщение об ошибке.
Каждый параметр проверки определяет правило проверки, которое обеспечивается PowerShell.

PowerShell соблюдает правила для проверки, на основе следующих атрибутов.

### <a name="validatecount"></a>ValidateCount

Указывает минимальное и максимальное число аргументов, которые могут принимать параметр.
Дополнительные сведения см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>ValidateLength

Указывает минимальное и максимальное число символов в качестве аргумента параметра.
Дополнительные сведения см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Указывает регулярное выражение, которое проверяет аргумент параметра.
Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>ValidateRange

Задает минимальное и максимальное значения аргумента параметра.
Дополнительные сведения см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Указывает допустимые значения для параметра аргумента.
Дополнительные сведения см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Как проверки входных параметров](./how-to-validate-parameter-input.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
