---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228361"
---
# Get-WmiObject

## Краткий обзор
Получает экземпляры классов инструментария управления Windows (WMI) или сведения о доступных классах.

## SYNTAX

### запрос (по умолчанию)

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### list

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### вклкуери

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### class

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### path

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## DESCRIPTION

Начиная с PowerShell 3,0 этот командлет был заменен `Get-CimInstance` .

`Get-WmiObject`Командлет получает экземпляры классов WMI или сведения о доступных классах WMI. Чтобы указать удаленный компьютер, используйте параметр **ComputerName** . Если указан параметр **List** , командлет получает сведения о классах WMI, доступных в указанном пространстве имен. Если указан параметр **Query** , командлет запускает инструкцию языка запросов WMI (WQL).

`Get-WmiObject`Командлет не использует удаленное взаимодействие Windows PowerShell для выполнения удаленных операций.
Параметр **ComputerName** командлета можно использовать, `Get-WmiObject` даже если компьютер не соответствует требованиям для удаленного взаимодействия Windows PowerShell или не настроен для удаленного взаимодействия в Windows PowerShell.

Начиная с Windows PowerShell 3,0, свойство **__Server** объекта, которое возвращает, `Get-WmiObject` имеет псевдоним **PSComputerName** . Это упрощает включение имени исходного компьютера во входные данные и отчеты.

## Примеры

### Пример 1. получение процессов на локальном компьютере

В этом примере получаются процессы на локальном компьютере.

```powershell
Get-WmiObject -Class Win32_Process
```

### Пример 2. Получение служб на удаленном компьютере

Этот пример получает службы на удаленном компьютере. Параметр **ComputerName** задает IP-адрес удаленного компьютера. По умолчанию текущая учетная запись пользователя должна быть членом группы **администраторов** на удаленном компьютере.

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### Пример 3. получение классов WMI в корневом каталоге или пространстве имен по умолчанию локального компьютера

В этом примере показано, как получить классы WMI в корневом пространстве имен или по умолчанию для локального компьютера.

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### Пример 4. получение именованной службы на нескольких компьютерах

В этом примере получается служба WinRM на компьютерах, указанных значением параметра **ComputerName** .

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

Оператор конвейера (|) отправляет выходные данные в `Format-List` командлет, который добавляет свойство **PSComputerName** к выходу по умолчанию. **PSComputerName** — это псевдоним свойства **__Server** объектов, которые `Get-WmiObject` возвращают. Этот псевдоним появился в PowerShell 3,0.

### Пример 5. Завершение службы на удаленном компьютере

В этом примере служба WinRM останавливается на удаленном компьютере. `Get-WmiObject` Возвращает экземпляр объекта службы WinRM в Server01. Затем он **вызывает метод «начало» класса** WMI **Win32_Service** для этого объекта.

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

Это эквивалентно использованию `Stop-Service` командлета.

### Пример 6. получение BIOS на локальном компьютере

Этот пример получает данные BIOS с локального компьютера. Параметр **Property** `Format-List` командлета используется для вывода всех свойств возвращенного объекта в списке. По умолчанию отображаются только подмножество свойств, определенных в `Types.ps1xml` файле конфигурации.

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### Пример 7. Получение служб на удаленном компьютере

В этом примере используется параметр **Credential** `Get-WmiObject` командлета для получения служб на удаленном компьютере. Значение параметра **Credential** является именем учетной записи пользователя. Пользователю предлагается ввести пароль.

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> Учетные данные нельзя использовать при нацеливании на локальный компьютер.

## PARAMETERS

### — Исправлено

Получает или задает значение, которое указывает, должны ли объекты, возвращаемые из WMI, содержать измененные сведения. Обычно измененные сведения — это сведения, подлежащие локализации: например, описания объекта и свойства, вложенные в объект WMI.

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

### -AsJob

Выполняет команду как фоновое задание. Используйте этот параметр для запуска команд, на завершение которых требуется много времени.

При использовании параметра **AsJob** команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Если `Get-WmiObject` используется на удаленном компьютере, задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер. Для управления заданием используйте командлеты, которые содержат командлеты задания. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

> [!NOTE]
> Для использования этого параметра с удаленными компьютерами локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия. Кроме того, необходимо запустить Windows PowerShell с параметром "Запуск от имени администратора" в Windows Vista и более поздних версиях Windows. Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).

Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).

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

Указывает уровень проверки подлинности, используемый для подключения к WMI.
Допустимые значения:

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
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Центр

Указывает центр сертификации, используемый для проверки подлинности подключения к WMI. Можно выбрать стандартную проверку подлинности NTLM или Kerberos. Чтобы использовать NTLM, задайте для параметра центра сертификации значение `ntlmdomain:<DomainName>` , где `<DomainName>` определяет допустимое доменное имя NTLM. Чтобы использовать Kerberos, укажите `kerberos:<DomainName>\<ServerName>` . Параметр authority не может быть указан при подключении к локальному компьютеру.

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

### -Class

Задает имя класса WMI. Если используется этот параметр, командлет возвращает экземпляры класса WMI.

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает целевой компьютер для операции управления. Введите полное доменное имя, имя NetBIOS или IP-адрес. Если удаленный компьютер находится в домене, отличном от домена локального компьютера, необходимо указать полное доменное имя.

По умолчанию это локальный компьютер. Чтобы указать локальный компьютер (например, в списке имен компьютеров), используйте localhost, имя локального компьютера или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell, которое использует командлет WS-Management. Параметр **ComputerName** можно использовать, `Get-WmiObject` даже если компьютер не настроен для выполнения WS-Management удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь. Введите имя пользователя, например "User01", "Domain01\User01", или User@Contoso.com . Или введите объект **PSCredential** , например объект, возвращаемый `Get-Credential` командлетом. При вводе имени пользователя запрашивается пароль. Учетные данные нельзя использовать при нацеливании на локальный компьютер.

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

### -Директреад

Указывает, запрашивается ли прямой доступ к поставщику WMI для данного класса безотносительно базового класса или его наследуемых классов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Енаблеаллпривилежес

Включает все привилегии текущего пользователя перед вызовом WMI в команде.

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

### -Filter

Указывает предложение **Where** для использования в качестве фильтра. Использует синтаксис языка запросов WMI (WQL).

> [!IMPORTANT]
> Не включайте ключевое слово **Where** в значение параметра. Например, следующие команды возвращают только логические диски с **DeviceID** для "c:" и службы с именем WinRM без использования ключевого слова **Where** .

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Олицетворение

Задает используемый уровень олицетворения.

Допустимые значения для этого параметра:

- 0: по умолчанию. Считывает локальный реестр для уровня олицетворения по умолчанию. По умолчанию обычно устанавливается **олицетворение** .
- 1: анонимный. Скрывает учетные данные вызывающей стороны.
- 2: выявление. позволяет объектам запрашивать учетные данные вызывающей стороны.
- 3. олицетворение. позволяет объектам использовать учетные данные вызывающей стороны.
- 4: делегат. Позволяет объектам разрешать другим объектам использовать учетные данные вызывающей стороны.

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

### -List

Получает имена классов WMI в пространстве имен репозитория WMI, который указан параметром **Namespace** .

Если указать параметр **List** , но не параметр **Namespace** , `Get-WmiObject` по умолчанию использует пространство имен **Root\Cimv2** . Этот командлет не использует запись реестра **по умолчанию для пространства имен** в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` реестра для определения пространства имен по умолчанию.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Locale

Указывает предпочтительный язык для объектов WMI.
Введите значение в формате MS_\<LCID\>.

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

### -Namespace

При использовании с параметром **Class** параметр **Namespace** указывает пространство имен репозитория WMI, где располагается указанный класс WMI. При использовании с параметром **List** указывается пространство имен, из которого собирается информация о классе WMI.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Указывает свойства класса WMI, из которого этот командлет получает сведения. Введите имена свойств.

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Запускает указанную инструкцию языка запросов WMI (WQL). Этот параметр не поддерживает очереди событий.

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Ищет текущее пространство имен и все остальные пространства имен для имени класса, указанного параметром **Class** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное количество операций WMI, которые можно выполнить одновременно. Этот параметр допустим только в том случае, если в команде используется параметр **AsJob** .

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в `Get-WmiObject` .

## Выходные данные

### PSObject или System. Management. Automation. Ремотингжоб

При использовании параметра **AsJob** командлет возвращает объект задания. В противном случае `Get-WmiObject` возвращаемый объект зависит от значения параметра **класса** .

## ПРИМЕЧАНИЯ

Чтобы получить доступ к сведениям о WMI на удаленном компьютере, командлет необходимо запустить в рамках учетной записи, которая является членом группы локальных администраторов на удаленном компьютере. Кроме того, контроль доступа по умолчанию в пространстве имен WMI удаленного репозитория можно изменить, предоставив права доступа другим учетным записям.

Только некоторые свойства каждого класса WMI отображаются по умолчанию. Набор свойств, который отображается для каждого класса WMI, указан в файле конфигурации Types.ps1xml. Чтобы получить все свойства объекта WMI, используйте `Get-Member` `Format-List` командлеты или.

## Связанные ссылки

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
