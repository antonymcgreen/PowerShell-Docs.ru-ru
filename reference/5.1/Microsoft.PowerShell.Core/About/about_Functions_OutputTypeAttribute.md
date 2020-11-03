---
description: Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: cff471057a656f4c603d058f9db23a1ea003cd2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232405"
---
# <a name="about-functions-outputtypeattribute"></a>О функциях Аутпуттипеаттрибуте

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Атрибут OutputType перечисляет типы .NET объектов, возвращаемых функциями. Можно использовать его необязательный параметр Параметерсетнаме для вывода списка различных типов выходных данных для каждого набора параметров.

Атрибут OutputType поддерживается в простых и расширенных функциях. Он не зависит от атрибута CmdletBinding.

Атрибут OutputType предоставляет значение свойства OutputType объекта **System. Management. Automation. FunctionInfo** , `Get-Command` возвращаемого командлетом.

Значение атрибута OutputType предназначено только для документации. Он не является производным от кода функции или не сравнивается с фактическим выходом функции. Таким образом, значение может быть неточным.

## <a name="syntax"></a>SYNTAX

Атрибут OutputType функций имеет следующий синтаксис:

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

Параметр **параметерсетнаме** является необязательным.

В атрибут OutputType можно перечислить несколько типов.

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

Можно использовать параметр **параметерсетнаме** , чтобы указать, что различные наборы параметров возвращают разные типы.

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

Поместите операторы атрибута OutputType в список Attributes, предшествующий `Param` оператору.

В следующем примере показано размещение атрибута OutputType в простой функции.

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

В следующем примере показано размещение атрибута OutputType в расширенных функциях.

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a>Примеры

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a>Пример 1. Создание функции, имеющей значение OutputType строки

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

Чтобы просмотреть результирующее свойство типа выходных данных, используйте `Get-Command` командлет.

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a>Пример 2. Использование выходного атрибута для указания динамических типов выходных данных

Следующая Расширенная функция использует атрибут OutputType, чтобы указать, что функция возвращает различные типы в зависимости от набора параметров, используемого в команде функции.

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a>Пример 3. показывает, что фактические выходные данные отличаются от значения OutputType

В следующем примере показано, что значение свойства Тип выходных данных отображает значение атрибута OutputType, даже если оно неточно.

`Get-Time`Функция возвращает строку, содержащую краткую форму времени в любом объекте DateTime. Однако атрибут OutputType сообщает, что он возвращает объект **System. DateTime** .

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

`GetType()`Метод подтверждает, что функция возвращает строку.

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

Однако свойство OutputType, получающее его значение из атрибута OutputType, сообщает о том, что функция возвращает объект **DateTime** .

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a>Пример 4. функция, которая не должна иметь выходных данных

В следующем примере показана пользовательская функция, которая должна выполнять действия и не возвращать никаких результатов.

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a>ПРИМЕЧАНИЯ

Значением свойства OutputType объекта **FunctionInfo** является массив объектов **System. Management. Automation. пстипенаме** , каждый из которых имеет свойства Name и Type.

Чтобы получить только имя каждого выходного типа, используйте команду в следующем формате:

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

Значение свойства OutputType может быть равно null. Используйте значение null, если выходные данные не являются типом .NET, например **WMI** -объектом или форматированным представлением объекта.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)
