---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 541059691e794591e85a8321a4507ed8838bcb4a
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "93230229"
---
# Update-Help

## Краткий обзор
Скачивает и устанавливает новейшие файлы справки на компьютер.

## SYNTAX

### Путь (по умолчанию)

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LiteralPath

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Update-Help`Командлет загружает новейшие файлы справки для модулей PowerShell и устанавливает их на компьютер. Не нужно перезапускать PowerShell, чтобы изменения были эффективны. `Get-Help`Для немедленного просмотра новых файлов справки можно использовать командлет.

`Update-Help` проверяет версию файлов справки на компьютере. Если у вас нет файлов справки для модуля или файлы справки устарели, `Update-Help` загружает новейшие файлы справки. Файлы справки можно скачать и установить из Интернета или общей папки.

Без параметров `Update-Help` обновляет файлы справки для модулей в сеансе и для всех установленных модулей, поддерживающих обновляемую справку. Включены модули, которые установлены, но не загружены в текущем сеансе. Модули PowerShell хранятся в расположении, указанном в `$env:PSModulePath` переменной среды. Дополнительные сведения см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).

Параметр **module** можно использовать для обновления файлов справки для определенного модуля. Используйте параметр **UICulture** для скачивания файлов справки на нескольких языках и языковых стандартах.

Также можно использовать `Update-Help` на компьютерах, которые не подключены к Интернету. Сначала используйте `Save-Help` командлет для загрузки файлов справки из Интернета и сохраните их в общей папке, доступной системе, не подключенной к Интернету. Затем используйте параметр **SourcePath** функции, `Update-Help` чтобы скачать обновленные файлы справки из общего доступа и установить их на компьютере.

Вы можете автоматизировать обновление справки, добавив `Update-Help` командлет в свой профиль PowerShell. По умолчанию `Update-Help` выполняется только один раз в день на каждом компьютере. Чтобы переопределить ограничение одного раза в день, используйте параметр **Force** .

`Update-Help`Командлет появился в Windows PowerShell 3,0.

> [!IMPORTANT]
> `Update-Help` требуются права администратора в PowerShell 6,0 и ниже.
> В PowerShell 6,1 и выше для **области** по умолчанию задано значение `CurrentUser` .
> До выхода версии PowerShell 6,1 параметр **Scope** был недоступен.
>
> Для обновления файлов справки для модулей PowerShell Core необходимо быть членом группы администраторов на компьютере.
>
> Чтобы скачать или обновить файлы справки для модулей в каталоге установки PowerShell ( `$PSHOME\Modules` ), включая модули PowerShell Core, запустите PowerShell с помощью команды **Запуск от имени администратора** .
> Например: `Start-Process pwsh.exe -Verb RunAs`.

## Примеры

### Пример 1. обновление файлов справки для всех модулей

`Update-Help`Командлет обновляет файлы справки для установленных модулей, поддерживающих обновляемую справку. Язык и региональные параметры пользовательского интерфейса задаются в операционной системе.

```powershell
Update-Help
```

### Пример 2. обновление файлов справки для указанных модулей

`Update-Help`Командлет обновляет файлы справки только для имен модулей, начинающихся с **Microsoft. PowerShell** .

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### Пример 3. обновление файлов справки для разных языков

`Update-Help`Командлет обновляет файлы справки на японском языке (ja-JP) и английском (EN-US) для всех модулей.

Если модуль не предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса, выводится сообщение об ошибке для модуля и языка и региональных параметров пользовательского интерфейса. В этом примере сообщение об ошибке указывает на то, что файлы справки **ja-JP** не найдены для модуля **Microsoft. PowerShell. Utility** .

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### Пример 4. обновление файлов справки на нескольких компьютерах из общей папки

В этом примере обновленные файлы справки загружаются из Интернета и сохраняются в общей папке. Требуются учетные данные пользователя, имеющие разрешения на доступ к общей папке и установку обновлений. При использовании общей папки можно обновить компьютеры, находящиеся за брандмауэрами или не подключенные к Интернету.

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

`Save-Help`Команда скачивает самые новые файлы справки для всех модулей, поддерживающих обновляемую справку.
Параметр **DestinationPath** сохраняет файлы в `\\Server01\Share\PSHelp` общей папке. Параметр **Credential** указывает пользователя, имеющего разрешение на доступ к общей папке.

`Invoke-Command`Командлет запускает удаленные `Update-Help` команды на нескольких компьютерах. Параметр **ComputerName** возвращает список удаленных компьютеров из файла **Servers.txt** . Параметр **ScriptBlock** выполняет `Update-Help` команду и использует параметр **SourcePath** для указания общего файлового ресурса, содержащего обновленные файлы справки. Параметр **Credential** указывает пользователя, который имеет доступ к общей папке и выполняет удаленную `Update-Help` команду.

### Пример 5. Получение списка обновленных файлов справки

`Update-Help`Командлет обновляет справку для указанного модуля. Командлет использует параметр **verbose** Common для вывода списка обновленных файлов справки. Для просмотра выходных данных для всех файлов справки и файлов справки для конкретного модуля можно использовать параметр **verbose** .

Без параметра **verbose** `Update-Help` не отображает результаты выполнения команды. Вывод **подробных** параметров полезен для проверки обновления файлов справки или установки последней версии.

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### Пример 6. Поиск модулей, поддерживающих обновляемую справку

В этом примере перечислены модули, поддерживающие обновляемую справку. Команда использует свойство **HelpInfoUri** модуля для выявления модулей, поддерживающих обновляемую справку. Свойство **HelpInfoUri** содержит адрес, который перенаправляется при `Update-Help` выполнении командлета.

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### Пример 7. обновление файлов справки инвентаризации

В этом примере сценарий `Get-UpdateHelpVersion.ps1` создает инвентаризацию обновляемых файлов справки для каждого модуля и их номеров версий.

Скрипт определяет модули, поддерживающие обновляемую справку, с помощью свойства **HelpInfoUri** модулей. Для модулей, поддерживающих обновляемую справку, сценарий ищет и анализирует файл справочной информации (* helpinfo.xml), чтобы найти номер последней версии.

Для создания пользовательского выходного объекта скрипт использует класс **PSCustomObject** и хэш-таблицу.

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## PARAMETERS

### -Credential

Указывает учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **SourcePath** . Этот параметр допустим, только если в команде используется параметр **SourcePath** или **LiteralPath** .

Параметр **Credential** позволяет выполнять `Update-Help` команды с параметром **SourcePath** на удаленных компьютерах. Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.

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
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, размер которых превышает ограничение в 1 ГБ.

Без этого параметра `Update-Help` выполняется только один раз в 24-часовом периоде. Размер загружаемых файлов ограничен 1 ГБ несжатого содержимого на модуль, а файлы справки устанавливаются только в том случае, если они новее, чем существующие файлы на компьютере.

Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление `Update-Help` команды в профиль PowerShell без затрат на ресурсы при повторяющихся подключениях или загрузках.

Чтобы обновить справку для модуля на нескольких языках и в региональных параметрах пользовательского интерфейса без параметра **Force** , включите все языки и региональные параметры пользовательского интерфейса в одну команду, например:

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### -FullyQualifiedModule

Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .
Эти модули описаны в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в формате:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

or

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.

Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .

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

Указывает папку для обновленных файлов справки, а не скачивает их из Интернета. Используйте этот параметр или **SourcePath** , если вы использовали `Save-Help` командлет для загрузки файлов справки в каталог.

Вы можете выполнить конвейер объекта каталога, например из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .

В отличие от значения **SourcePath** , значение **LiteralPath** используется точно так же, как типизировано. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Module

Обновляет справку для указанных модулей. Введите одно или несколько имен модулей или шаблонов имен в списке с разделителями-запятыми или укажите файл, в котором перечислены имена отдельных модулей в каждой строке. Можно использовать подстановочные знаки. Вы можете конвейерировать модули из `Get-Module` командлета в `Update-Help` командлет.

Указанные модули должны быть установлены на компьютере, но их не нужно импортировать в текущий сеанс. Можно указать любой модуль в сеансе или любой модуль, установленный в расположении, указанном в `$env:PSModulePath` переменной среды.

Значение `*` (все) пытается обновить справку для всех модулей, установленных на компьютере.
Включены модули, которые не поддерживают обновляемую справку. Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку. Вместо этого запустите `Update-Help` без параметров.

Параметр **module** `Update-Help` командлета не принимает полный путь к файлу модуля или файлу манифеста модуля. Чтобы обновить справку для модуля, который не находится в `$env:PSModulePath` расположении, импортируйте модуль в текущий сеанс перед выполнением `Update-Help` команды.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Recurse

Выполняет рекурсивный поиск файлов справки в указанном каталоге. Этот параметр допустим только в том случае, если в команде используется параметр **SourcePath** .

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

### -Scope

Указывает область системы, в которой обновляется Справка. Для обновлений в области **ALLUSERS** требуются права администратора в системах Windows. `-Scope`Параметр был представлен в PowerShell Core версии 6,1.

**CurrentUser** — это область по умолчанию для файлов справки в PowerShell 6,1 и более поздних версиях. Можно указать **ALLUSERS** для установки или обновления справки для всех пользователей. В системах UNIX `sudo` требуются права на обновление справки для всех пользователей. Пример: `sudo pwsh -c Update-Help`

Допустимые значения:

- CurrentUser
- AllUsers

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePath

Указывает папку файловой системы `Update-Help` , в которой будут обновляться файлы справки, а не загружать их из Интернета. Введите путь к папке. Не указывайте имя файла или расширение имени файла. Вы можете конвейерировать папку, такую как, из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .

По умолчанию `Update-Help` скачивает обновленные файлы справки из Интернета. Используйте параметр **SourcePath** , если вы использовали `Save-Help` командлет для загрузки обновленных файлов справки в каталог.

Чтобы указать значение **SourcePath** по умолчанию, перейдите в раздел **Групповая политика** , **Конфигурация компьютера** и **Задайте путь к источнику по умолчанию для Update-Help** . Этот параметр групповая политика запрещает пользователям использовать `Update-Help` для загрузки файлов справки из Интернета.
Дополнительные сведения см. в статье [О параметрах групповой политики](./About/about_Group_Policy_Settings.md).

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Задает значения языка и региональных параметров пользовательского интерфейса, которые `Update-Help` используются для получения обновленных файлов справки. Введите один или несколько кодов языка, например **es-ES** , переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, такие как `Get-Culture` `Get-UICulture` команда или. Подстановочные знаки не допускаются, и нельзя отправлять код частичного языка, например **de** .

По умолчанию `Update-Help` получает файлы справки в языке и региональных параметрах пользовательского интерфейса, заданных для операционной системы. Если указан параметр **UICulture** , `Update-Help` ищет справку только для указанного языка и региональных параметров пользовательского интерфейса.

> [!NOTE]
> Ubuntu 18,04 изменила параметр языкового стандарта по умолчанию на `C.UTF.8` , который не является распознаваемым языком пользовательского интерфейса. `Update-Help` автоматически не удается загрузить справку, если вы не используете этот параметр с поддерживаемым языковым стандартом, например `en-US` . Это может произойти на любой платформе, которая использует неподдерживаемое значение.

Команды, которые используют параметр **UICulture** , выполняются, только если модуль предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса. Если команда завершается ошибкой из-за того, что указанная культура пользовательского интерфейса не поддерживается, выводится сообщение об ошибке.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

Указывает, что `Update-Help` выполняет команду, включая загрузку из Интернета, используя учетные данные текущего пользователя. По умолчанию команда выполняется без явных учетных данных.

Этот параметр эффективен, только если веб-скачивание использует проверку подлинности NT LAN Manager (NTLM), согласование или аутентификацию на основе Kerberos.

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

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.IO.DirectoryInfo

Путь к каталогу можно передать по конвейеру `Update-Help` .

### System.Management.Automation.PSModuleInfo

Объект модуля можно передать из `Get-Module` командлета в `Update-Help` .

## Выходные данные

### Нет

`Update-Help` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Чтобы обновить справку для модулей PowerShell Core, содержащих команды, установленные с помощью PowerShell, или любой модуль в `$PSHOME\Modules` каталоге, запустите PowerShell с параметром для **запуска от имени администратора** .

Только члены группы администраторов на компьютере могут обновлять справку по модулям PowerShell Core, командам, которые устанавливаются вместе с PowerShell и для модулей в `$PSHOME\Modules` папке. Если у вас нет разрешения на обновление файлов справки, можно прочитать файлы справки в Интернете. Например, `Get-Help Update-Help -Online`.

Модули — это наименьшая единица обновляемой справки. Невозможно обновить справку для конкретного командлета. Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** `Get-Command` командлета, например `(Get-Command Update-Help).ModuleName` .

Поскольку файлы справки устанавливаются в каталог Module, `Update-Help` командлет может установить обновленный файл справки только для модулей, установленных на компьютере. Однако `Save-Help` командлет может сохранить справку для модулей, которые не установлены на компьютере.

Если `Update-Help` не удается найти обновленные файлы справки для модуля или не удается найти обновленную справку на указанном языке, она продолжится без вывода сообщения об ошибке. Чтобы увидеть состояние и сведения о ходе выполнения, используйте параметр **Verbose** .

`Update-Help`Командлет появился в Windows PowerShell 3,0. Он не работает в более ранних версиях PowerShell. На компьютерах, где установлены Windows PowerShell 2,0 и Windows PowerShell 3,0, используйте `Update-Help` командлет в сеансе Windows powershell 3,0 для скачивания и обновления файлов справки. Файлы справки доступны как для Windows PowerShell 2,0, так и для Windows PowerShell 3,0.

`Update-Help` `Save-Help` Командлеты и используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.

`Update-Help` поддерживает все модули и оснастки PowerShell Core. Другие оснастки не поддерживаются.

Чтобы обновить справку для модуля в расположении, не указанном в `$env:PSModulePath` переменной среды, импортируйте модуль в текущий сеанс, а затем выполните `Update-Help` команду. Выполните команду `Update-Help` без параметров или укажите имя модуля с помощью параметра **module** . Параметр **module** `Update-Help` `Save-Help` командлетов и не принимает полный путь к файлу модуля или файлу манифеста модуля.

Любой модуль может поддерживать обновляемую справку. Инструкции по поддержке обновляемой справки в созданных вами модулях см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).

`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).

## Связанные ссылки

[Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Get-UICulture](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[Start-Job](Start-Job.md)

[Save-Help](Save-Help.md)
