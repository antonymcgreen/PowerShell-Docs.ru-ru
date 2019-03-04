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
ms.openlocfilehash: f7e5d4fb2f89bd6bc7036fdcff8f38e017d5d0e4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858850"
---
# <a name="validating-parameter-input"></a>Проверка входных данных параметра

Windows PowerShell можно проверить аргументы, передаваемые параметры командлета несколькими способами. Windows PowerShell можно проверить длину, диапазон и шаблон символов, аргумента. Он может проверять количество доступных аргументов (число). Эти правила проверки определяются атрибуты проверки, объявленные с атрибутом параметр на открытые свойства класса cmdlet.

Чтобы проверить аргумент параметра, среды выполнения Windows PowerShell использует сведения, предоставляемые атрибуты проверки для подтверждения значение параметра, перед выполнением командлета. Если входные данные параметра не является допустимым, то пользователь получает сообщение об ошибке. Каждый параметр проверки определяет правила проверки, которое зависит от Windows PowerShell.

Windows PowerShell обеспечивает выполнение правил проверки, на основе следующих атрибутов.

ValidateCount указывает минимальное и максимальное число аргументов, которые могут принимать параметр. Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).

ValidateLength указывает минимальное и максимальное число символов в качестве аргумента параметра. Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).

ValidatePattern задает регулярное выражение, которое проверяет аргумент параметра. Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

ValidateRange задает минимальное и максимальное значения аргумента параметра. Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).

ValidateSet указывает допустимые значения для параметра аргумента. Дополнительные сведения о синтаксисе, используемом для объявления этого атрибута см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Как проверки входных параметров](./how-to-validate-parameter-input.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
