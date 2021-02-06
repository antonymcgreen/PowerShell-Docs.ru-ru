---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: f6d31980e27b73e884b46168606ab8255a64efb9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600462"
---
# Stop-Computer

## Краткий обзор
Останавливает (завершает работу) локальный и удаленные компьютеры.

## SYNTAX

### Все

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Stop-Computer`Командлет завершает работу локального компьютера и удаленных компьютеров.

С помощью параметров можно `Stop-Computer` указать уровни проверки подлинности и альтернативные учетные данные, а также принудительно выполнить немедленное завершение работы.

В PowerShell 7,1 `Stop-Computer` был добавлен для Linux и macOS. Параметры не влияют на эти платформы. Командлет просто вызывает машинную команду `/sbin/shutdown` .

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

Оператор Background `&` выполняет `Stop-Computer` команду как фоновое задание. Дополнительные сведения см. в разделе [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

`Stop-Computer` использует параметр **ComputerName** для задания двух удаленных компьютеров. `&`Оператор Background выполняет команду как фоновое задание. Объекты задания хранятся в `$j` переменной.

Объекты задания в `$j` переменной отправляются по конвейеру в `Receive-Job` , который получает результаты задания. Объекты хранятся в `$results` переменной. `$results`Переменная отображает сведения о задании в консоли PowerShell.

### Пример 4. Завершение работы удаленного компьютера

В этом примере завершается работа удаленного компьютера с использованием указанной проверки подлинности.

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

`Stop-Computer` Задает удаленный компьютер с помощью параметра **ComputerName** . Параметр **всманаусентикатион** указывает, что для установления удаленного подключения используется протокол Kerberos.

### Пример 5. Завершение работы компьютеров в домене

В этом примере команды вынуждены немедленно завершить работу всех компьютеров в указанном домене.

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

`Get-Content` использует параметр **path** для получения файла в текущем каталоге со списком компьютеров домена. Объекты хранятся в `$s` переменной.

`Get-Credential` использует параметр **Credential** для указания учетных данных администратора домена. Учетные данные хранятся в `$c` переменной.

`Stop-Computer` завершает работу компьютеров, указанных в списке компьютеров с параметром **ComputerName** , в `$s` переменной. Параметр **Force** принудительно вызывает немедленное завершение работы. Параметр **Credential** передает учетные данные, сохраненные в `$c` переменной.

## PARAMETERS

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

Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

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

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan. Значение по умолчанию ― **Default**.

Допустимые значения для этого параметра:

- Basic
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

### None

Вы не можете передать входные данные в этот командлет.

## Выходные данные

### None

## ПРИМЕЧАНИЯ

Этот командлет использует метод **Win32Shutdown** класса WMI **Win32_OperatingSystem** . Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .

В PowerShell 7,1 `Stop-Computer` был добавлен для Linux и macOS. Для этих платформ командлет вызывает собственную команду `/sbin/shutdown` .

## Связанные ссылки

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Test-Connection](Test-Connection.md)

