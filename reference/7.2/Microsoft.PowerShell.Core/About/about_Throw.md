---
description: Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: 2984e0a9e5f470594dd1e5987b69b92f91ce4913
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600200"
---
# <a name="about-throw"></a>О вызове

## <a name="short-description"></a>Краткое описание
Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.

## <a name="long-description"></a>Подробное описание

Ключевое слово Throw вызывает завершающую ошибку. Для завершения обработки команды, функции или скрипта можно использовать ключевое слово Throw.

Например, можно использовать ключевое слово Throw в блоке script инструкции if для ответа на условие или в блоке catch оператора try-catch-finally. Можно также использовать ключевое слово Throw в объявлении параметра, чтобы сделать параметр функции обязательным.

Ключевое слово Throw может вызывать любой объект, например строку сообщения пользователя или объект, вызвавший ошибку.

## <a name="syntax"></a>Синтаксис

Синтаксис ключевого слова Throw выглядит следующим образом:

```powershell
throw [<expression>]
```

Выражение в синтаксисе Throw является необязательным. Если инструкция throw не отображается в блоке catch и не содержит выражение, возникает ошибка Скрипсалтед.

```powershell
C:\PS> throw

Exception: ScriptHalted
```

Если ключевое слово Throw используется в блоке catch без выражения, оно снова выдает текущий RuntimeException. Дополнительные сведения см. в разделе about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>Создание строки

Необязательное выражение в операторе Throw может быть строкой, как показано в следующем примере:

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a>Вызов других объектов

Выражение также может быть объектом, создающим объект, который представляет процесс PowerShell, как показано в следующем примере:

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

Для проверки ошибки можно использовать свойство TargetObject объекта Ерроррекорд в автоматической переменной $error.

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

Можно также вызвать исключение объекта Ерроррекорд или исключения .NET. В следующем примере используется ключевое слово Throw для создания объекта System. FormatException.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a>Итоговая ошибка

Ключевое слово Throw может создавать объект Ерроррекорд. Свойство Exception объекта Ерроррекорд содержит объект RuntimeException. Оставшаяся часть объекта Ерроррекорд и объекта RuntimeException зависят от объекта, который вызывает ключевое слово Throw.

Объект RunTimeException упаковывается в объект Ерроррекорд, а объект Ерроррекорд автоматически сохраняется в $Error автоматической переменной.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>Использование инструкции THROW для создания обязательного параметра

В отличие от прошлых версий PowerShell, не используйте ключевое слово Throw для проверки параметров. Правильный способ см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) .

## <a name="see-also"></a>См. также

- [about_Break](about_Break.md)
- [about_Continue](about_Continue.md)
- [about_Scopes](about_Scopes.md)
- [about_Trap](about_Trap.md)
- [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
