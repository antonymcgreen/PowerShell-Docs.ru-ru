---
title: Проверка входных параметров | Документация Майкрософт
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363513"
---
# <a name="validating-parameter-input"></a>Проверка входных данных параметра

PowerShell может проверить аргументы, передаваемые в параметры командлета, несколькими способами.
PowerShell может проверить длину, диапазон и шаблон символов аргумента.
Он может проверить количество доступных аргументов (количество).
Эти правила проверки определяются атрибутами проверки, объявленными с атрибутом Parameter в общих свойствах класса командлета.

Для проверки аргумента параметра среда выполнения PowerShell использует сведения, предоставленные атрибутами проверки, для подтверждения значения параметра перед выполнением командлета.
Если входные данные параметра недопустимы, пользователь получает сообщение об ошибке.
Каждый параметр проверки определяет правило проверки, принудительно применяемое PowerShell.

PowerShell применяет правила проверки на основе следующих атрибутов.

### <a name="validatecount"></a>валидатекаунт

Указывает минимальное и максимальное число аргументов, которые может принимать параметр.
Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>валидателенгс

Указывает минимальное и максимальное число символов в аргументе параметра.
Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Задает регулярное выражение, которое проверяет аргумент параметра.
Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>валидатеранже

Задает минимальное и максимальное значения аргумента параметра.
Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Указывает допустимые значения для аргумента параметра.
Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".

## <a name="see-also"></a>См. также:

[Проверка входных параметров](./how-to-validate-parameter-input.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
