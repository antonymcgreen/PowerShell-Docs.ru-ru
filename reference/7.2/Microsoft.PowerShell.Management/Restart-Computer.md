---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 0e6df859a19f2281cc835b725fbc52c232042e56
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604035"
---
# Restart-Computer

## Краткий обзор
Перезапускает операционную систему на локальных и удаленных компьютерах.

## SYNTAX

### Default (по умолчанию)

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Restart-Computer`Командлет перезапускает операционную систему на локальном и удаленном компьютерах.

Параметры можно использовать `Restart-Computer` для запуска операций перезапуска, для указания уровней проверки подлинности и альтернативных учетных данных, для ограничения операций, выполняемых одновременно, и для принудительной перезагрузки.

Начиная с Windows PowerShell 3,0, перед выполнением следующей команды можно дождаться завершения перезапуска. Укажите время ожидания и интервал запроса, а также дождитесь доступности определенных служб на перезагруженном компьютере. Эта функция делает ее практичной для использования `Restart-Computer` в скриптах и функциях.

## Примеры

### Пример 1. перезапуск локального компьютера

`Restart-Computer` перезапускает локальный компьютер.

```powershell
Restart-Computer
```

### Пример 2. перезапуск нескольких компьютеров

`Restart-Computer` может перезапустить удаленный и локальный компьютеры. Параметр **ComputerName** принимает массив имен компьютеров.

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### Пример 3. Получение имен компьютеров из текстового файла

`Restart-Computer` Возвращает список имен компьютеров из текстового файла и перезапускает компьютеры. Параметр **ComputerName** не указан. Но поскольку это первый параметр размещения, он принимает имена компьютеров из текстового файла, которые отправляются по конвейеру.

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**. Имена компьютеров отправляются по конвейеру. `Restart-Computer` перезапускает каждый компьютер.

### Пример 4. принудительный перезапуск компьютеров, перечисленных в текстовом файле

В этом примере выполняется принудительная перезагрузка компьютеров, перечисленных в `Domain01.txt` файле. Имена компьютеров из текстового файла хранятся в переменной. Параметр **Force** принудительно вызывает немедленную перезагрузку.

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**. Имена компьютеров хранятся в переменной `$Names` . `Get-Credential` запрашивает имя пользователя и пароль и сохраняет значения в переменной `$Creds` . `Restart-Computer` использует параметры **ComputerName** и **Credential** с их переменными. Параметр **Force** приводит к немедленному перезапуску каждого компьютера.

### Пример 6. перезапуск удаленного компьютера и ожидание PowerShell

`Restart-Computer` перезапускает удаленный компьютер, после чего ждет до 5 минут (300 секунд), чтобы PowerShell был доступен на перезагруженном компьютере, прежде чем продолжить.

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` использует параметр **ComputerName** для указания **Server01**. Параметр **Wait** ожидает завершения перезапуска. **Для** указывает, что PowerShell может выполнять команды на удаленном компьютере. Параметр **timeout** задает время ожидания в пять минут. Параметр **delay** запрашивает удаленный компьютер каждые две секунды, чтобы определить, перезапущен ли он.

### Пример 7. перезагрузка компьютера с помощью Всманаусентикатион

`Restart-Computer` перезапускает удаленный компьютер с помощью механизма **всманаусентикатион** .
Проверка подлинности Kerberos определяет, имеет ли текущий пользователь разрешение на перезапуск удаленного компьютера. Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

`Restart-Computer` использует параметр **ComputerName** для указания удаленного компьютера **Server01**.
Параметр **всманаусентикатион** указывает метод проверки подлинности **Kerberos**.

## PARAMETERS

### -ComputerName

Указывает одно имя компьютера или разделенный запятыми массив имен компьютеров. `Restart-Computer` принимает объекты **ComputerName** из конвейера или переменных.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера. Чтобы указать локальный компьютер, введите имя компьютера, точку `.` или localhost.

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

Если параметр **ComputerName** не указан, `Restart-Computer` перезапускает локальный компьютер.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Delay

Указывает частоту запросов в секундах. PowerShell запрашивает службу, указанную **параметром, чтобы** определить, доступна ли служба после перезагрузки компьютера.

Этот параметр допустим только вместе с параметрами **ожидания** и **для** параметров.

Этот параметр впервые появился в Windows PowerShell 3.0.

Если параметр **delay** не указан, `Restart-Computer` использует 5-секундную задержку.

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Для

Задает поведение PowerShell при ожидании доступности указанной службы или компонента после перезагрузки компьютера. Этот параметр допустим только с параметром **Wait** .

Допустимые значения для этого параметра:

- **По умолчанию**: ожидает перезапуска PowerShell.
- **PowerShell**: может выполнять команды в удаленном сеансе PowerShell на компьютере.
- **WMI**: получает ответ на запрос Win32_ComputerSystem компьютера.
- **WinRM**: может установить удаленный сеанс для компьютера с помощью WS-Management.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Вызывает немедленную перезагрузку компьютера.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout

Указывает время ожидания в секундах. По истечении времени ожидания `Restart-Computer` возвращает в командную строку, даже если компьютеры не перезапускаются.

Параметр **timeout** допустим только с параметром **Wait** . **Время ожидания** переопределяет неопределенный период ожидания в параметре **ожидания** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

`Restart-Computer` подавляет командную строку PowerShell и блокирует конвейер до перезапуска компьютеров. Этот параметр можно использовать в скрипте для перезагрузки компьютеров и продолжения обработки после завершения перезагрузки.

Параметр **Wait** ожидает неограниченное время ожидания перезапуска компьютеров. Можно использовать **время ожидания** для настройки времени, а параметры **для** и **задержки** ожидают, когда определенные службы станут доступны на перезагруженных компьютерах.

Параметр **Wait** недопустим при перезапуске локального компьютера. Если значение параметра **ComputerName** содержит имена удаленных компьютеров и локального компьютера, `Restart-Computer` создает неустранимую ошибку для **ожидания** на локальном компьютере, но ожидает перезапуска удаленных компьютеров.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя. Этот параметр впервые появился в Windows PowerShell 3.0.

Допустимые значения для этого параметра: " **базовый**", " **CredSSP**", " **по умолчанию**", " **дайджест**", **Kerberos** и " **согласование**".

Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед запуском `Restart-Computer` .

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

Показывает, что произойдет при `Restart-Computer` выполнении. `Restart-Computer`Командлет не выполняется.

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

### System.String

`Restart-Computer` принимает имена компьютеров из конвейера или переменных.

## Выходные данные

### None

`Restart-Computer` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

- В Windows `Restart-Computer` использует [метод Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) класса [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) инструментарий управления Windows (WMI) (WMI). Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .
- В Linux и Mac OS `Restart-Computer` использует `/sbin/shutdown` средство bash.

## Связанные ссылки

[О служба удаленного управления Windows](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Протокол WS-Management](/windows/desktop/WinRM/ws-management-protocol)
