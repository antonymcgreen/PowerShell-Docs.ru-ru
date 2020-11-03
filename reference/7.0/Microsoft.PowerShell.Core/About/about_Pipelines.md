---
description: Объединение команд в конвейеры в PowerShell
keywords: powershell,командлет
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: bf5e57389d286a2bb1cca9b3dd73ea59674461ec
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232214"
---
# <a name="about-pipelines"></a>О конвейерах

## <a name="short-description"></a>Краткое описание

Объединение команд в конвейеры в PowerShell

## <a name="long-description"></a>Подробное описание

Конвейер — это серия команд, Соединенных операторами конвейера ( `|` ) (ASCII 124). Каждый оператор конвейера отправляет результаты предыдущей команды следующей команде.

Выходные данные первой команды можно отправить для обработки в качестве входных данных во вторую команду. И эти выходные данные можно отправить в еще одну команду. Результатом является сложная цепочка команд или _конвейер_ , состоящая из ряда простых команд.

Например, примененная к объекту директива

```powershell
Command-1 | Command-2 | Command-3
```

В этом примере объекты, `Command-1` порождаемые, отправляются в `Command-2` .
`Command-2` обрабатывает объекты и отправляет их в `Command-3` . `Command-3` обрабатывает объекты и отправляет их по конвейеру. Так как в конвейере больше нет команд, результаты отображаются в консоли.

В конвейере команды обрабатываются в порядке слева направо. Обработка обрабатывается как одна операция, а выходные данные отображаются по мере их создания.

Вот простой пример. Следующая команда получает процесс блокнота и останавливает его.

Например, примененная к объекту директива

```powershell
Get-Process notepad | Stop-Process
```

Первая команда использует `Get-Process` командлет для получения объекта, представляющего процесс блокнота. Он использует оператор конвейера ( `|` ) для отправки объекта Process в `Stop-Process` командлет, который останавливает процесс блокнота. Обратите внимание, что у `Stop-Process` команды нет параметра **Name** или **ID** для указания процесса, так как указанный процесс отправляется через конвейер.

Этот пример конвейера получает текстовые файлы в текущем каталоге, выбирает только те файлы, которые имеют длину более 10 000 байт, сортирует их по длине и отображает имя и длину каждого файла в таблице.

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

Этот конвейер состоит из четырех команд в указанном порядке. На следующем рисунке показаны выходные данные каждой команды, которые передаются в следующую команду конвейера.

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a>Использование конвейеров

Большинство командлетов PowerShell предназначены для поддержки конвейеров. В большинстве случаев можно _передать_ результаты командлета **Get** в другой командлет того же существительного.
Например, выходные данные командлета можно передать в `Get-Service` `Start-Service` `Stop-Service` командлеты или.

Этот пример конвейера запускает службу WMI на компьютере:

```powershell
Get-Service wmi | Start-Service
```

Другой пример: можно передать выходные данные `Get-Item` `Get-ChildItem` поставщика реестра PowerShell в `New-ItemProperty` командлет. В этом примере в раздел реестра **MyCompany** добавляется новая запись реестра **NoOfEmployees** со значением **8124**.

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

Многие командлеты служебной программы, такие как,,, `Get-Member` `Where-Object` и, `Sort-Object` `Group-Object` `Measure-Object` используются практически исключительно в конвейерах. К этим командлетам можно передать любой тип объекта. В этом примере показано, как сортировать все процессы на компьютере по количеству открытых дескрипторов в каждом процессе.

```powershell
Get-Process | Sort-Object -Property handles
```

Объекты можно передавать в командлеты форматирования, экспорта и вывода, такие как,, `Format-List` `Format-Table` `Export-Clixml` , `Export-CSV` и `Out-File` .

В этом примере показано, как использовать `Format-List` командлет для отображения списка свойств объекта процесса.

```powershell
Get-Process winlogon | Format-List -Property *
```

С небольшой практикой вы обнаружите, что объединение простых команд в конвейеры экономит время и ввод и делает создание сценариев более эффективным.

## <a name="how-pipelines-work"></a>Принцип работы конвейеров

В этом разделе объясняется, как входные объекты привязаны к параметрам командлета и обрабатываются во время выполнения конвейера.

### <a name="accepts-pipeline-input"></a>Принимает входные данные конвейера

Для поддержки конвейера принимающий командлет должен иметь параметр, который принимает входные данные конвейера. Используйте `Get-Help` команду с параметрами **Full** или **Parameter** , чтобы определить, какие параметры командлета принимают входные данные конвейера.

Например, чтобы определить, какой из параметров `Start-Service` командлета принимает входные данные конвейера, введите:

```powershell
Get-Help Start-Service -Full
```

or

```powershell
Get-Help Start-Service -Parameter *
```

Справка по `Start-Service` командлету показывает, что только параметры **InputObject** и **Name** принимают входные данные конвейера.

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

При отправке объектов через конвейер в `Start-Service` PowerShell пытается связать объекты с параметрами **InputObject** и **Name** .

### <a name="methods-of-accepting-pipeline-input"></a>Методы приема входных данных конвейера

Параметры командлетов могут принимать входные данные конвейера одним из двух способов:

- **Бивалуе** : параметр принимает значения, которые соответствуют ожидаемому типу .NET или могут быть преобразованы в этот тип.

  Например, параметр **Name** `Start-Service` принимает входные данные конвейера по значению. Он может принимать строковые объекты или объекты, которые могут быть преобразованы в строки.

- **Бипропертинаме** : параметр принимает входные данные только в том случае, если входной объект имеет свойство с тем же именем, что и параметр.

  Например, параметр Name объекта `Start-Service` может принимать объекты со свойством **Name** . Чтобы получить список свойств объекта, передайте его по конвейеру `Get-Member` .

Некоторые параметры могут принимать объекты по значению или имени свойства, что упрощает получение входных данных из конвейера.

### <a name="parameter-binding"></a>Привязка параметра

При передаче объектов из одной команды в другую команда PowerShell пытается связать переданный объект с параметром командлета получения.

Компонент привязки параметров PowerShell связывает входные объекты с параметрами командлета в соответствии со следующими критериями:

- Параметр должен принимать входные данные из конвейера.
- Параметр должен принимать тип отправляемого объекта или тип, который может быть преобразован в ожидаемый тип.
- Параметр не использовался в команде.

Например, `Start-Service` у командлета есть много параметров, но только два из них, **Name** и **InputObject** принимают входные данные конвейера. Параметр **Name** принимает строки, а параметр **InputObject** принимает объекты службы. Таким образом, можно передать строки, объекты служб и объекты со свойствами, которые могут быть преобразованы в строковые или служебные объекты.

PowerShell управляет привязкой параметров как можно эффективнее. Нельзя предложить или принудительно выполнить привязку PowerShell к конкретному параметру. Команда завершается ошибкой, если PowerShell не удается привязать перенаправленные объекты.

Дополнительные сведения об устранении ошибок привязки см. в разделе [исследование ошибок конвейера](#investigating-pipeline-errors) далее в этой статье.

### <a name="one-at-a-time-processing"></a>Однократная обработка

Передача объектов в команду во многом аналогична использованию параметра команды для отправки объектов. Рассмотрим пример конвейера. В этом примере мы используем конвейер для вывода таблицы объектов службы.

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

Функционально, это аналогично использованию параметра **InputObject** объекта `Format-Table` для отправки коллекции объектов.

Например, можно сохранить коллекцию служб в переменную, которая передается с помощью параметра **InputObject** .

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

Или можно внедрить команду в параметр **InputObject** .

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

Однако есть и важное отличие. При передаче нескольких объектов команде PowerShell по одной команде отправляет объекты в команду по одному. При использовании параметра команды объекты отправляются как один объект массива. Это небольшое различие имеет значительные последствия.

При выполнении конвейера PowerShell автоматически перечисляет любой тип, реализующий интерфейс, `IEnumerable` и отправляет элементы по одному в конвейере. Исключением является `[hashtable]` , что требует вызова `GetEnumerator()` метода.

В следующих примерах массив и хэш-таблица передаются в `Measure-Object` командлет для подсчета количества объектов, полученных из конвейера. Массив содержит несколько элементов, а таблица Hashtable содержит несколько пар "ключ-значение". Только массив перечисляется по одному за раз.

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Аналогично, если передать несколько объектов Process из `Get-Process` командлета в `Get-Member` командлет, PowerShell отправляет каждый объект процесса по одному за раз в `Get-Member` . `Get-Member` Отображает класс .NET (тип) объектов процесса, а также их свойства и методы.

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> `Get-Member` устраняет дубликаты, поэтому, если все объекты имеют одинаковый тип, он отображает только один тип объекта.

Однако если используется параметр **InputObject** из `Get-Member` , то `Get-Member` получает массив объектов **System. Diagnostics. Process** как единый блок. Он отображает свойства массива объектов. (Обратите внимание на символ массива ( `[]` ) после имени типа **System. Object** .)

Например, примененная к объекту директива

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

Этот результат может быть не так, как планировалось. Но после того, как вы понимаете его, вы можете использовать его. Например, все объекты массива имеют свойство **Count** . Его можно использовать для подсчета количества процессов, запущенных на компьютере.

Например, примененная к объекту директива

```powershell
(Get-Process).count
```

Важно помнить, что объекты, отправленные по конвейеру, доставляются по одному за раз.

## <a name="investigating-pipeline-errors"></a>Исследование ошибок конвейера

Если PowerShell не может связать переданный объект с параметром командлета получения, команда завершается ошибкой.

В следующем примере мы пытаемся переместить запись реестра из одного раздела реестра в другой. `Get-Item`Командлет возвращает путь назначения, который затем передается в `Move-ItemProperty` командлет. `Move-ItemProperty`Команда задает текущий путь и имя перемещаемой записи реестра.

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

Команда завершается ошибкой, и PowerShell выводит следующее сообщение об ошибке:

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

Для изучения используйте `Trace-Command` командлет для трассировки компонента привязки параметров PowerShell. В следующем примере выполняется трассировка привязки параметра во время выполнения конвейера. Параметр **PSHost** отображает результаты трассировки в консоли, а параметр **FilePath** отправляет результаты трассировки в `debug.txt` файл для последующей ссылки.

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

Результаты трассировки имеют длину, но они показывают значения, привязанные к `Get-Item` командлету, а затем именованные значения, привязанные к `Move-ItemProperty` командлету.

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

Наконец, он показывает, что попытка привязки пути к параметру **назначения** `Move-ItemProperty` не удалась.

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

Используйте `Get-Help` командлет для просмотра атрибутов **целевого** параметра.

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

Результаты показывают, что **назначение** принимает только входные данные конвейера "по имени свойства". Таким образом, объект последовательного объекта должен иметь свойство с именем **Destination**.

Используйте `Get-Member` для просмотра свойств объекта, поступающих из `Get-Item` .

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

Выходные данные показывают, что элемент является объектом **Microsoft. Win32. RegistryKey** , который не имеет **целевого** свойства. Это объясняет, почему команда завершилась ошибкой.

Параметр **path** принимает входные данные конвейера по имени или по значению.

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

Чтобы исправить эту команду, необходимо указать назначение в `Move-ItemProperty` командлете и использовать `Get-Item` для получения **пути** к элементу, который нужно переместить.

Например, примененная к объекту директива

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a>Внутреннее продолжение строки

Как уже говорилось, конвейер — это серия команд, Соединенных операторами конвейера ( `|` ), обычно написанными на одной строке. Однако для удобства чтения PowerShell позволяет разбить конвейер на несколько строк.
Если оператор Pipe является последним маркером в строке, средство синтаксического анализа PowerShell присоединяет следующую строку к текущей команде, чтобы продолжить построение конвейера.

Например, следующий однострочный конвейер:

```powershell
Command-1 | Command-2 | Command-3
```

можно записать следующим образом:

```powershell
Command-1 |
  Command-2 |
    Command-3
```

Начальные пробелы в последующих строках не являются значимыми. Отступ повышает удобочитаемость.

В PowerShell 7 добавлена поддержка продолжения конвейеров с символом конвейера в начале строки. В следующих примерах показано, как можно использовать эту новую функциональность.

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> При интерактивной работе в оболочке Вставка кода с конвейерами в начале строки выполняется только при использовании <kbd>клавиши CTRL</kbd> + <kbd>V</kbd> для вставки.
> Щелкните правой кнопкой мыши операции вставки, чтобы вставить строки по одному. Поскольку строка не заканчивается символом конвейера, PowerShell считает входные данные полными и выполняет эту строку как введенную.

## <a name="see-also"></a>См. также:

[about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)

[about_Objects](about_objects.md)

[about_Parameters](about_parameters.md)

[about_Command_Syntax](about_command_syntax.md)

[about_ForEach](about_foreach.md)
