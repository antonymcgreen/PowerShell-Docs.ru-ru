---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: 9a51c97def7cddf45c391ed91ff67ad97fbedf77
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "93230617"
---
# Add-Type

## Краткий обзор
Добавляет класс Microsoft .NET Core в сеанс PowerShell.

## SYNTAX

### Фромсаурце (по умолчанию)

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### фроммембер

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### фромпас

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### фромлитералпас

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### фромассемблинаме

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Add-Type`Командлет позволяет определить класс Microsoft .NET Core в сеансе PowerShell. Затем можно создать экземпляры объектов с помощью `New-Object` командлета и использовать объекты так же, как и любой объект .NET Core. При добавлении `Add-Type` команды в профиль PowerShell класс доступен во всех сеансах PowerShell.

Тип можно указать, указав существующую сборку или файлы исходного кода. Кроме того, можно указать встроенный или сохраненный в переменной исходный код. Можно даже указать только метод, а также `Add-Type` Определение и создание класса. В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell. Если указан исходный код, `Add-Type` компилирует указанный исходный код и создает сборку в памяти, содержащую новые типы .NET Core.

`Add-Type`Для указания альтернативного языка и компилятора можно использовать параметры, C# — это по умолчанию, параметры компилятора, зависимости сборок, пространство имен класса, имена типа и результирующая сборка.

## Примеры

### Пример 1. Добавление типа .NET в сеанс

В этом примере класс **BasicTest** добавляется в сеанс путем указания исходного кода, хранящегося в переменной. Класс **BasicTest** используется для добавления целых чисел, создания объекта и умножения целых чисел.

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

`$Source`Переменная хранит исходный код для класса. Тип имеет вызванный статический метод `Add` и метод, не являющийся статическим `Multiply` .

`Add-Type`Командлет добавляет класс в сеанс. Так как он использует встроенный исходный код, команда использует параметр **типедефинитион** для указания кода в `$Source` переменной.

`Add`Статический метод класса **BasicTest** использует символы двойного двоеточия ( `::` ) для указания статического члена класса. Добавляются целые числа и отображается сумма.

`New-Object`Командлет создает экземпляр класса **BasicTest** . Он сохраняет новый объект в `$BasicTestObject` переменной.

`$BasicTestObject` использует `Multiply` метод. Целые числа умножаются, а продукт отображается.

### Пример 2. Проверка добавленного типа

В этом примере `Get-Member` командлет используется для проверки объектов, `Add-Type` `New-Object` созданных командлетами и, в **примере 1** .

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

`Get-Member`Командлет возвращает тип и члены класса **BasicTest** , `Add-Type` добавленные в сеанс. `Get-Member`Команда обнаруживает, что это объект **System. RuntimeType** , производный от класса **System. Object** .

`Get-Member` **Статический** параметр получает статические свойства и методы класса **BasicTest** . Выходные данные показывают, что `Add` метод включен.

`Get-Member`Командлет возвращает элементы объекта, хранящегося в `$BasicTestObject` переменной.
`$BasicTestObject` был создан с помощью `New-Object` командлета с классом **BasicTest** . Результат показывает, что значение `$BasicTestObject` переменной является экземпляром класса **BasicTest** и включает член с именем `Multiply` .

### Пример 3. Добавление типов из сборки

В этом примере классы из сборки добавляются `NJsonSchema.dll` в текущий сеанс.

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

`Set-Location` использует параметр **path** для указания `$PSHOME` переменной. Переменная ссылается на каталог установки PowerShell, в котором находится DLL-файл.

`$AccType`Переменная хранит объект, созданный с помощью `Add-Type` командлета. `Add-Type` использует параметр **AssemblyName** для указания имени сборки. `*`Подстановочный знак звездочки () позволяет получить правильную сборку, даже если вы не уверены в ее имени или ее написании. Параметр **PassThru** создает объекты, представляющие классы, которые добавляются в сеанс.

### Пример 4. вызов собственных интерфейсов API Windows

В этом примере показано, как вызывать собственные API Windows в PowerShell. `Add-Type` использует механизм вызова неуправляемого кода (P/Invoke) для вызова функции `User32.dll` из PowerShell. Этот пример работает только на компьютерах под управлением операционной системы Windows.

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

`$Signature`Переменная хранит сигнатуру C# `ShowWindowAsync` функции. Чтобы обеспечить видимость полученного метода в сеансе PowerShell, `public` ключевое слово было добавлено к стандартной сигнатуре. Дополнительные сведения см. в разделе [функция showWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).

`$ShowWindowAsync`Переменная хранит объект, созданный `Add-Type` параметром **PassThru** .
`Add-Type`Командлет добавляет `ShowWindowAsync` функцию в сеанс PowerShell как статический метод. Команда использует параметр **MemberDefinition** для указания определения метода, сохраненного в `$Signature` переменной. Команда использует параметры **Name** и **Namespace** , чтобы указать имя и пространство имен для класса. Параметр **PassThru** создает объект, представляющий типы.

Новый `ShowWindowAsync` статический метод используется в командах для сворачивания и восстановления консоли PowerShell. Метод принимает два параметра: маркер окна и целое число, которое указывает, как отображается окно.

Для сворачивания консоли PowerShell `ShowWindowAsync` использует `Get-Process` командлет с `$PID` автоматической переменной для получения процесса, в котором размещается текущий сеанс PowerShell. Затем используется свойство **маинвиндовхандле** текущего процесса и значение `2` , представляющее `SW_MINIMIZE` значение.

Для восстановления окна `ShowWindowAsync` использует значение `4` для расположения окна, которое представляет `SW_RESTORE` значение.

Чтобы развернуть окно, используйте значение `3` , представляющее `SW_MAXIMIZE` .

## PARAMETERS

### -AssemblyName

Задает имя сборки, включающей типы. `Add-Type` принимает типы из указанной сборки. Этот параметр является обязательным при создании типов на основе имени сборки.

Введите полное или простое имя сборки, также называемое частичным именем. В именах сборок можно использовать подстановочные знаки. Если вы вводите простое или частичное имя, `Add-Type` разрешаете его в полное имя, а затем использует полное имя для загрузки сборки.

Этот параметр не принимает путь или имя файла. Чтобы ввести путь к файлу библиотеки динамической компоновки (DLL) сборки, используйте параметр **path** .

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Компилероптионс

Указывает параметры для компилятора исходного кода. Эти параметры отправляются в компилятор без проверки.

Этот параметр позволяет указать компилятору создать исполняемый файл, внедрить ресурсы или задать параметры командной строки, например `/unsafe` параметр.

В одной команде нельзя использовать параметры **компилероптионс** и **референцедассемблиес** .

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Игнореварнингс

Игнорирует предупреждения компилятора. Используйте этот параметр, чтобы предотвратить `Add-Type` обработку предупреждений компилятора как ошибок.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### — Язык

Задает язык, который используется в исходном коде. Допустимое значение для этого параметра — **CSharp** .

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы. В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberDefinition

Указывает новые свойства или методы для класса. `Add-Type` создает код шаблона, необходимый для поддержки свойств или методов.

В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает имя создаваемого класса. Этот параметр является обязательным при создании типа из определения члена.

Имя типа и пространство имен должны быть уникальными в пределах сеанса. Невозможно выгрузить тип или изменить его.
Чтобы изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.
В противном случае произойдет сбой команды.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Задает пространство имен для типа.

Если этот параметр не включен в команду, тип создается в пространстве имен **Microsoft. PowerShell. Commands. аддтипе. аутоженератедтипес** . Если параметр включен в команду с пустым строковым значением или значением `$Null` , то тип создается в глобальном пространстве имен.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аутпутассембли

Создает DLL-файл для сборки с заданным именем в расположении. Введите необязательный путь и имя файла. Можно использовать подстановочные знаки. По умолчанию `Add-Type` создает сборку только в памяти.

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -OutputType

Указывает тип вывода выходной сборки. По умолчанию тип вывода не указывается. Этот параметр допустим только в том случае, если в команде указана выходная сборка. Дополнительные сведения о значениях см. в разделе [Аутпутассемблитипе enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).

Для этого параметра допустимы следующие значения:

- консолеаппликатион
- Библиотека
- виндовсаппликатион

> [!IMPORTANT]
> `ConsoleApplication`Значения и `WindowsApplication` не создают рабочие выходные данные и не должны использоваться.

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект **System.Runtime** , представляющий добавленные типы. По умолчанию этот командлет не создает никаких выходных данных.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы.

При отправке файлов исходного кода `Add-Type` компилирует код в файлы и создает сборку типов в памяти. Расширение файла, указанное в значении **path** , определяет компилятор, который `Add-Type` использует.

При отправке файла сборки `Add-Type` принимает типы из сборки. Чтобы указать сборку в памяти или глобальный кэш сборок, используйте параметр **AssemblyName** .

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Референцедассемблиес

Указывает сборки, от которых зависит тип. По умолчанию `Add-Type` ссылки `System.dll` и `System.Management.Automation.dll` . Ссылки на сборки, указываемые этим параметром, создаются в дополнение к сборкам по умолчанию.

Начиная с PowerShell 6, **референцедассемблиес** не включает сборки .NET по умолчанию. В значение, передаваемое этому параметру, необходимо включить определенную ссылку на них.

В одной команде нельзя использовать параметры **компилероптионс** и **референцедассемблиес** .

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Типедефинитион

Указывает исходный код, содержащий определения типов. Введите исходный код в строку или автономную строку либо введите переменную, которая содержит исходный код. Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).

Включите объявление пространства имен в определение типа. Если опустить объявление пространства имен, имя типа может совпасть с именем или ярлыком другого типа, вызывая непреднамеренную перезапись. Например, если определить тип с именем **Exception** , скрипты, использующие **исключение** в качестве ярлыка для **System. Exception** , завершатся ошибкой.

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Усингнамеспаце

Задает другие пространства имен, которые требуются для класса. Это очень похоже на ключевое слово C# `Using` .

По умолчанию `Add-Type` ссылается на пространство имен **System** . При использовании параметра **MemberDefinition** `Add-Type` также ссылается на пространство имен **System. Runtime. InteropServices** по умолчанию. Ссылки на пространства имен, добавляемые с помощью **UsingNamespace** , создаются в дополнение к пространствами имен по умолчанию.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете отправить объекты по конвейеру в `Add-Type` .

## Выходные данные

### None или System. Type

При использовании параметра **PassThru** `Add-Type` возвращает объект **System. Type** , представляющий новый тип. В противном случае этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Добавляемые типы существуют только в текущем сеансе. Чтобы использовать типы во всех сеансах, добавьте их в профиль PowerShell. Дополнительные сведения о профиле см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Имена типов и пространства имен должны быть уникальными в пределах сеанса. Невозможно выгрузить тип или изменить его. Если необходимо изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.
В противном случае произойдет сбой команды.

В Windows PowerShell (версия 5,1 и более ранние версии) необходимо использовать `Add-Type` для всех компонентов, которые еще не загружены. Чаще всего это относится к сборкам, находящихся в глобальном кэше сборок (GAC).
В PowerShell 6 и более поздних версий отсутствует глобальный кэш сборок, поэтому PowerShell устанавливает собственные сборки в `$PSHome` .
Эти сборки автоматически загружаются по запросу, поэтому их не нужно использовать `Add-Type` для их загрузки. Тем не менее, использование имеет разрешение на `Add-Type` разрешение неявной совместимости скриптов с любой версией PowerShell.

Сборки в глобальном кэше сборок могут загружаться по имени типа, а не по пути. Для загрузки сборок из произвольного пути требуется `Add-Type` , так как эти сборки не могут быть загружены автоматически.

## Связанные ссылки

[about_Profiles](../Microsoft.PowerShell.Core/About/about_profiles.md)

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Add-Member](Add-Member.md)

[New-Object](New-Object.md)

[аутпутассемблитипе](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[Вызов неуправляемого кода (P/Invoke)](/dotnet/standard/native-interop/pinvoke)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
