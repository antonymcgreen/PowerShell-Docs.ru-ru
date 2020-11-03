---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229793"
---
# Stop-Computer

## Краткий обзор
Останавливает (завершает работу) локальный и удаленные компьютеры.

## SYNTAX

### Все

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Stop-Computer`Командлет завершает работу локального компьютера и удаленных компьютеров.

Параметры можно использовать `Stop-Computer` для запуска операций завершения работы в качестве фоновых заданий, для указания уровней проверки подлинности и альтернативных учетных данных, чтобы ограничить количество параллельных подключений, создаваемых для выполнения команды, и принудительно выполнить немедленное завершение работы.

Этот командлет не требует удаленного взаимодействия PowerShell, если не используется параметр **AsJob** .

## Примеры

### Пример 1. Завершение работы локального компьютера

В этом примере завершается работа локального компьютера.

```powershell
Stop-Computer -ComputerName localhost
```

### Пример 2. Завершение работы двух удаленных компьютеров и локального компьютера

В этом примере останавливаются два удаленных компьютера и локальный компьютер.

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

`Stop-Computer` использует параметр **ComputerName** для указания двух удаленных компьютеров и локального компьютера. Работа каждого компьютера завершена.

### Пример 3. Завершение работы удаленных компьютеров в качестве фоновых заданий

В этом примере `Stop-Computer` выполняется как фоновое задание на двух удаленных компьютерах.

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

`Stop-Computer` использует параметр **ComputerName** для задания двух удаленных компьютеров. Параметр **AsJob** выполняет команду в качестве фонового задания. Объекты задания хранятся в `$j` переменной.

Объекты задания в `$j` переменной отправляются по конвейеру в `Receive-Job` , который получает результаты задания. Объекты хранятся в `$results` переменной. `$results`Переменная отображает сведения о задании в консоли PowerShell.

Поскольку функция **AsJob** создает задание на локальном компьютере и автоматически возвращает результаты на локальный компьютер, можно выполнить `Receive-Job` локальную команду.

### Пример 4. Завершение работы удаленного компьютера

В этом примере завершается работа удаленного компьютера с использованием указанной проверки подлинности.

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Stop-Computer` Задает удаленный компьютер с помощью параметра **ComputerName** . Параметр **олицетворения** задает настраиваемое олицетворение, а параметр **дкомаусентикатион** задает параметры уровня проверки подлинности.

### Пример 5. Завершение работы компьютеров в домене

В этом примере команды вынуждены немедленно завершить работу всех компьютеров в указанном домене.

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

`Get-Content` использует параметр **path** для получения файла в текущем каталоге со списком компьютеров домена. Объекты хранятся в `$s` переменной.

`Get-Credential` использует параметр **Credential** для указания учетных данных администратора домена. Учетные данные хранятся в `$c` переменной.

`Stop-Computer` завершает работу компьютеров, указанных в списке компьютеров с параметром **ComputerName** , в `$s` переменной. Параметр **Force** принудительно вызывает немедленное завершение работы. Параметр **ThrottleLimit** ограничивает команду до 10 одновременных подключений. Параметр **Credential** передает учетные данные, сохраненные в `$c` переменной.

## PARAMETERS

### -AsJob

Указывает, что этот командлет выполняется как фоновое задание.

Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие, а в Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** . Дополнительные сведения см. в разделе [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).

При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) и [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).

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

### -ComputerName

Указывает компьютеры для отмены. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми. Чтобы указать локальный компьютер, введите имя компьютера или localhost.

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на это действие. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Дкомаусентикатион

Указывает уровень проверки подлинности, используемый этим командлетом с WMI. `Stop-Computer` использует WMI. По умолчанию используется значение **Packet**.

Допустимые значения для этого параметра:

- **По умолчанию** : проверка подлинности Windows.
- **Нет** : проверка подлинности COM отсутствует.
- **Подключение** : проверка подлинности COM на уровне подключения.
- **Вызов** : проверка подлинности COM на уровне вызова.
- **Пакет** : проверка подлинности COM на уровне пакетов.
- **Паккетинтегрити** : проверка подлинности COM на уровне целостности пакетов.
- **Паккетприваци** : проверка подлинности COM уровня конфиденциальности пакета.
- **Без изменений** : то же, что и Предыдущая команда.

Дополнительные сведения о значениях этого параметра см. в разделе [аусентикатионлевел](/dotnet/api/system.management.authenticationlevel).

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Принудительно выполняет немедленное завершение работы компьютера.

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

### — Олицетворение

Задает уровень олицетворения, используемый при вызове WMI этим командлетом. Значение по умолчанию — **impersonate**.

`Stop-Computer` использует WMI. Допустимые значения для этого параметра:

- **По умолчанию** : олицетворение по умолчанию.
- **Anonymous** : скрывает удостоверение вызывающей стороны.
- **Identify** : позволяет объектам запрашивать учетные данные вызывающей стороны.
- **Impersonate** : позволяет объектам использовать учетные данные вызывающей стороны.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Указывает, какой протокол следует использовать для перезагрузки компьютеров. Допустимые значения для этого параметра: **WSMan** и **DCOM**. Значение по умолчанию — **DCOM**.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan. Значение по умолчанию ― **Default**.

Допустимые значения для этого параметра:

- Базовый
- CredSSP
- По умолчанию
- Digest (дайджест)
- Kerberos
- Negotiate —

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
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

### Нет

Вы не можете передать входные данные в этот командлет.

## Выходные данные

### None или System. Management. Automation. Ремотингжоб

Командлет возвращает объект **System. Management. Automation. ремотингжоб** , если указан параметр **AsJob** . В противном случае он не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет использует метод **Win32Shutdown** класса WMI **Win32_OperatingSystem** . Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .

## Связанные ссылки

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Test-Connection](Test-Connection.md)
