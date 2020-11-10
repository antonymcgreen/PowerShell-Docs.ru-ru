---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 88d36c7e919e11be7b8c1568bd28f6badb789539
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391329"
---
# Save-Help

## Краткий обзор
Скачивает и сохраняет последние файлы справки в каталог файловой системы.

## SYNTAX

### Путь (по умолчанию)

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### LiteralPath

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## DESCRIPTION

`Save-Help`Командлет загружает новейшие файлы справки для модулей PowerShell и сохраняет их в указанном каталоге. Эта функция позволяет обновлять файлы справки на компьютерах без доступа к Интернету и упрощает обновление файлов справки на нескольких компьютерах.

В Windows PowerShell 3,0 `Save-Help` работает только для модулей, установленных на локальном компьютере. Хотя можно импортировать модуль с удаленного компьютера или получить ссылку на объект **PSModuleInfo** с удаленного компьютера с помощью удаленного взаимодействия PowerShell, свойство **HelpInfoUri** не было сохранено и `Save-Help` не будет работать в справке по удаленному модулю.

В Windows PowerShell 4,0 свойство **HelpInfoUri** сохраняется через удаленное взаимодействие PowerShell, что позволяет `Save-Help` работать с модулями, установленными на удаленных компьютерах. Можно также сохранить объект **PSModuleInfo** на диске или съемном носителе, запустив `Export-Clixml` на компьютере, который не подключен к Интернету, импортировать объект на компьютере, который имеет доступ к Интернету, а затем запустить `Save-Help` на объекте **PSModuleInfo** . Сохраненная Справка может быть перенесена на удаленный компьютер с помощью съемных носителей, таких как USB-накопитель. Справку можно установить на удаленном компьютере, выполнив команду `Update-Help` . Этот процесс можно использовать для установки справки на компьютерах без доступа к какой-либо сети.

Чтобы установить сохраненные файлы справки, выполните `Update-Help` командлет. Добавьте его параметр **SourcePath** , чтобы указать папку, в которой были сохранены файлы справки.

Без параметров `Save-Help` команда загружает новейшую справку для всех модулей в сеансе и для модулей, установленных на компьютере, в расположении, указанном в переменной среды **PSModulePath** . Это действие пропускает модули, которые не поддерживают обновляемую справку без предупреждения.

`Save-Help`Командлет проверяет версию всех файлов справки в папке назначения. Если доступны новые файлы справки, этот командлет скачивает новейшие файлы справки из Интернета, а затем сохраняет их в папке. `Save-Help`Командлет работает так же, как и `Update-Help` командлет, за исключением того, что он сохраняет загруженные CAB-файлы, а не извлекает файлы справки из этих CAB-файлов и не устанавливает их на компьютер.

Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса. Нет необходимости извлекать файлы справки из CAB-файла. `Update-Help`Командлет извлекает файлы справки, проверяет XML для обеспечения безопасности, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.

Чтобы сохранить файлы справки для модулей в папке установки PowerShell ( `$pshome\Modules` ), запустите PowerShell с помощью команды Запуск от имени администратора. Для загрузки файлов справки для этих модулей необходимо быть членом группы администраторов на компьютере.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Сохранение справки для модуля DhcpServer

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module,
# save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

В этом примере показаны три разных способа `Save-Help` сохранения справки для модуля **DhcpServer** с клиентского компьютера, подключенного к Интернету, без установки модуля **DhcpServer** или роли DHCP-сервера на локальном компьютере.

### Пример 2. Установка справки для модуля DhcpServer

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the
# PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer
# module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and
# then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

В этом примере показано, как установить справку, сохраненную в примере 1 для модуля **DhcpServer** на компьютере без доступа к Интернету.

### Пример 3. Сохранение справки для всех модулей

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

Эта команда загружает последние файлы справки для всех модулей для языка Windows на локальном компьютере. Файлы справки сохраняются в `\\Server01\Fileshare01` папке.

### Пример 4. Сохранение справки для модуля на компьютере

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

Эта команда скачивает новейшие файлы справки для модуля **ServerManager** , а затем сохраняет их в `\\Server01\Fileshare01` папке.

Если модуль установлен на компьютере, можно ввести имя модуля в параметре **Module** , даже если модуль не импортируется в текущий сеанс.

Команда использует параметр **Credential** , чтобы передать учетные данные пользователя с разрешением на запись в общую папку.

### Пример 5. Сохранение справки для модуля на другом компьютере

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

Эти команды загружают самые новые файлы справки для модуля **кустомскл** и сохраняют их в `\\Server01\Fileshare01` папке.

Так как модуль **кустомскл** не установлен на компьютере, последовательность включает `Invoke-Command` команду, которая получает объект модуля для модуля Кустомскл с компьютера Server02, а затем передает объект модуля в `Save-Help` командлет.

Если модуль не установлен на компьютере, `Save-Help` требуется объект модуля, который содержит сведения о расположении самых новых файлов справки.

### Пример 6. Сохранение справки для модуля на нескольких языках

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

Эта команда сохраняет справку для модулей PowerShell Core в четырех различных культурах пользовательского интерфейса. Языковые пакеты для этих языков не должны устанавливаться на компьютере.

`Save-Help` может скачивать файлы справки для модулей в различных культурах пользовательского интерфейса только в том случае, если владелец модуля делает переведенные файлы доступными в Интернете.

### Пример 7. Сохранение справки более одного раза в день

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

Эта команда сохраняет справку для всех модулей, которые установлены на компьютере. Команда задает параметр **Force** для переопределения правила, которое не позволяет `Save-Help` командлету загружать справку более одного раза в течение каждого 24-часового периода.

Параметр **Force** также переопределяет ограничение 1 ГБ и обходит проверку версии.
Таким образом, можно загружать файлы, даже если версия не превышает версию в папке назначения.

Команда использует `Save-Help` командлет для загрузки и сохранения файлов справки в указанной папке.
Параметр **Force** необходим, если необходимо выполнять `Save-Help` команду более одного раза каждый день.

## PARAMETERS

### -Credential

Указывает учетные данные пользователя. Этот командлет выполняет команду, используя учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **DestinationPath** . Этот параметр доступен, только если в команде используется параметр **DestinationPath** или **LiteralPath**.

Этот параметр позволяет выполнять `Save-Help` команды, использующие параметр **DestinationPath** на удаленных компьютерах. Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath

Указывает путь к папке, в которой сохраняются файлы справки. Не указывайте имя или расширение файла.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, превышающие ограничение в 1 ГБ.

Без этого параметра `Save-Help` для каждого модуля допускается только одна команда в течение 24 часов, Загрузка ограничена 1 ГБ несжатого содержимого на модуль, а файлы справки для модуля устанавливаются только в том случае, если они новее, чем файлы на компьютере.

Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление `Save-Help` команды в профиль PowerShell.

Чтобы сохранить справку для модуля в нескольких культурах пользовательского интерфейса без параметра **Force** , включите все языки и региональные параметры пользовательского интерфейса в той же команде, например: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### -FullyQualifiedModule

Указывает модули с именами, указанными в форме объектов **ModuleSpecification** . См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет. Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** . два параметра являются взаимоисключающими.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к папке назначения. В отличие от значения параметра **DestinationPath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module

Указывает модули, для которых этот командлет скачивает справку. Введите одно или несколько имен модулей или имя шаблонов в списке с разделителями-запятыми или в файле с одним именем модуля в каждой строке. Можно использовать подстановочные знаки. Также можно передать объекты модуля из `Get-Module` командлета в `Save-Help` .

По умолчанию `Save-Help` загружает справку для всех модулей, поддерживающих обновляемую справку и установленных на локальном компьютере в расположении, указанном в переменной среды **PSModulePath** .

Чтобы сохранить справку для модулей, которые не установлены на компьютере, выполните `Get-Module` команду на удаленном компьютере. Затем передавайте полученные объекты модуля в `Save-Help` командлет или отправьте объекты модуля в качестве значения параметров **модуля** или **InputObject** .

Если указанный модуль установлен на компьютере, можно ввести имя модуля или объект модуля. Если модуль не установлен на компьютере, необходимо ввести объект модуля, например один из них, возвращаемый `Get-Module` командлетом.

Параметр **module** `Save-Help` командлета не принимает полный путь к файлу модуля или файлу манифеста модуля. Чтобы сохранить справку для модуля, который не находится в **PSModulePath** расположении, импортируйте модуль в текущий сеанс перед выполнением `Save-Help` команды.

Значение "*" (все) пытается обновить справку для всех модулей, установленных на компьютере.
Сюда входят модули, которые не поддерживают обновляемую справку. Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку.

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UICulture

Задает значения языка и региональных параметров пользовательского интерфейса, для которых этот командлет получает обновленные файлы справки. Введите один или несколько кодов языка, например `es-ES` , переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, такие как `Get-Culture` `Get-UICulture` команда или.

Подстановочные знаки не допускаются. Не указывайте код частичного языка, например "de".

По умолчанию `Save-Help` получает файлы справки в языке и региональных параметрах пользовательского интерфейса для Windows или его резервного языка и региональных параметров.
Если указан параметр **UICulture** , `Save-Help` ищет справку только для указанной культуры пользовательского интерфейса, а не для резервной культуры.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

Указывает, что этот командлет выполняет команду, включая загрузку в Интернете, с учетными данными текущего пользователя. По умолчанию команда выполняется без явных учетных данных.

Этот параметр действует, только если веб-загрузка использует проверку подлинности NTLM, проверку подлинности с согласованием или проверку подлинности Kerberos.

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

### -Scope

Этот не делает ничего в этом командлете.

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSModuleInfo

Объект модуля можно передать из `Get-Module` командлета в параметр **модуля** `Save-Help` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- Чтобы сохранить справку по модулям в папке $pshome \Модулес, запустите PowerShell с помощью команды Запуск от имени администратора. Только члены группы "Администраторы" на компьютере могут загружать справку по модулям в папке $pshome \Модулес.
- Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса. Нет необходимости извлекать файлы справки из CAB-файла. `Update-Help`Командлет извлекает файлы справки, проверяет XML, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.
- `Save-Help`Командлет может сохранить справку для модулей, которые не установлены на компьютере. Однако, поскольку файлы справки устанавливаются в папку Module, `Update-Help` командлет может установить обновленный файл справки только для модулей, установленных на компьютере.
- Если `Save-Help` не удается найти обновленные файлы справки для модуля или не удается найти обновленные файлы справки на указанном языке, он продолжится без вывода сообщения об ошибке. Чтобы узнать, какие файлы были сохранены с помощью команды, укажите параметр **verbose** .
- Модули — это наименьшая единица обновляемой справки. Невозможно сохранить справку для конкретного командлета только для всех командлетов в модуле. Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** вместе с `Get-Command` командлетом, например `(Get-Command \<cmdlet-name\>).ModuleName`
- `Save-Help` поддерживает все модули и оснастки PowerShell Core. Она не поддерживает никакие другие оснастки.
- `Update-Help` `Save-Help` Командлеты и используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.
- `Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).

## Связанные ссылки

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Update-Help](Update-Help.md)
