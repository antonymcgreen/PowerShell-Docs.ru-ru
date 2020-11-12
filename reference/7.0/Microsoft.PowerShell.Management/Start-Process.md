---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 8967f68e23a7b5447ce32f698bfe0cf1c44b9c9e
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524713"
---
# Start-Process

## Краткий обзор
Запускает один или несколько процессов на локальном компьютере.

## SYNTAX

### Default (по умолчанию)

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UseShellExecute

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Start-Process`Командлет запускает один или несколько процессов на локальном компьютере. По умолчанию `Start-Process` создает новый процесс, который наследует все переменные среды, определенные в текущем процессе.

Чтобы указать программу, выполняемую в процессе, введите исполняемый файл или файл скрипта, либо файл, который может быть открыт с помощью имеющейся на компьютере программы. Если указан неисполняемый файл, `Start-Process` программа запускает программу, связанную с файлом, аналогично `Invoke-Item` командлету.

Параметры можно использовать `Start-Process` для указания параметров, таких как загрузка профиля пользователя, запуск процесса в новом окне или использование альтернативных учетных данных.

## Примеры

### Пример 1. Запуск процесса, использующего значения по умолчанию

В этом примере запускается процесс, который использует `Sort.exe` файл в текущей папке. Команда использует все значения по умолчанию, включая стиль окна по умолчанию, рабочую папку и учетные данные.

```powershell
Start-Process -FilePath "sort.exe"
```

### Пример 2. Печать текстового файла

В этом примере запускается процесс, который выводит `C:\PS-Test\MyFile.txt` файл.

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### Пример 3. Запуск процесса для сортировки элементов в новый файл

В этом примере запускается процесс, который сортирует элементы в `Testsort.txt` файле и возвращает отсортированные элементы в `Sorted.txt` файлах. Все ошибки записываются в `SortError.txt` файл.

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

Параметр **усеневенвиронмент** указывает, что процесс выполняется с собственными переменными среды.

### Пример 4. Запуск процесса в развернутом окне

В этом примере запускается `Notepad.exe` процесс. Окно разворачивается во весь экран и удерживается до завершения процесса.

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### Пример 5. Запуск PowerShell от имени администратора

В этом примере запускается PowerShell с помощью команды **Запуск от имени администратора** .

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### Пример 6. Использование различных команд для запуска процесса

В этом примере показано, как найти команды, которые можно использовать при запуске процесса. Доступные команды определяются расширением имени файла, который выполняется в процессе.

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

В примере используется `New-Object` для создания объекта **System. Diagnostics. ProcessStartInfo** для **PowerShell.exe** — файла, который выполняется в процессе PowerShell. Свойство **Verbs** объекта **ProcessStartInfo** показывает, что можно использовать команды **Open** и **runas** с `PowerShell.exe` или с любым процессом, запускающим `.exe` файл.

### Пример 7. Указание аргументов для процесса

Обе команды запускают интерпретатор команд Windows, выполняя `dir` команду в `Program Files` папке. Поскольку это переключка содержит пробел, значение должно заключаться в экранированные кавычки.
Обратите внимание, что первая команда указывает строку как **ArgumentList**. Вторая команда является массивом строк.

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### Пример 8. Создание отсоединенного процесса в Linux

В Windows `Start-Process` создает независимый процесс, который остается запущенным независимо от запуска оболочки. На платформах, отличных от Windows, вновь запущенный процесс прикрепляется к запущенной оболочке. Если закрывается Запуск оболочки, дочерний процесс завершается.

Во избежание завершения дочернего процесса на платформах, подобных Unix, можно сочетать `Start-Process` с `nohup` . В следующем примере запускается фоновый экземпляр PowerShell в Linux, который остается активным даже после закрытия сеанса запуска. `nohup`Команда собирает выходные данные в файле `nohup.out` в текущем каталоге.

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

В этом примере `Start-Process` выполняет `nohup` команду Linux, которая запускается `pwsh` как отсоединенный процесс. Дополнительные сведения см. на справочной странице [нохуп](https://linux.die.net/man/1/nohup).

## PARAMETERS

### -ArgumentList

Указывает параметры или значения параметров, которые следует использовать при запуске этого командлета. Аргументы можно принимать как одну строку с аргументами, разделенными пробелами, или как массив строк, разделенных запятыми.

Если параметры или значения параметров содержат пробел, их необходимо заключить в escape-символы, заключенные в двойные кавычки. Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию командлет использует учетные данные текущего пользователя.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает необязательный путь и имя файла программы, выполняемой в процессе. Введите имя исполняемого файла или документа, например `.txt` `.doc` файла или, связанного с программой на компьютере. Этот параметр обязателен.

Если указано только имя файла, используйте параметр **WorkingDirectory** , чтобы указать путь.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadUserProfile

Указывает, что этот командлет загружает профиль пользователя Windows, хранящийся в разделе `HKEY_USERS` реестра для текущего пользователя. Параметр не применяется для систем, отличных от Windows.

Этот параметр не влияет на профили PowerShell. Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoNewWindow

Предотвращает запуск процесса в новом окне. По умолчанию в Windows PowerShell открывает новое окно. В системах, отличных от Windows, новое окно терминала никогда не появляется.

Использовать параметры **NoNewWindow** и **WindowStyle** в одной и той же команде нельзя.

Параметр не применяется для систем, отличных от Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект процесса для каждого запущенного командлетом процесса По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardError

Указывает файл. Этот командлет отправляет все ошибки, созданные процессом, в указанный файл.
Введите путь и имя файла. По умолчанию все ошибки отображаются в консоли.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardInput

Указывает файл. Этот командлет считывает входные данные из указанного файла. Введите путь и имя входного файла. По умолчанию процесс получает входные данные с клавиатуры.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardOutput

Указывает файл. Этот командлет отправляет выходные данные, созданные процессом, в указанный вами файл.
Введите путь и имя файла. По умолчанию выходные данные отображаются в консоли.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNewEnvironment

Указывает, что этот командлет использует новые переменные среды, заданные для процесса. По умолчанию запущенный процесс выполняется с переменными среды, унаследованными от родительского процесса.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verb

Задает команду, используемую при запуске этого командлета. Доступные команды определяются расширением имени файла, который выполняется в процессе.

В приведенной ниже таблице показаны команды, доступные для некоторых распространенных типов файлов.

| Тип файла |                Команды                |
| --------- | ----------------------------------- |
| .cmd      | Правка, открытие, печать, Запуск от имени, выполняющийся |
| EXE      | Open, RunAs, RunAsUser              |
| .txt      | Открытие, печать, Принтто                |
| .wav      | Открыть, воспроизвести                          |

Чтобы найти команды, которые можно использовать с файлом, выполняемым в процессе, используйте `New-Object` командлет, чтобы создать объект **System. Diagnostics. ProcessStartInfo** для файла. Доступные команды находятся в свойстве **Verbs** объекта **ProcessStartInfo** . Дополнительные сведения см. в примерах.

Параметр не применяется для систем, отличных от Windows.

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Указывает, что этот командлет ожидает завершения указанного процесса и его потомков, прежде чем принимать дополнительные входные данные. Этот параметр подавляет командную строку или оставляет окно до завершения процессов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowStyle

Определяет состояние окна для нового процесса. Допустимые значения для этого параметра: **нормальный** , **скрытый** , **сведенный** и **развернутый**. Значение по умолчанию — **Обычная**.

Использовать параметры **WindowStyle** и **NoNewWindow** в одной и той же команде нельзя.

Параметр не применяется для систем, отличных от Windows.

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkingDirectory

Указывает расположение, в котором должен начинаться новый процесс. По умолчанию это расположение исполняемого файла или документа, который запускается. Подстановочные знаки не поддерживаются. Имя пути не должно содержать символы, интерпретируемые как подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет, System. Диагностика. Process

Этот командлет создает объект **System. Diagnostics. Process** , если указан параметр **PassThru** . В противном случае командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

- Этот командлет реализуется с помощью метода **Start** класса **System. Diagnostics. Process** . Дополнительные сведения об этом методе см. в разделе [метод Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).

- В Windows при использовании **усеневенвиронмент** новый процесс запускается только с переменными среды по умолчанию, определенными для области **компьютера** . Это влияет на то, что параметр `$env:USERNAME` имеет значение **System**. Ни одна из переменных из **пользовательской** области не включена.

- В Windows наиболее распространенным вариантом использования `Start-Process` является использование параметра **Wait** для блокировки хода выполнения до завершения нового процесса. В системе, отличной от Windows, это редко требуется, так как поведение по умолчанию для приложений командной строки эквивалентно `Start-Process -Wait` .

- При использовании `Start-Process` в системах, отличных от Windows, новое окно терминала никогда не появляется.

## Связанные ссылки

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Service](Start-Service.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
