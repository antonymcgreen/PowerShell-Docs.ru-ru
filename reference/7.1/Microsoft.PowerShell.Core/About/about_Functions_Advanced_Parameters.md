---
description: Объясняется, как добавлять параметры в расширенные функции.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 2a5b13475dd648a9f778d23b4089da00351b237c
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "93233289"
---
# <a name="about-functions-advanced-parameters"></a>О функциях дополнительные параметры

## <a name="short-description"></a>Краткое описание

Объясняется, как добавлять параметры в расширенные функции.

## <a name="long-description"></a>Подробное описание

Вы можете добавить параметры в расширенные функции, которые вы пишете, и использовать атрибуты и аргументы параметров для ограничения значений параметров, которые пользователи будут передавать с параметром.

Параметры, добавляемые в функцию, доступны пользователям в дополнение к общим параметрам, которые PowerShell автоматически добавляет ко всем командлетам и расширенным функциям. Дополнительные сведения об общих параметрах PowerShell см. в разделе [about_CommonParameters](about_CommonParameters.md).

Начиная с PowerShell 3,0 можно использовать Сплаттинг с `@Args` для представления параметров в команде. Сплаттинг является допустимым для простых и расширенных функций. Дополнительные сведения см. в разделе [about_Functions](about_Functions.md) и [about_Splatting](about_Splatting.md).

## <a name="type-conversion-of-parameter-values"></a>Преобразование типов значений параметров

При предоставлении строк в качестве аргументов для параметров, которые предполагают другой тип, PowerShell неявно преобразует строки в целевой тип параметра.
Расширенные функции выполняют синтаксический анализ инвариантных значений параметров.

В отличие от этого, преобразование с учетом языка и региональных параметров выполняется во время привязки параметра для скомпилированных командлетов.

В этом примере мы создадим командлет и функцию скрипта, которая принимает `[datetime]` параметр. Текущий язык и региональные параметры изменены для использования параметров немецкого языка.
Дата в немецком формате передается в параметр.

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

Как показано выше, командлеты используют синтаксический анализ с учетом языка и региональных параметров для преобразования строки.

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

Дополнительные функции используют синтаксический анализ инвариантного языка и региональных параметров, что приводит к следующей ошибке.

```Output
Get-Date_Func: Cannot process argument transformation on parameter 'Date'.
Cannot convert value "19-06-2018" to type "System.DateTime". Error: "String
'19-06-2018' was not recognized as a valid DateTime."
```

## <a name="static-parameters"></a>Статические параметры

Статические параметры — это параметры, которые всегда доступны в функции.
Большинство параметров в командлетах и скриптах PowerShell являются статическими параметрами.

В следующем примере показано объявление параметра **ComputerName** , имеющего следующие характеристики.

- Это обязательный параметр (обязательно).
- Он принимает входные данные из конвейера.
- Он принимает массив строк в качестве входных данных.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a>Атрибуты параметров

В этом разделе описываются атрибуты, которые можно добавить в параметры функции.

Все атрибуты являются необязательными Однако если опустить атрибут **CmdletBinding** , то для распознавания в качестве расширенной функции функция должна включать атрибут **Parameter** .

В каждое объявление параметра можно добавить один или несколько атрибутов. Количество атрибутов, которые можно добавить в объявление параметра, не ограничено.

### <a name="parameter-attribute"></a>Атрибут параметра

Атрибут **Parameter** используется для объявления атрибутов параметров функции.

Атрибут **параметра** является необязательным, и его можно опустить, если ни один из параметров функций не требует атрибутов. Но для распознавания в качестве расширенной функции, а не для простой функции, функция должна иметь либо атрибут **CmdletBinding** , либо атрибут **Parameter** , либо и то, и другое.

Атрибут **Parameter** имеет аргументы, определяющие характеристики параметра, например, является ли параметр обязательным или необязательным.

Используйте следующий синтаксис для объявления атрибута **параметра** , аргумента и значения аргумента. Круглые скобки, которые заключают аргумент и его значение, должны следовать за **параметром** без промежуточного пробела.

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

Используйте запятые для разделения аргументов в круглых скобках. Используйте следующий синтаксис, чтобы объявить два аргумента атрибута **Parameter** .

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

Типы логических аргументов атрибута **Parameter** по умолчанию имеют **значение false** , если не указано в атрибуте **параметра** . Присвойте аргументу значение `$true` или просто перечислите аргумент по имени. Например, следующие атрибуты **параметров** эквивалентны.

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

Если вы используете атрибут **Parameter** без аргументов, в качестве альтернативы использованию атрибута **CmdletBinding** , по-прежнему требуются круглые скобки, следующие за именем атрибута.

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a>Обязательный аргумент

`Mandatory`Аргумент указывает, что параметр является обязательным. Если этот аргумент не указан, параметр является необязательным.

В следующем примере объявляется параметр **ComputerName** . Он использует `Mandatory` аргумент, чтобы сделать параметр обязательным.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a>Аргумент расположения

`Position`Аргумент определяет, является ли имя параметра обязательным, если параметр используется в команде. Если объявление параметра включает `Position` аргумент, то имя параметра может быть опущено, а PowerShell определяет неименованное значение параметра по его положению или порядку в списке неименованных значений параметров в команде.

Если `Position` аргумент не указан, имя параметра или псевдоним или аббревиатура имени параметра должно предшествовать значению параметра при использовании параметра в команде.

По умолчанию все параметры функции являются позиционированными. PowerShell присваивает номера позиций параметрам в порядке, в котором параметры объявляются в функции. Чтобы отключить эту функцию, задайте `PositionalBinding` для аргумента атрибута **CmdletBinding** значение `$False` . `Position`Аргумент имеет приоритет над значением `PositionalBinding` аргумента атрибута **CmdletBinding** . Дополнительные сведения см `PositionalBinding` . в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

Значение `Position` аргумента указывается как целое число. Значение " **0** " представляет первую точку в команде, значение " **1** " — вторую точку в команде и т. д.

Если у функции нет позиционированных параметров, PowerShell назначает позиции каждому параметру в соответствии с порядком, в котором объявляются параметры.
Тем не менее, рекомендуется не полагаться на это назначение. Если требуется, чтобы параметры были позиционированы, используйте `Position` аргумент.

В следующем примере объявляется параметр **ComputerName** . Он использует `Position` аргумент со значением **0**. В результате, если параметр `-ComputerName` не указан в команде, его значение должно быть первым или единственным неименованным значением параметра в команде.

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a>Параметерсетнаме, аргумент

`ParameterSetName`Аргумент задает набор параметров, к которому принадлежит параметр. Если набор параметров не задан, параметр относится ко всем наборам параметров, определенным функцией. Поэтому для каждого набора параметров должен быть хотя бы один параметр, который не является членом какого-либо другого набора параметров.

> [!NOTE]
> Для командлета или функции существует ограничение в 32 наборов параметров.

В следующем примере объявляется параметр **ComputerName** в `Computer` наборе параметров, параметр **username** в `User` наборе параметров и параметр **сводки** в обоих наборах параметров.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

`ParameterSetName`В каждом аргументе можно указать только одно значение и только один `ParameterSetName` аргумент в каждом атрибуте **параметра** . Чтобы указать, что параметр отображается более чем в одном наборе параметров, добавьте дополнительные атрибуты **параметров** .

В следующем примере параметр **сводки** явно добавляется к `Computer` `User` наборам параметров и. Параметр **сводки** является необязательным в `Computer` наборе параметров и обязателен в `User` наборе параметров.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

Дополнительные сведения о наборах параметров см. в разделе [о наборах параметров](about_parameter_sets.md).

#### <a name="valuefrompipeline-argument"></a>Валуефромпипелине, аргумент

`ValueFromPipeline`Аргумент указывает, что параметр принимает входные данные из объекта конвейера. Укажите этот аргумент, если функция принимает весь объект, а не только свойство объекта.

В следующем примере объявляется параметр **ComputerName** , который является обязательным и принимает объект, который передается в функцию из конвейера.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a>Валуефромпипелинебипропертинаме, аргумент

`ValueFromPipelineByPropertyName`Аргумент указывает, что параметр принимает входные данные из свойства объекта конвейера. Свойство объекта должно иметь то же имя или псевдоним, что и параметр.

Например, если функция имеет параметр **ComputerName** , а переданный объект имеет свойство **ComputerName** , значение свойства **ComputerName** присваивается параметру **ComputerName** функции.

В следующем примере объявляется обязательный параметр **ComputerName** , который принимает входные данные из свойства **ComputerName** объекта, которое передается в функцию через конвейер.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с _отложенной привязкой_ для параметра.
>
> Блок скрипта _с отложенной привязкой_ запускается автоматически во время **ParameterBinding оболочки**. Результат привязан к параметру. Отложенная привязка не работает для параметров, определенных как тип `ScriptBlock` или `System.Object` . Блок скрипта передается _без_ вызова.
>
> Сведения о блоках скриптов _с отложенной привязкой_ можно узнать здесь [about_Script_Blocks. md](about_Script_Blocks.md).

#### <a name="valuefromremainingarguments-argument"></a>Валуефромремаинингаргументс, аргумент

`ValueFromRemainingArguments`Аргумент указывает, что параметр принимает все значения параметра в команде, которые не назначены другим параметрам функции.

В следующем примере объявляется обязательный параметр **значения** и **оставшийся** параметр, принимающий все остальные значения параметров, которые передаются в функцию.

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 2 elements
0: one
1: two
```

> [!NOTE]
> До выхода версии PowerShell 6,2 коллекция **валуефромремаинингаргументс** была соединена как единая сущность с индексом **0**.

#### <a name="helpmessage-argument"></a>Хелпмессаже, аргумент

`HelpMessage`Аргумент задает строку, содержащую краткое описание параметра или его значение. PowerShell отображает это сообщение в командной строке, которая появляется, когда в команде отсутствует обязательное значение параметра. Этот аргумент не влияет на необязательные параметры.

В следующем примере объявляется обязательный параметр **ComputerName** и сообщение справки, поясняющее ожидаемое значение параметра.

Если для функции не существует другого синтаксиса [справки на основе комментариев](./about_comment_based_help.md) (например,), `.SYNOPSIS` это сообщение также отображается в `Get-Help` выходных данных.

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a>Alias - атрибут

Атрибут **Alias** устанавливает альтернативное имя для параметра.
Количество псевдонимов, которые можно назначить параметру, не ограничено.

В следующем примере показано объявление параметра, добавляющее псевдонимы **CN** и **MachineName** в обязательный параметр **ComputerName** .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a>Атрибут Суппортсвилдкардс

Атрибут **суппортсвилдкардс** используется для указания того, что параметр принимает подстановочные знаки. В следующем примере показано объявление параметра для обязательного параметра **пути** , который поддерживает подстановочные значения.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

Использование этого атрибута не включает автоматическую поддержку подстановочных знаков. Разработчик командлета должен реализовать код, обрабатывающий входные данные с подстановочными знаками. Поддерживаемые подстановочные знаки могут различаться в зависимости от базового API или поставщика PowerShell. Дополнительные сведения см. в разделе [about_Wildcards](about_Wildcards.md).

### <a name="parameter-and-variable-validation-attributes"></a>Атрибуты проверки параметров и переменных

Атрибуты проверки Direct PowerShell для проверки значений параметров, отправляемых пользователями при вызове расширенной функции. Если значения параметров не прошли проверку, создается ошибка и функция не вызывается. Проверка параметров применяется только к предоставленным входным данным, а любые другие значения, такие как значения по умолчанию, не проверяются.

Можно также использовать атрибуты проверки, чтобы ограничить значения, которые пользователи могут указывать для переменных. При использовании преобразователя типов вместе с атрибутом проверки преобразователь типов должен быть определен перед атрибутом.

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a>Атрибут проверки AllowNull

Атрибут **AllowNull** допускает значение обязательного параметра `$null` . В следующем примере объявляется параметр **компутеринфо** Hashtable, который может иметь значение **null** .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> Атрибут **AllowNull** не работает, если преобразователь типов имеет значение String, так как тип строки не принимает значение null. Для этого сценария можно использовать атрибут **алловемптистринг** .

### <a name="allowemptystring-validation-attribute"></a>Атрибут проверки Алловемптистринг

Атрибут **алловемптистринг** позволяет значению обязательного параметра быть пустой строкой ( `""` ). В следующем примере объявляется параметр **ComputerName** , который может иметь пустое строковое значение.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a>Атрибут проверки Алловемптиколлектион

Атрибут **алловемптиколлектион** позволяет значению обязательного параметра быть пустой коллекцией `@()` . В следующем примере объявляется параметр **ComputerName** , который может иметь пустое значение коллекции.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a>Атрибут проверки Валидатекаунт

Атрибут **валидатекаунт** указывает минимальное и максимальное число значений параметров, принимаемых параметром. PowerShell выдает ошибку, если число значений параметров в команде, вызывающей функцию, находится за пределами этого диапазона.

Приведенное ниже объявление параметра создает параметр **ComputerName** , который принимает от одного до пяти значений параметров.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a>Атрибут проверки Валидателенгс

Атрибут **валидателенгс** указывает минимальное и максимальное число символов в значении параметра или переменной. PowerShell выдает ошибку, если длина значения, указанного для параметра или переменной, находится за пределами диапазона.

В следующем примере имя каждого компьютера должно содержать от 1 до десяти символов.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

В следующем примере значение переменной `$number` должно быть как минимум одним символом в длину и не более десяти символов.

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> В этом примере значение `01` заключено в одинарные кавычки. Атрибут **валидателенгс** не принимает число без заключения в кавычки.

### <a name="validatepattern-validation-attribute"></a>Атрибут проверки ValidatePattern

Атрибут **ValidatePattern** указывает регулярное выражение, которое сравнивается с параметром или значением переменной. PowerShell выдает ошибку, если значение не соответствует шаблону регулярного выражения.

В следующем примере значение параметра должно содержать четырехзначное число, а каждая цифра должна быть числом от 0 до девяти.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

В следующем примере значение переменной `$number` должно быть ровно четырехзначным числом, а каждая цифра должна быть числом от 0 до девяти.

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a>Атрибут проверки Валидатеранже

Атрибут **валидатеранже** задает числовой диапазон или **валидатеранжекинд** значение перечисления для каждого значения параметра или переменной.
PowerShell выдает ошибку, если какое-либо значение выходит за пределы этого диапазона.

Перечисление **валидатеранжекинд** допускает следующие значения:

- **Положительное** число больше нуля.
- **Отрицательное** — число меньше нуля.
- **Неположительное** число, меньшее или равное нулю.
- **Неотрицательное** — число больше или равно нулю.

В следующем примере значение параметра **попыток** должно находиться в диапазоне от 0 до десяти.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

В следующем примере значение переменной `$number` должно находиться в диапазоне от 0 до десяти.

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

В следующем примере значение переменной `$number` должно быть больше нуля.

```powershell
[Int32][ValidateRange("Positive")]$number = 1
```

### <a name="validatescript-validation-attribute"></a>Атрибут проверки Валидатескрипт

Атрибут **валидатескрипт** указывает скрипт, используемый для проверки значения параметра или переменной. PowerShell передает значение в скрипт и выдает ошибку, если скрипт возвращает `$false` или вызывает исключение.

При использовании атрибута **валидатескрипт** проверяемое значение сопоставляется с `$_` переменной. Переменную можно использовать `$_` для ссылки на значение в скрипте.

В следующем примере значение параметра **евентдате** должно быть больше или равно текущей дате.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

В следующем примере значение переменной `$date` должно быть больше текущей даты и времени или равно ей.

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> При использовании **валидатескрипт** нельзя передавать `$null` значение в параметр. При передаче значения NULL **валидатескрипт** не может проверить аргумент.

### <a name="validateset-attribute"></a>Атрибут "Validate"

Атрибут **Validate** задает набор допустимых значений для параметра или переменной и включает Заполнение клавишей TAB. PowerShell выдает ошибку, если значение параметра или переменной не соответствует значению в наборе. В следующем примере значение параметра **detail** может быть только низким, средним или высоким.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

В следующем примере значение переменной `$flavor` должно быть шоколадным, Strawberry или обычный.

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

Проверка выполняется каждый раз, когда переменная присваивается даже внутри скрипта. Например, следующее приводит к ошибке во время выполнения:

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

#### <a name="dynamic-validateset-values"></a>Динамические значения Validate

**Класс** можно использовать для динамического создания значений для **Validate** во время выполнения. В следующем примере допустимые значения для переменной `$Sound` создаются с помощью **класса** с именем **саунднамес** , который проверяет три пути файловой системы для доступных звуковых файлов:

```powershell
Class SoundNames : System.Management.Automation.IValidateSetValuesGenerator {
    [String[]] GetValidValues() {
        $SoundPaths = '/System/Library/Sounds/',
            '/Library/Sounds','~/Library/Sounds'
        $SoundNames = ForEach ($SoundPath in $SoundPaths) {
            If (Test-Path $SoundPath) {
                (Get-ChildItem $SoundPath).BaseName
            }
        }
        return [String[]] $SoundNames
    }
}
```

`[SoundNames]`Затем класс реализуется как динамическое значение **Validate** следующим образом:

```powershell
Param(
    [ValidateSet([SoundNames])]
    [String]$Sound
)
```

### <a name="validatenotnull-validation-attribute"></a>Атрибут проверки Валидатенотнулл

Атрибут **валидатенотнулл** указывает, что значение параметра не может быть `$null` . PowerShell выдает ошибку, если параметр имеет значение `$null` .

Атрибут **валидатенотнулл** предназначен для использования, если параметр является необязательным и тип не определен или имеет преобразователь типов, который не может неявно преобразовать значение null, например **Object**. Если указать тип, который будет неявно преобразовывать значение null, например **строку** , значение NULL преобразуется в пустую строку даже при использовании атрибута **валидатенотнулл** . Для этого сценария используйте **валидатенотнуллоремпти**

В следующем примере значение параметра **ID** не может быть `$null` .

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a>Атрибут проверки Валидатенотнуллоремпти

Атрибут **валидатенотнуллоремпти** указывает, что значение параметра не может быть `$null` пустой строкой ( `""` ). PowerShell выдает ошибку, если параметр используется в вызове функции, но имеет значение `$null` , пустую строку ( `""` ) или пустой массив `@()` .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a>Атрибут проверки Валидатедриве

Атрибут **валидатедриве** указывает, что значение параметра должно представлять путь, который ссылается только на разрешенные диски. PowerShell выдает ошибку, если значение параметра относится к дискам, отличным от разрешенного. Наличие пути, за исключением самого диска, не проверяется.

Если используется относительный путь, текущий диск должен находиться в списке разрешенных дисков.

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a>Атрибут проверки Валидатеусердриве

Атрибут **валидатеусердриве** указывает, что значение параметра должно представлять путь, который ссылается на `User` диск. PowerShell выдает ошибку, если путь ссылается на другой диск. Атрибут проверки проверяет только наличие части пути, которая является диском.

Если используется относительный путь, то текущий диск должен быть `User` .

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

Вы можете определить `User` диск в достаточном объеме конфигураций сеансов администрирования (JEA). В этом примере мы создадим диск User:.

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a>Атрибут проверки Валидатетрустеддата

Этот атрибут был добавлен в 6.1.1 PowerShell.

В настоящее время атрибут используется внутри самой PowerShell и не предназначен для внешнего использования.

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, функции или скрипта, доступные только при определенных условиях.

Например, несколько командлетов поставщика имеют параметры, доступные только при использовании командлета на диске поставщика или в определенном пути к диску поставщика. Например, параметр **Encoding** доступен для `Add-Content` `Get-Content` командлетов, и, `Set-Content` только если он используется на диске файловой системы.

Можно также создать параметр, который появляется только в том случае, если другой параметр используется в команде функции или если другой параметр имеет определенное значение.

Динамические параметры могут быть полезными, но их следует использовать только при необходимости, так как пользователям может быть трудно обнаружить. Чтобы найти динамический параметр, пользователь должен быть в пути поставщика, использовать параметр **ArgumentList** `Get-Command` командлета или использовать параметр **path** в `Get-Help` .

Чтобы создать динамический параметр для функции или скрипта, используйте `DynamicParam` ключевое слово.

Синтаксис выглядит следующим образом:

`DynamicParam {<statement-list>}`

В списке инструкций используйте `If` оператор, чтобы указать условия, при которых параметр доступен в функции.

Используйте `New-Object` командлет, чтобы создать объект **System. Management. Automation. рунтимедефинедпараметер** для представления параметра и указать его имя.

Вы можете использовать `New-Object` команду, чтобы создать объект **System. Management. Automation. параметераттрибуте** для представления атрибутов параметра, например **обязательный** , параметр " **Расположение** " или " **валуефромпипелине** " или набор параметров.

В следующем примере показан пример функции со стандартными параметрами **Name** и **path** и необязательным динамическим параметром с именем **DP1**. Параметр **DP1** находится в `PSet1` наборе параметров и имеет тип `Int32` .
Параметр **DP1** доступен в `Get-Sample` функции только в том случае, если значение параметра **path** начинается с `HKLM:` , что указывает на то, что он используется на `HKEY_LOCAL_MACHINE` диске реестра.

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

Дополнительные сведения см. в разделе [рунтимедефинедпараметер](/dotnet/api/system.management.automation.runtimedefinedparameter).

## <a name="switch-parameters"></a>Параметры-переключатели

Параметры переключателей — это параметры без значения параметра. Они вступают в силу только в том случае, если они используются и имеют только один результат.

Например, параметром **Parameter параметра** **powershell.exe** является параметр Switch.

Чтобы создать параметр переключателя в функции, укажите `Switch` тип в определении параметра.

Пример:

```powershell
Param([Switch]<ParameterName>)
```

Кроме того, можно использовать другой метод:

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

Параметры переключателей просты в использовании и являются предпочтительными по сравнению с логическими параметрами, которые имеют более сложный синтаксис.

Например, чтобы использовать параметр Switch, пользователь вводит параметр в команду.

`-IncludeAll`

Чтобы использовать логический параметр, пользователь вводит параметр и логическое значение.

`-IncludeAll:$true`

При создании параметров переключателя следует тщательно выбирать имя параметра. Убедитесь, что имя параметра передает пользователю результат параметра.
Избегайте неоднозначных терминов, таких как **Фильтр** или **Максимальное** значение, которое может требовать значения.

## <a name="argumentcompleter-attribute"></a>Атрибут Аргументкомплетер

Атрибут **аргументкомплетер** позволяет добавлять значения заполнения клавишей TAB в конкретный параметр. Атрибут **аргументкомплетер** должен быть определен для каждого параметра, для которого требуется заполнение по клавише TAB. Как и в случае с **DynamicParameters** , доступные значения рассчитываются во время выполнения, когда пользователь нажимает клавишу <kbd>Tab</kbd> после имени параметра.

Чтобы добавить атрибут **аргументкомплетер** , необходимо определить блок скрипта, который определяет значения. Блок скрипта должен принимать следующие параметры в указанном ниже порядке. Имена параметров не важны, так как значения указаны по положению.

Синтаксис выглядит следующим образом:

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a>Блок сценария Аргументкомплетер

Для параметров блока сценария задаются следующие значения:

- `$commandName` (Расположение 0) — Этот параметр задает имя команды, для которой блок скрипта обеспечивает заполнение нажатием клавиши TAB.
- `$parameterName` (Расположение 1) — Этот параметр задан для параметра, значение которого требует заполнения нажатием клавиши TAB.
- `$wordToComplete` (Расположение 2) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.
- `$commandAst` (Расположение 3) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки. Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Расположение 4) — для этого параметра задается хэш-таблица `$PSBoundParameters` , содержащая для командлета перед нажатием пользователем <kbd>вкладки</kbd>. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

Блок скрипта **аргументкомплетер** должен выполнить девращение значений с помощью конвейера, например `ForEach-Object` , `Where-Object` или другого подходящего метода.
Возврат массива значений приводит к тому, что PowerShell обрабатывает весь массив как **одно** значение заполнения Tab.

В следующем примере заполнение клавиши TAB добавляется в параметр **value** . Если указан только параметр **value** , отображаются все возможные значения или аргументы для **параметра значение** . Если указан параметр **типа** , параметр **value** отображает только возможные значения для этого типа.

Кроме того, `-like` оператор гарантирует, что если пользователь вводит следующую команду и использует заполнение по <kbd>клавише TAB</kbd> , возвращается только **Apple** .

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a>См. также статью

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
