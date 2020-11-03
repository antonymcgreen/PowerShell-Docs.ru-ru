---
description: Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: dce019e9dc77d24843f254f978224cf5820d31aa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231217"
---
# <a name="about-throw"></a>О вызове

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Содержит описание ключевого слова Throw, генерирующего прерывающую ошибку.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Ключевое слово Throw вызывает завершающую ошибку. Для завершения обработки команды, функции или скрипта можно использовать ключевое слово Throw.

Например, можно использовать ключевое слово Throw в блоке script инструкции if для ответа на условие или в блоке catch оператора try-catch-finally. Можно также использовать ключевое слово Throw в объявлении параметра, чтобы сделать параметр функции обязательным.

Ключевое слово Throw может вызывать любой объект, например строку сообщения пользователя или объект, вызвавший ошибку.

## <a name="syntax"></a>SYNTAX

Синтаксис ключевого слова Throw выглядит следующим образом:

```powershell
throw [<expression>]
```

Выражение в синтаксисе Throw является необязательным. Если инструкция throw не отображается в блоке catch и не содержит выражение, возникает ошибка Скрипсалтед.

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

Если ключевое слово Throw используется в блоке catch без выражения, оно снова выдает текущий RuntimeException. Дополнительные сведения см. в разделе about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>СОЗДАНИЕ СТРОКИ

Необязательное выражение в операторе Throw может быть строкой, как показано в следующем примере:

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a>ВЫЗОВ ДРУГИХ ОБЪЕКТОВ

Выражение также может быть объектом, создающим объект, который представляет процесс PowerShell, как показано в следующем примере:

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

Для проверки ошибки можно использовать свойство TargetObject объекта Ерроррекорд в автоматической переменной $error.

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

Можно также вызвать исключение объекта Ерроррекорд или Microsoft .NET Framework. В следующем примере используется ключевое слово Throw для создания объекта System. FormatException.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a>ИТОГОВАЯ ОШИБКА

Ключевое слово Throw может создавать объект Ерроррекорд. Свойство Exception объекта Ерроррекорд содержит объект RuntimeException. Оставшаяся часть объекта Ерроррекорд и объекта RuntimeException зависят от объекта, который вызывает ключевое слово Throw.

Объект RunTimeException упаковывается в объект Ерроррекорд, а объект Ерроррекорд автоматически сохраняется в $Error автоматической переменной.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>ИСПОЛЬЗОВАНИЕ ИНСТРУКЦИИ THROW ДЛЯ СОЗДАНИЯ ОБЯЗАТЕЛЬНОГО ПАРАМЕТРА

Чтобы сделать параметр функции обязательным, можно использовать ключевое слово Throw.

Это альтернатива использованию обязательного параметра ключевого слова Parameter. При использовании обязательного параметра система запрашивает у пользователя требуемое значение параметра. При использовании ключевого слова Throw команда останавливается и отображает запись об ошибке.

Например, ключевое слово Throw в подвыражении параметра делает параметр пути обязательным параметром в функции.

В этом случае ключевое слово Throw выдает строку сообщения, но она является присутствием ключевого слова Throw, создающего завершающую ошибку, если параметр path не указан. Выражение, следующее за throw, является необязательным.

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
