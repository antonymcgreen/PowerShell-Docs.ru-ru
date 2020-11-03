---
description: Содержит описание языка WQL, используемого для получения объектов WMI в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232258"
---
# <a name="about-wql"></a>Сведения о WQL

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Содержит описание языка WQL, используемого для получения объектов WMI в Windows PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

WQL — это язык запросов инструментарий управления Windows (WMI) (WMI), который используется для получения информации от WMI.

Для выполнения запросов WMI в Windows PowerShell не требуется использовать WQL.
Вместо этого можно использовать параметры командлетов Get-WmiObject или Get-CimInstance. Запросы WQL выполняются несколько быстрее, чем стандартные команды Get-WmiObject и улучшенная производительность очевидна, когда команды выполняются на сотнях систем. Однако следует убедиться, что время, затрачиваемое на написание успешного запроса WQL, не перевешивает повышение производительности.

Основные инструкции WQL, для которых необходимо использовать WQL, — SELECT, WHERE и from.

## <a name="when-to-use-wql"></a>КОГДА СЛЕДУЕТ ИСПОЛЬЗОВАТЬ WQL

При работе с WMI, особенно с WQL, не забывайте, что вы также используете Windows PowerShell. Часто, если запрос WQL не работает должным образом, проще использовать стандартную команду Windows PowerShell, чем отладка WQL-запроса.

Если вы не возвращаете большие объемы данных из нескольких удаленных систем с ограниченной пропускной способностью, редко бывает, что тратить время на совершение сложных запросов WQL и сложные, если существует вполне приемлемый командлет Windows, который делает то же самое, если немного медленнее.

## <a name="using-the-select-statement"></a>ИСПОЛЬЗОВАНИЕ ИНСТРУКЦИИ SELECT

Типичный запрос WMI начинается с инструкции SELECT, которая получает все свойства или определенные свойства класса WMI. Чтобы выбрать все свойства класса WMI, используйте звездочку ( \* ). Ключевое слово FROM указывает класс WMI.

Инструкция SELECT имеет следующий формат:

```
Select <property> from <WMI-class>
```

Например, следующая инструкция SELECT выбирает все свойства (*) из экземпляров класса Win32_Bios WMI.

```
Select * from Win32_Bios
```

Чтобы выбрать определенное свойство класса WMI, поместите имя свойства между ключевыми словами SELECT и from.

Следующий запрос выбирает только имя BIOS из класса Win32_Bios WMI. Команда сохраняет запрос в переменной $queryName.

```
Select Name from Win32_Bios
```

Чтобы выбрать несколько свойств, используйте запятые для разделения имен свойств.
Следующий запрос WMI выбирает имя и версию класса Win32_Bios WMI. Команда сохраняет запрос в переменной $queryNameVersion.

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a>ИСПОЛЬЗОВАНИЕ WQL-ЗАПРОСА

Существует три способа использования WQL-запроса в команде Windows PowerShell.

- Использование командлета Get-WmiObject
- Использование командлета Get-CimInstance
- Используйте ускоритель типа [вмисеарчер].

## <a name="using-the-get-wmiobject-cmdlet"></a>ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТА GET-WMIOBJECT

Самый простой способ использовать WQL-запрос заключается в заключении его в кавычки (в виде строки), а затем используйте строку запроса в качестве значения параметра запроса командлета Get-WmiObject, как показано в следующем примере.

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Можно также сохранить инструкцию WQL в переменной, а затем использовать переменную в качестве значения параметра запроса, как показано в следующей команде.

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

Можно использовать любой из форматов с любой инструкцией WQL. Следующая команда использует запрос в переменной $queryName, чтобы получить только свойства Name и Version BIOS системы.

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

Помните, что для получения того же результата можно использовать параметры командлета Get-WmiObject. Например, следующая команда также возвращает значения свойств Name и Version экземпляров класса Win32_Bios WMI.

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a>ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТА GET-CIMINSTANCE

Начиная с Windows PowerShell 3,0, можно использовать командлет Get-CimInstance для выполнения WQL-запросов.

Get-CimInstance получает экземпляры классов, совместимых с CIM, включая классы WMI. Командлеты CIM, появившиеся в Windows PowerShell 3,0, выполняют те же задачи, что и командлеты WMI. Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM), который позволяет командлетам использовать те же методы для управления компьютерами и компьютерами Windows, на которых работают другие операционные системы.

Следующая команда использует командлет Get-CimInstance для выполнения WQL-запроса.

Любой запрос WQL, который можно использовать с Get-WmiObject, также можно использовать с Get-CimInstance.

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Get-CimInstance возвращает объект CimInstance, а не ManagementObject, который Get-WmiObject возвращает, но объекты весьма похожи.

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a>Использование УСКОРИТЕЛя типов [вмисеарчер]

Ускоритель типа [вмисеарчер] создает объект Манажементобжектсеарчер из строки инструкции WQL. Объект Манажементобжектсеарчер имеет множество свойств и методов, но самый простой метод — это метод Get, который вызывает заданный WMI-запрос и возвращает результирующие объекты.

Используя [вмисеарчер], вы получаете простой доступ к классу .NET Framework Манажементобжектсеарчер. Это позволяет запрашивать Инструментарий WMI и настраивать способ выполнения запроса.

Чтобы использовать ускоритель типа [вмисеарчер], выполните следующие действия.

1. Приведите строку WQL в объект Манажементобжектсеарчер.
2. Вызовите метод Get объекта Манажементобжектсеарчер.

Например, следующая команда приводит к появлению запроса SELECT ALL, сохраняет результат в переменной $bios, а затем вызывает метод Get объекта Манажементобжектсеарчер в переменной $bios.

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Примечание. по умолчанию отображаются только выбранные свойства объекта. Эти свойства определяются в Types.ps1XML-файле.

Для приведения запроса или переменной можно использовать ускоритель типа [вмисеарчер]. В следующем примере для приведения переменной используется ускоритель типа [вмисеарчер]. Результат такой же.

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

При использовании ускорителя типа [вмисеарчер] строка запроса преобразуется в объект Манажементобжектсеарчер, как показано в следующих командах.

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

Этот формат команды работает с любым запросом. Следующая команда возвращает значение свойства Name класса WMI Win32_Bios.

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

Эту операцию можно выполнить в одной команде, хотя команда немного сложнее интерпретировать.

В этом формате вы используете ускоритель типа [вмисеарчер] для приведения строки запроса WQL к Манажементобжектсеарчер, а затем вызываете метод Get для объекта--ALL в одной команде. Круглые скобки (), которые заключают приведенную строку в оболочку Windows PowerShell для приведения строки перед вызовом метода.

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a>ИСПОЛЬЗОВАНИЕ БАЗОВОЙ ИНСТРУКЦИИ WQL WHERE

Оператор WHERE устанавливает условия для данных, возвращаемых инструкцией SELECT.

Инструкция WHERE имеет следующий формат:

```
where <property> <operator> <value>
```

Пример:

```
where Name = 'Notepad.exe'
```

Инструкция WHERE используется с инструкцией SELECT, как показано в следующем примере.

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

При использовании инструкции WHERE имя и значение свойства должны быть точными.

Например, следующая команда получает процессы Notepad на локальном компьютере.

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

Однако следующая команда завершается ошибкой, так как имя процесса включает расширение имени файла ". exe".

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a>ОПЕРАТОРЫ СРАВНЕНИЯ ОПЕРАТОРОВ WHERE

Следующие операторы являются допустимыми в инструкции WQL WHERE.

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

Существуют и другие операторы, но это те, которые используются для сравнения.

Например, следующий запрос выбирает свойства Name и Priority из процессов в классе Win32_Process, где приоритет процесса больше или равен 11. Командлет Get-WmiObject выполняет запрос.

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a>ИСПОЛЬЗОВАНИЕ ОПЕРАТОРОВ WQL В ПАРАМЕТРЕ FILTER

Операторы WQL также можно использовать в значении параметра Filter командлетов Get-WmiObject или Get-CimInstance, а также в значениях параметров запроса этих командлетов.

Например, следующая команда возвращает свойства Name и ProcessID последних пяти процессов, которые имеют значения ProcessID, превышающие 1004. Команда использует параметр Filter для указания условия ProcessID.

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a>ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА LIKE

Оператор Like позволяет использовать подстановочные знаки для фильтрации результатов WQL-запроса.

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

Если оператор Like используется без подстановочных знаков или операторов диапазона, он ведет себя как оператор равенства (=) и возвращает объекты только в том случае, если они точно соответствуют шаблону.

Операцию Range можно объединить с подстановочным знаком процента, чтобы создать простые, но мощные фильтры.

### <a name="like-operator-examples"></a>ПРИМЕРЫ ОПЕРАТОРОВ LIKE

#### <a name="example-1-range"></a>Пример 1: [ \<range> ]

Следующие команды запускают Блокнот, а затем выполняют поиск экземпляра класса Win32_Process, имя которого начинается с буквы в диапазоне от "H" до "N" (без учета регистра).

Запрос должен возвращать любой процесс из Hotpad.exe с помощью Notepad.exe.

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a>Пример 2: [ \<range> ] и%

Следующие команды выбирают все процессы, имена которых начинаются с буквы между A и P (без учета регистра), за которым следует ноль или более букв в любом сочетании.

Командлет Get-WmiObject выполняет запрос, командлет Select-Object получает свойства Name и ProcessID, а командлет Sort-Object сортирует результаты в алфавитном порядке по имени.

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a>Пример 3. не в диапазоне (^)

Следующая команда получает процессы, имена которых не начинаются с одной из следующих букв: A, S, W, P, R, C, U, N

и с последующей длиной не более букв.

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a>Пример 4. любые символы--или None (%)

Следующие команды получают процессы, имена которых начинаются с "Calc".
Символ% в WQL эквивалентен символу звездочки ( \* ) в регулярных выражениях.

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a>Пример 5. один символ (_)

Следующие команды получают процессы, имена которых имеют следующий шаблон: "c_lc.exe", где символ подчеркивания представляет любой символ. Этот шаблон соответствует любому имени из calc.exe с помощью czlc.exe или c9lc.exe, но не соответствует именам, в которых символы "c" и "l" разделены более чем одним символом.

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a>Пример 6. точное совпадение

Следующие команды получают процессы с именем WLIDSVC.exe. Несмотря на то, что запрос использует ключевое слово LIKE, он требует точного соответствия, так как значение не содержит подстановочных знаков.

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a>ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА OR

Чтобы указать несколько независимых условий, используйте ключевое слово или. Ключевое слово или присутствует в предложении WHERE. Он выполняет включающую операцию или для двух (или более) условий и возвращает элементы, соответствующие любому из условий.

Оператор или имеет следующий формат:

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

Например, следующие команды получают все экземпляры класса WMI Win32_Process, но возвращают их только в том случае, если имя процесса имеет значение winword.exe или excel.exe.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

Оператор или можно использовать с более чем двумя условиями. В следующем запросе инструкция или возвращает Winword.exe, Excel.exe или Powershell.exe.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a>ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА AND

Чтобы указать несколько связанных условий, используйте ключевое слово и. Ключевое слово и отображается в предложении WHERE. Он возвращает элементы, соответствующие всем условиям.

Оператор and имеет следующий формат:

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

Например, следующие команды получают процессы с именем "Winword.exe" и ИДЕНТИФИКАТОРом процесса 6512.

Обратите внимание, что команды используют командлет Get-CimInstance.

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

Все операторы, включая операторы LIKE, допустимы с операторами OR и. Кроме того, можно сочетать операторы OR и и в одном запросе с круглыми скобками, которые указывают Windows PowerShell, какие предложения должны обрабатываться первыми.

Эта команда использует символ продолжения Windows PowerShell ('), разделите команду на две строки.

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a>ПОИСК ЗНАЧЕНИЙ NULL

Поиск значений NULL в WMI является сложной задачей, так как это может привести к непредсказуемым результатам. Значение NULL не равно нулю и не является эквивалентным или пустой строкой. Некоторые свойства класса WMI инициализированы, а другие — нет, поэтому поиск значений NULL может не работать для всех свойств.

Чтобы найти значения NULL, используйте оператор is со значением NULL.

Например, следующие команды получают процессы, имеющие значение NULL для свойства Инталлдате. Команды возвращают множество процессов.

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

В отличие от этого, следующая команда возвращает учетные записи пользователей, имеющие значение NULL для свойства Description. Эта команда не возвращает никаких учетных записей пользователей, хотя большинство учетных записей пользователей не имеют значения для свойства Description.

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

Чтобы найти учетные записи пользователей, не имеющие значения для свойства Description, используйте оператор равенства, чтобы получить пустую строку. Чтобы представить пустую строку, используйте две последовательные одинарные кавычки.

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a>ИСПОЛЬЗОВАНИЕ TRUE ИЛИ FALSE

Для получения логических значений в свойствах объектов WMI используйте значения true и false.
Для них регистр не учитывается.

Следующий WQL-запрос возвращает только локальные учетные записи пользователей с компьютера, присоединенного к домену.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

Чтобы найти учетные записи домена, используйте значение false, как показано в следующем примере.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a>ИСПОЛЬЗОВАНИЕ ESCAPE-СИМВОЛА

WQL использует обратную косую черту ( \) в качестве escape-символа). Это отличается от Windows PowerShell, в котором используется символ обратной кавычки (').

Кавычки и символы, используемые в кавычках, часто требуют экранирования, чтобы они не были правильно интерпретированы.

Чтобы найти пользователя, имя которого содержит одинарные кавычки, используйте обратную косую черту для экранирования одиночных кавычек, как показано в следующей команде.

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

В некоторых случаях обратная косая черта также должна быть экранирована. Например, следующие команды создают недопустимую ошибку запроса из-за обратной косой черты в значении заголовка.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

Чтобы экранировать обратную косую черту, используйте второй символ обратной косой черты, как показано в следующей команде.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Special_Characters](about_Special_Characters.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_WMI](about_WMI.md)

[about_WMI_Cmdlets](about_WMI_Cmdlets.md)
