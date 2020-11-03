---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 6b22e8d4f843d0611083c253027222f4d4cd7282
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228369"
---
# Get-Process

## Краткий обзор
Получает процессы, запущенные на локальном или удаленном компьютере.

## SYNTAX

### Имя (по умолчанию)

```
Get-Process [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### намевисусернаме

```
Get-Process [[-Name] <String[]>] [-IncludeUserName] [<CommonParameters>]
```

### идвисусернаме

```
Get-Process -Id <Int32[]> [-IncludeUserName] [<CommonParameters>]
```

### Идентификатор

```
Get-Process -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### инпутобжектвисусернаме

```
Get-Process -InputObject <Process[]> [-IncludeUserName] [<CommonParameters>]
```

### InputObject

```
Get-Process -InputObject <Process[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

## DESCRIPTION

`Get-Process`Командлет получает процессы на локальном или удаленном компьютере.

Без параметров этот командлет получает все процессы на локальном компьютере.
Можно также указать конкретный процесс по имени или ИДЕНТИФИКАТОРу процесса (PID) или передать объект процесса через конвейер в этот командлет.

По умолчанию этот командлет возвращает объект Process с подробными сведениями о процессе и поддерживает методы, позволяющие запускать и прекращать процесс.
Можно также использовать параметры `Get-Process` командлета, чтобы получить сведения о версии файла для программы, выполняемой в процессе, и получить модули, загруженные процессом.

## Примеры

### Пример 1. Получение списка всех активных процессов на локальном компьютере

```powershell
Get-Process
```

Эта команда возвращает список всех активных процессов, запущенных на локальном компьютере.
Определение каждого столбца см. в разделе [Примечания](#notes) .

### Пример 2. получение всех доступных данных о одном или нескольких процессах

```powershell
Get-Process winword, explorer | Format-List *
```

Эта команда возвращает все доступные данные о процессах Winword и проводника на компьютере.
В нем используется параметр **Name** для указания процессов, но в нем опущено необязательное имя параметра.
Оператор конвейера `|` передает данные в `Format-List` командлет, который отображает все доступные свойства `*` объектов Process Winword и проводника.

Процессы также можно определить по идентификаторам (PID).
Например, `Get-Process -Id 664, 2060` .

### Пример 3. получение всех процессов с рабочим набором, превышающим указанный размер

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

Эта команда возвращает все процессы, размер рабочего набора которых превышает 20 МБ.
Он использует `Get-Process`  командлет для получения всех запущенных процессов.
Оператор конвейера `|` передает объекты процесса в `Where-Object` командлет, который выбирает только объект со значением, превышающим 20 000 000 байт для свойства " **рабочее** множество".

**Рабочее** множество — это одно из многих свойств объектов Process.
Чтобы просмотреть все свойства, введите `Get-Process | Get-Member` .
По умолчанию значения всех свойств объема указываются в байтах, несмотря на то что по умолчанию отображаются они отображаются в килобайтах и мегабайтах.

### Пример 4. Вывод списка процессов на компьютере в группах на основе приоритета

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

Эти команды выводит список процессов на компьютере в группах в зависимости от их класса приоритета.
Первая команда получает все процессы на компьютере, а затем сохраняет их в `$A` переменной.

Вторая команда передает объект **процесса** , хранящийся в `$A` переменной `Get-Process` , в командлет, а затем — в `Format-Table` командлет, который форматирует процессы с помощью представления **Priority** .

Представление **приоритетов** и другие представления определяются в файлах форматирования ps1xml в домашнем каталоге PowerShell ( `$pshome` ).

### Пример 5. Добавление свойства к отображению стандартного Get-Process вывода

```powershell
Get-Process powershell -ComputerName S1, localhost | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 S1          powershell
     6 23500 31348   142 2.75   4016 S1          powershell
    27 54572 54520   576 5.52   4428 localhost   powershell
```

В этом примере извлекаются процессы с локального компьютера и с удаленного компьютера (S1).
Полученные процессы передаются `Format-Table` команде, которая добавляет свойство **MachineName** к стандартному `Get-Process` отображению выходных данных.

### Пример 6. Получение сведений о версии для процесса

```
Get-Process powershell -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.6713.1       6.1.6713.1 (f... C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe
```

Эта команда использует параметр **FileVersionInfo** для получения сведений о версии файла powershell.exe, который является основным модулем для процесса PowerShell.

Чтобы выполнить эту команду с процессами, которые не являются владельцами в Windows Vista и более поздних версиях Windows, необходимо открыть PowerShell с параметром Запуск от имени администратора.

### Пример 7. Загрузка модулей, загруженных с указанным процессом

```powershell
Get-Process SQL* -Module
```

Эта команда использует параметр **module** для получения модулей, загруженных процессом.
Эта команда возвращает модули для процессов, имена которых начинаются с SQL.

Чтобы выполнить эту команду в Windows Vista и более поздних версиях Windows с несобственными процессами, необходимо запустить PowerShell с параметром Запуск от имени администратора.

### Пример 8. Поиск владельца процесса

```powershell
PS C:\> Get-Process powershell -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     powershell
```

```powershell
$p = Get-WmiObject Win32_Process -Filter "name='powershell.exe'"
$p.GetOwner()
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 3
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Domain           : DOMAIN01
ReturnValue      : 0
User             : user01
```

Первая команда показывает, как найти владельца процесса.
Для параметра **IncludeUserName** требуются повышенные права пользователя (Запуск от имени администратора).
Результат показывает, что владелец — Domain01\user01.

Вторая и третья команды — еще один способ найти владельца процесса.

Вторая команда использует `Get-WmiObject` для получения процесса PowerShell.
Он сохраняется в переменной $p.

Третья команда использует метод, чтобы получить владельца процесса в $p.
Результат показывает, что владелец — Domain01\user01.

### Пример 9. Использование автоматической переменной для обнаружения процесса, в котором размещен текущий сеанс

```powershell
Get-Process powershell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
308      26        52308      61780   567     3.18   5632 powershell
377      26        62676      63384   575     3.88   5888 powershell
```

```powershell
Get-Process -Id $PID
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
396      26        56488      57236   575     3.90   5888 powershell
```

Эти команды показывают, как использовать `$PID` автоматическую переменную для указания процесса, в котором размещается текущий сеанс PowerShell.
Этот метод можно использовать, чтобы отличить ведущий процесс от других процессов PowerShell, которые может потребоваться приостанавливаться или закрыть.

Первая команда получает все процессы PowerShell в текущем сеансе.

Вторая команда получает процесс PowerShell, в котором размещается текущий сеанс.

### Пример 10. получение всех процессов, имеющих заголовок главного окна, и их отображение в таблице

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

Эта команда возвращает все процессы с заголовком главного окна и отображает их в таблице, где также указаны идентификатор и имя процесса.

Свойство **маинвиндовтитле** — это лишь одно из многих полезных свойств объекта **Process** , который `Get-Process` возвращает.
Чтобы просмотреть все свойства, передайте результаты выполнения `Get-Process` команды в `Get-Member` командлет `Get-Process | Get-Member` .

## PARAMETERS

### -ComputerName

Указывает компьютеры, для которых этот командлет получает активные процессы.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) одного или нескольких компьютеров.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр **ComputerName** этого командлета можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: Name, Id, InputObject
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileVersionInfo

Указывает, что этот командлет получает сведения о версии файла для программы, которая выполняется в процессе.

В Windows Vista и более поздних версиях Windows необходимо открыть PowerShell с параметром Запуск от имени администратора, чтобы использовать этот параметр для процессов, которыми вы не владеете.

Параметры **FileVersionInfo** и **ComputerName** `Get-Process` командлета нельзя использовать в одной команде.

Чтобы получить сведения о версии файла для процесса на удаленном компьютере, используйте `Invoke-Command` командлет.

Использование этого параметра эквивалентно получению свойства **маинмодуле. FileVersionInfo** каждого объекта процесса.
При использовании этого параметра `Get-Process` возвращает объект **FileVersionInfo** **System. Diagnostics. FileVersionInfo** , а не объект процесса.
Таким образом, нельзя передать выходные данные команды в командлет, который предполагает объект процесса, например `Stop-Process` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает один или несколько процессов по идентификатору процесса (PID).
При указании нескольких идентификаторов разделяйте их запятыми.
Чтобы найти идентификатор процесса, введите `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: IdWithUserName, Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeUserName

Указывает, что значение UserName объекта **процесса** возвращается с результатами выполнения команды.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает один или несколько объектов процесса.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObjectWithUserName, InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Module

Указывает, что этот командлет получает модули, загруженные процессами.

В Windows Vista и более поздних версиях Windows необходимо открыть PowerShell с параметром Запуск от имени администратора, чтобы использовать этот параметр для процессов, которыми вы не владеете.

Чтобы получить модули, загруженные процессом на удаленном компьютере, используйте `Invoke-Command` командлет.

Этот параметр эквивалентен получению свойства **modules** каждого объекта процесса.
При использовании этого параметра командлет возвращает объект **ProcessModule** **. Diagnostics. ProcessModule** , а не объект процесса.
Таким образом, нельзя передать выходные данные команды в командлет, который предполагает объект процесса, например `Stop-Process` .

При одновременном использовании параметров *module* и **FileVersionInfo** в одной команде этот командлет возвращает объект **FileVersionInfo** со сведениями о версии файла всех модулей.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает один или несколько процессов по имени процесса.
Можно ввести несколько имен процессов (разделенных запятыми) и использовать подстановочные знаки.
Имя параметра (Name) указывать необязательно.

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Diagnostics.Process

Объект процесса можно передать в этот командлет по конвейеру.

## Выходные данные

### System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule

По умолчанию этот командлет возвращает объект **System. Diagnostics. Process** .
При использовании параметра **FileVersionInfo** возвращается объект **System. Diagnostics. FileVersionInfo** .
Если вы используете параметр **module** без параметра **FileVersionInfo** , он возвращает объект **System. Diagnostics. ProcessModule** .

## ПРИМЕЧАНИЯ

- Вы также можете ссылаться на этот командлет по его встроенным псевдонимам, PS и GPS. Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- На компьютерах, работающих под управлением 64-разрядной версии Windows, 64-разрядная версия PowerShell получает только 64-разрядные модули процесса, а в 32-разрядной версии PowerShell — только модули с 32-битным процессом.
- Вы можете использовать свойства и методы Win32_Process объекта инструментарий управления Windows (WMI) (WMI) в PowerShell. Дополнительные сведения см `Get-WmiObject` . в разделе и пакете SDK для инструментария WMI.
- По умолчанию процесс отображается как таблица, которая содержит следующие столбцы. Описание всех свойств объектов Process см. в разделе [Свойства процесса](/dotnet/api/system.diagnostics.process) в библиотеке MSDN.
  - Handles: количество дескрипторов, открытых процессом.
  - NPM (K): объем нестраничной памяти, используемой процессом, в килобайтах.
  - PM (K): объем выгружаемой памяти, используемой процессом, в килобайтах.
  - WS (K): размер рабочего набора процесса в килобайтах.
    Рабочий набор состоит из страниц памяти, на которые недавно ссылался процесс.
  - VM (M): объем виртуальной памяти, используемой процессом, в мегабайтах.
    Виртуальная память используется для хранения файлов подкачки на диске.
  - ЦП: количество процессорного времени, которое процесс использовал во всех процессорах (в секундах).
  - ID: идентификатор процесса (PID) процесса.
  - ProcessName: имя процесса.
    Описание понятий, связанных с процессами, см. в центре справки и поддержки, а также в справке диспетчера задач.
- Вы также можете использовать встроенные альтернативные представления процессов `Format-Table` , таких как **StartTime** и **Priority** , а также создавать собственные представления.

## Связанные ссылки

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
