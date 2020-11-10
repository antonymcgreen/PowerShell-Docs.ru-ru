---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388354"
---
# Add-Computer

## Краткий обзор
Добавляет локальный компьютер в домен или рабочую группу.

## SYNTAX

### Домен (по умолчанию)

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Рабочая группа

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Add-Computer`Командлет добавляет локальный или удаленный компьютер в домен или рабочую группу или перемещает их из одного домена в другой. Он также создает учетную запись домена при добавлении компьютера в домен без учетной записи.

Параметры этого командлета можно использовать для указания контроллера домена и подразделения или выполнения незащищенного присоединения.

Чтобы получить результаты выполнения команды, используйте параметры **Verbose** и **PassThru**.

## Примеры

### Пример 1. Добавление локального компьютера в домен и перезагрузка компьютера

```powershell
Add-Computer -DomainName Domain01 -Restart
```

Эта команда добавляет локальный компьютер в домен Domain01, а затем перезагружает компьютер, чтобы изменения вступили в силу.

### Пример 2. Добавление локального компьютера в рабочую группу

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

Эта команда добавляет локальный компьютер в рабочую группу Workgroup-A.

### Пример 3. Добавление локального компьютера в домен

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

Эта команда добавляет локальный компьютер в домен Domain01, используя контроллер домена Domain01\DC01.

Команда использует параметры **PassThru** и **Verbose** для получения подробных сведений о результатах выполнения команды.

### Пример 4. Добавление локального компьютера в домен с помощью параметра Аупас

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

Эта команда добавляет локальный компьютер в домен Domain02.
Она использует параметр OUPath, чтобы указать подразделение для новых учетных записей.

### Пример 5. Добавление локального компьютера в домен с использованием учетных данных

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

Эта команда добавляет компьютер Server01 в домен Domain02. Она использует параметр **LocalCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на подключение к компьютеру Server01. Она использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на присоединение компьютеров к домену. Она использует параметр **Restart** , чтобы перезагрузить компьютер после выполнения операции присоединения, и параметр **Force** для отключения запросов подтверждения пользователем.

### Пример 6. Перемещение группы компьютеров в новый домен

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

Эта команда перемещает компьютеры Server01 и Server02 и локальный компьютер из Domain01 в Domain02.

Она использует параметр **LocalCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на подключение к трем задействованным компьютерам. Она использует параметр **UnjoinDomainCredential** , чтобы указать учетную запись пользователя, имеющую разрешение на исключение компьютеров из домена Domain01, и параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на присоединение компьютеров к домену Domain02. Она использует параметр **Restart** для перезагрузки всех трех компьютеров после завершения перемещения.

### Пример 7. Перемещение компьютера в новый домен и изменение имени компьютера

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

Эта команда перемещает компьютер Server01 в домен Domain02 и изменяет имя компьютера на Server044.

Команда использует учетные данные текущего пользователя для подключения к компьютеру Server01 и исключению его из текущего домена. Параметр **Credential** используется для указания учетной записи пользователя, имеющей разрешение на присоединение компьютера к домену домен domain02.

### Пример 8. Добавление компьютеров, перечисленных в файле, в новый домен

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

Эта команда добавляет компьютеры, перечисленные в файле Servers.txt, в домен Domain02. Она использует параметр **Options** для указания параметра **Win9xUpgrade**. Параметр **Restart** перезапускает все добавленные компьютеры после выполнения операции присоединения.

### Пример 9. Добавление компьютера в домен с использованием стандартных учетных данных компьютера

Эта первая команда должна запускаться администратором с компьютера, который уже присоединен к домену `Domain03` .

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

Это сочетание команд создает новую учетную запись компьютера с предопределенным именем и временным паролем присоединения в домене, используя существующий компьютер, присоединенный к домену. Затем по отдельности компьютер с предопределенным именем присоединяется к домену, используя только имя компьютера и временный пароль присоединение.
Предопределенный пароль используется только для поддержки операции JOIN и заменяется как часть обычных процедур учетной записи компьютера после того, как компьютер завершает соединение.

## PARAMETERS

### -ComputerName

Указывает компьютеры для добавления в домен или рабочую группу.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя каждого удаленного компьютера. Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или localhost.

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell. Параметр **ComputerName** можно использовать, `Add-Computer` даже если компьютер не настроен для выполнения удаленных команд.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на присоединение компьютеров к новому домену.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя запрашивается пароль.

Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютера из текущего домена, используйте параметр **UnjoinDomainCredential**. Чтобы указать учетную запись, имеющую разрешение на подключение к удаленному компьютеру, используйте параметр **LocalCredential**.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

Указывает домен, в который добавляются компьютеры. Этот параметр является обязательным при добавлении компьютеров в домен.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Отключает запрос подтверждения пользователя. Без этого параметра `Add-Computer` требует подтверждения добавления каждого компьютера.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Локалкредентиал

Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютерам, указанным в параметре **ComputerName**. По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя запрашивается пароль.

Чтобы указать учетную запись пользователя, имеющую разрешение на добавление компьютеров в новый домен, используйте параметр **Credential**. Чтобы указать учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущего домена, используйте параметр **UnjoinDomainCredential**.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -NewName

Указывает новое имя для компьютера в новом домене. Этот параметр допустим только при добавлении или перемещении одного компьютера.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Параметры

Указывает дополнительные параметры для операции присоединение к **Add-Computer** . Введите одно или несколько значений в строку с разделителями запятыми.

Допустимые значения для этого параметра:

- **Аккаунткреате** : создает учетную запись домена. Командлет **Add-Computer** автоматически создает учетную запись домена при добавлении компьютера в домен. Этот параметр включен для полноты.

- **Win9XUpgrade** : указывает, что операция JOIN является частью обновления операционной системы Windows.

- **Унсекуреджоин** : Выполняет небезопасное соединение. Чтобы запросить небезопасное соединение, используйте параметр *незащищенный* или этот параметр. Если вы хотите передать пароль компьютера, этот параметр следует использовать в сочетании с `PasswordPass` параметром.

- **Пассвордпасс** : задает для пароля компьютера значение параметра *Credential* (домаинкредентиал) после выполнения небезопасного объединения. Этот параметр также указывает, что значение параметра *Credential* (DomainCredential) является паролем компьютера, а не пользователя. Этот параметр допустим только в том случае, если `UnsecuredJoin` указан параметр. При использовании этого параметра учетные данные, предоставленные для `-Credential` параметра, *должны* иметь значение NULL username.

- **Жоинвисневнаме** : переименовывает имя компьютера в новом домене на имя, заданное параметром *newname* . При использовании параметра *NewName* этот параметр задается автоматически. Этот параметр предназначен для использования с командлетом Rename-Computer. Если вы используете командлет **Rename-Computer** для переименования компьютера, но не перезапускайте компьютер для внесения изменений, можно использовать этот параметр, чтобы присоединить компьютер к домену с новым именем.

- **Жоинреадонли** : использует существующую учетную запись компьютера для приподключения компьютера к контроллеру домена только для чтения. Учетная запись компьютера должна быть добавлена в список разрешенных для политики репликации паролей, а пароль учетной записи должен быть реплицирован на контроллер домена только для чтения до выполнения операции JOIN.

- **Инсталлинвоке** : задает флаги Create (0x2) и Delete (0x4) параметра **фжоиноптионс** метода **жоиндомаинорворкграуп** . Дополнительные сведения о методе **жоиндомаинорворкграуп** см. в разделе [метод жоиндомаинорворкграуп класса Win32_ComputerSystem](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).
  Дополнительные сведения об этих параметрах см. в разделе [функция нетжоиндомаин](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аупас

Указывает подразделение для учетной записи домена. Введите полное различающееся имя подразделения в кавычках. Значение по умолчанию — подразделение по умолчанию для объектов компьютеров в домене.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете. По умолчанию этот командлет не создает выходные данные.

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

### -Restart

Перезапускает компьютеры, которые были добавлены в домен или рабочую группу. Чтобы изменения вступили в силу, часто требуется перезагрузка.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Server

Задает имя контроллера домена, который добавляет компьютер в домен. Введите имя в формате "ИмяДомена\ИмяКомпьютера". По умолчанию контроллер домена не указан.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Унжоиндомаинкредентиал

Указывает учетную запись пользователя, имеющую разрешение на удаление компьютеров из текущих доменов. По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя запрашивается пароль.

Используйте этот параметр при перемещении компьютеров в другой домен. Чтобы указать учетную запись, имеющую разрешение на присоединение к новому домену, используйте параметр **Credential**. Чтобы указать учетную запись, имеющую разрешение на подключение к удаленному компьютеру, используйте параметр **LocalCredential**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Небезопасный

Выполняет незащищенное присоединение к указанному домену.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkgroupName

Указывает имя рабочей группы, в которую добавляются компьютеры. Значение по умолчанию — WORKGROUP.

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

В командлет можно передать имена компьютеров и новые имена `Add-Computer` .

## Выходные данные

### Microsoft. PowerShell. Commands. Компутерчанжеинфо

При использовании параметра **PassThru** `Add-Computer` возвращает объект **компутерчанжеинфо** .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- В Windows PowerShell 2,0 параметр **сервера** `Add-Computer` завершается ошибкой даже при наличии сервера. В Windows PowerShell 3.0 реализация параметра **Server** изменилась. Теперь он работает надежно.

## Связанные ссылки

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
