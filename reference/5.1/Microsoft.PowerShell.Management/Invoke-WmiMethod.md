---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "93229661"
---
# Invoke-WmiMethod

## Краткий обзор
Вызывает методы WMI.

## SYNTAX

### Класс (по умолчанию)

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### объект

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### вклкуери

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-WmiMethod`Командлет вызывает методы объектов инструментарий управления Windows (WMI) (WMI).

Новые командлеты модель CIM (CIM), появившиеся в Windows PowerShell 3,0, выполняют те же задачи, что и командлеты WMI. Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту CIM, который позволяет командлетам использовать те же методы для управления компьютерами Windows и другими операционными системами. Вместо использования `Invoke-WmiMethod` рекомендуется использовать [командлет Invoke-Циммесод](../cimcmdlets/invoke-cimmethod.md).

## Примеры

### Пример 1. вывод необходимого порядка объектов WMI

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

Эта команда указывает нужный порядок объектов. Вызов WMI в PowerShell 3.0 отличается от других методов и требует, чтобы значения объекта вводились в определенном порядке.

### Пример 2. Запуск экземпляра приложения

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

Эта команда запускает экземпляр блокнота, вызывая `Create` метод класса **Win32_Process** .

Свойство **ReturnValue** заполняется значением 0, а свойство **ProcessID** заполняется ЦЕЛЫМ числом (идентификатором следующего процесса), если команда выполнена.

### Пример 3. Переименование файла

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

Эта команда переименовывает файл. Он использует параметр **path** для ссылки на экземпляр класса **CIM_DataFile** . Затем она применяет метод Rename к этому конкретному экземпляру.

Если команда выполнена, свойство **ReturnValue** заполняется 0.

### Пример 4. Передача массива значений с помощью `-ArgumentList`

Пример использования массива объектов `$binSD` , за которым следует `$null` значение.

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## PARAMETERS

### -ArgumentList

Задает параметры для передачи в вызываемый метод. Значение этого параметра должно быть массивом объектов и должно находиться в том порядке, который требуется вызываемому методу. У `Invoke-CimCommand` командлета нет этих ограничений.

Чтобы определить порядок перечисления этих объектов, запустите `GetMethodParameters()` метод класса WMI, как показано в примере 1 в конце этого раздела.

> [!IMPORTANT]
> Если первое значение является массивом, который содержит более одного элемента, требуется второе значение $null. В противном случае команда вызывает ошибку: например, «Не удалось привести объект типа System.Byte к типу System.Array». См. Пример 4 выше.

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Указывает, что этот командлет выполняет команду как фоновое задание. Используйте этот параметр для запуска команд, на завершение которых требуется много времени.

При использовании параметра **AsJob** команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Если `Invoke-WmiMethod` используется на удаленном компьютере, задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер. Чтобы управлять заданием, используйте командлеты, которые содержат существительное Job (командлеты Job). Чтобы получить результаты задания, используйте командлет Receive-Job.

Для использования этого параметра с удаленными компьютерами локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия. Кроме того, необходимо запустить Windows PowerShell с помощью команды Запуск от имени администратора в Windows Vista и более поздних версиях Windows. Дополнительные сведения см. в разделе about_Remote_Requirements.

Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах about_Jobs и about_Remote_Jobs.

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

### -Authentication

Указывает уровень проверки подлинности, используемый для подключения к WMI. Допустимые значения для этого параметра:

- -1: без изменений
- 0: по умолчанию
- 1: нет (проверка подлинности не выполняется).
- 2: Connect (проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.)
- 3: вызов (проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос).
- 4: пакет (проверка подлинности выполняется для всех данных, полученных от клиента.)
- 5: Паккетинтегрити (все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.)
- 6: Паккетприваци (используются свойства других уровней проверки подлинности, и все данные шифруются).

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Центр

Указывает центр сертификации, используемый для проверки подлинности подключения к WMI. Можно указать стандартную проверку подлинности Windows NT LAN Manager (NTLM) или Kerberos. Чтобы использовать NTLM, установите для параметра authority значение ntlmdomain:\<DomainName\>, где \<DomainName\> указывает допустимое доменное имя NTLM. Чтобы использовать Kerberos, укажите kerberos:\<DomainName\ServerName\>. Параметр authority не может быть указан при подключении к локальному компьютеру.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class

Указывает класс WMI, который содержит вызываемый статический метод.

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает в виде массива строк компьютеры, на которых этот командлет выполняет команду. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь. Введите имя пользователя, например `User01` , `Domain01\User01` или `User@Contoso.com` . Или введите объект **PSCredential** , например объект, возвращаемый командлетом Get-Credential. При вводе имени пользователя появится приглашение ввести пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Енаблеаллпривилежес

Указывает, что этот командлет включает все привилегии текущего пользователя, прежде чем команда сделает вызов WMI.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Олицетворение

Задает используемый уровень олицетворения. Допустимые значения для этого параметра:

- 0: по умолчанию (считывает локальный реестр для уровня олицетворения по умолчанию, который обычно имеет значение "3: IMPERSONATE".)
- 1: anonymous (скрывает учетные данные вызывающей стороны).
- 2: Identify (позволяет объектам запрашивать учетные данные вызывающей стороны).
- 3. олицетворение (позволяет объектам использовать учетные данные вызывающей стороны).
- 4: делегат (позволяет объектам разрешить другим объектам использовать учетные данные вызывающей стороны).

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объект **ManagementObject** для использования в качестве входных данных. При использовании этого параметра все остальные параметры, за исключением параметров **Flag** и **Argument** , игнорируются.

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Locale

Указывает предпочтительный язык для объектов WMI. Укажите значение параметра **locale** в формате массива в `MS_<LCID>` предпочтительном порядке.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имя вызываемого метода. Этот параметр является обязательным и не может быть NULL или пустым.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

При использовании с параметром **класса** этот параметр указывает пространство имен репозитория WMI, в котором находится упоминаемый класс WMI или объект.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к объекту WMI класса WMI или указывает путь к объекту WMI экземпляра класса WMI. Заданный класс или экземпляр должны содержать метод, указанный в параметре **Name** .

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает значение регулирования для количества операций WMI, которые могут выполняться одновременно.
Этот параметр используется вместе с параметром **AsJob** . Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

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

### Нет

Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[Get-WmiObject](Get-WmiObject.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)
