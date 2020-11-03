---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229797"
---
# Restart-Computer

## Краткий обзор
Перезапускает операционную систему на локальных и удаленных компьютерах.

## SYNTAX

### Default (по умолчанию)

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### асжобсет

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Restart-Computer`Командлет перезапускает операционную систему на локальном и удаленном компьютерах.

Параметры можно использовать `Restart-Computer` для запуска операций перезапуска в качестве фонового задания, для указания уровней проверки подлинности и альтернативных учетных данных, для ограничения операций, выполняемых одновременно, и для принудительной перезагрузки.

Начиная с Windows PowerShell 3,0, перед выполнением следующей команды можно дождаться завершения перезапуска. Укажите время ожидания и интервал запроса, а также дождитесь доступности определенных служб на перезагруженном компьютере. Эта функция делает ее практичной для использования `Restart-Computer` в скриптах и функциях.

Для перезагрузки компьютера можно использовать протокол WS-Management (WSMan). в случае блокировки вызовов DCOM блокируются, например, брандмауэром предприятия. Дополнительные сведения см. в разделе [протокол WS-Management](/windows/desktop/WinRM/ws-management-protocol).

Этому командлету удаленное взаимодействие Windows PowerShell необходимо только при использовании параметра **AsJob**.

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

### Пример 3. перезапуск компьютеров в качестве фонового задания

Эти команды выполняют `Restart-Computer` команду в качестве фонового задания на двух удаленных компьютерах, а затем получают результаты.

Поскольку функция **AsJob** создает задание на локальном компьютере и автоматически возвращает результаты на локальный компьютер, можно выполнить `Receive-Job` локальную команду.

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

`Restart-Computer` использует параметр **ComputerName** для указания **Server01** и **Server02**. Параметр **AsJob** выполняет команду в качестве фонового задания. Объект задания хранится в `$Job` переменной. `$Job` отправляется по конвейеру в `Receive-Job` командлет, который получает результаты.

### Пример 4. перезапуск удаленного компьютера

`Restart-Computer` перезапускает удаленный компьютер с настроенными параметрами олицетворения и проверки подлинности.

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Restart-Computer` использует параметр **ComputerName** для указания **Server01**. Параметр **олицетворения** указывает Anonymous, чтобы скрыть удостоверение инициатора запроса. Параметр **дкомаусентикатион** указывает паккетинтегрити в качестве уровня проверки подлинности соединения.

### Пример 5. принудительный перезапуск компьютеров, перечисленных в текстовом файле

В этом примере выполняется принудительная перезагрузка компьютеров, перечисленных в `Domain01.txt` файле. Имена компьютеров из текстового файла хранятся в переменной. Параметр **Force** принудительно вызывает немедленный перезапуск, а параметр **ThrottleLimit** ограничивает количество одновременных подключений.

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

`Get-Content` использует параметр **path** для получения списка имен компьютеров из текстового файла **Domain01.txt**. Имена компьютеров хранятся в переменной `$Names` . `Get-Credential` запрашивает имя пользователя и пароль и сохраняет значения в переменной `$Creds` . `Restart-Computer` использует параметры **ComputerName** и **Credential** с их переменными. Параметр **Force** приводит к немедленному перезапуску каждого компьютера. Параметр **ThrottleLimit** ограничивает команду до 10 одновременных подключений.

### Пример 6. перезапуск удаленного компьютера и ожидание PowerShell

`Restart-Computer` перезапускает удаленный компьютер, после чего ждет до 5 минут (300 секунд), чтобы PowerShell был доступен на перезагруженном компьютере, прежде чем продолжить.

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` использует параметр **ComputerName** для указания **Server01**. Параметр **Wait** ожидает завершения перезапуска. **Для** указывает, что PowerShell может выполнять команды на удаленном компьютере. Параметр **timeout** задает время ожидания в пять минут. Параметр **delay** запрашивает удаленный компьютер каждые две секунды, чтобы определить, перезапущен ли он.

### Пример 7. перезагрузка компьютера с помощью протокола WSMan

`Restart-Computer` перезапускает удаленный компьютер с помощью протокола WSMan, а не по умолчанию, DCOM. Проверка подлинности Kerberos определяет, имеет ли текущий пользователь разрешение на перезапуск удаленного компьютера.

Эти параметры предназначены для предприятий, в которых перезапуски на основе DCOM завершаются сбоем из-за блокировки DCOM. Например, брандмауэром.

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

`Restart-Computer` использует параметр **ComputerName** для указания удаленного компьютера **Server01**.
Параметр **протокола** задает использование протокола WSMan. Параметр **всманаусентикатион** указывает метод проверки подлинности **Kerberos**.

## PARAMETERS

### -AsJob

Указывает, что `Restart-Computer` выполняется как фоновое задание.

Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие. В Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** . Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер. Чтобы управлять заданием, используйте командлеты **Job**. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

Указывает уровень проверки подлинности, используемый для WMI-соединения. `Restart-Computer` использует WMI.

Допустимые значения:

- **Вызов** : проверка подлинности COM на уровне вызова
- **Подключение** : проверка подлинности COM на уровне подключения
- **По умолчанию** : проверка подлинности Windows
- **Нет** : нет проверки подлинности COM
- **Пакет** : проверка подлинности COM на уровне пакетов.
- **Паккетинтегрити** : проверка подлинности COM на уровне целостности пакетов
- **Паккетприваци** : проверка подлинности COM уровня конфиденциальности пакета.
- **Без изменений** : уровень проверки подлинности совпадает с предыдущей командой.

Дополнительные сведения см. в разделе [перечисление аусентикатионлевел](/dotnet/api/system.management.authenticationlevel).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
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
Parameter Sets: DefaultSet
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

- **По умолчанию** : ожидает перезапуска PowerShell.
- **PowerShell** : может выполнять команды в удаленном сеансе PowerShell на компьютере.
- **WMI** : получает ответ на запрос Win32_ComputerSystem компьютера.
- **WinRM** : может установить удаленный сеанс для компьютера с помощью WS-Management.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
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

### — Олицетворение

Задает уровень олицетворения, используемый этим командлетом для вызова WMI. `Restart-Computer` использует WMI.
Допустимые значения для этого параметра:

- **По умолчанию** : олицетворение по умолчанию. Несмотря на имя, это не значение по умолчанию.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Указывает, какой протокол следует использовать для перезагрузки компьютеров. Допустимые значения: **WSMan** и **DCOM**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

Если параметр **ThrottleLimit** не указан или используется значение 0, `Restart-Computer` использует не более 32 одновременных подключений.

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

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
Parameter Sets: DefaultSet
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
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя. Этот параметр впервые появился в Windows PowerShell 3.0.

Допустимые значения для этого параметра: " **базовый** ", " **CredSSP** ", " **по умолчанию** ", " **дайджест** ", **Kerberos** и " **согласование** ".

Дополнительные сведения см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.String
Parameter Sets: DefaultSet
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

В Windows PowerShell 2.0 параметр **ComputerName** принимает входные данные из конвейера только по имени свойства. В Windows PowerShell 3,0 и более поздних версиях параметр **ComputerName** принимает входные данные из конвейера по значению.

## Выходные данные

### Нет, System. Management. Automation. Ремотингжоб

Если указан параметр **AsJob** , `Restart-Computer` возвращает объект задания. В противном случае никаких выходных данных не создается.

## ПРИМЕЧАНИЯ

- `Restart-Computer` работает только на компьютерах под управлением Windows и требует от WinRM и инструментария WMI для завершения работы системы, включая локальную систему.
- `Restart-Computer` использует [метод Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) класса [WIN32_OPERATINGSYSTEM](/windows/desktop/CIMWin32Prov/win32-operatingsystem) инструментарий управления Windows (WMI) (WMI).  Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .

В Windows PowerShell 2,0 параметр **AsJob** не работает надежно при перезапуске или остановке удаленных компьютеров. В Windows PowerShell 3.0 реализация была изменена, чтобы устранить эту проблему.

## Связанные ссылки

[О служба удаленного управления Windows](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Протокол WS-Management](/windows/desktop/WinRM/ws-management-protocol)
