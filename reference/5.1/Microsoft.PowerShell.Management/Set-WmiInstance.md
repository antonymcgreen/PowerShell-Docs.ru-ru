---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227870"
---
# Set-WmiInstance

## Краткий обзор
Создает или обновляет экземпляр существующего класса WMI.

## SYNTAX

### Класс (по умолчанию)

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### объект

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### вклкуери

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
`Set-WmiInstance`Командлет создает или обновляет экземпляр существующего класса инструментарий управления Windows (WMI) (WMI).
Созданный или обновленный экземпляр записывается в репозиторий WMI.

В Windows PowerShell 3.0 появились новые командлеты CIM, которые выполняют те же задачи, что и командлеты WMI.
Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM).
Это позволяет командлетам использовать те же методы для управления компьютерами под управлением Windows и с другими операционными системами.
Вместо использования `Set-WmiInstance` , рассмотрите возможность использования командлетов [Set-Ciminstance](/powershell/module/cimcmdlets/set-ciminstance) или [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) .

## Примеры

### Пример 1. Настройка уровня ведения журнала WMI

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

Эта команда задает 2 уровень ведения журнала WMI.
Команда передает свойство в значение, которое вместе считается парой значений в параметре argument.
Параметр принимает хэш-таблицу, которая определяется конструкцией @{property = value}.
Возвращаемые сведения о классе отражают новое значение.

### Пример 2. Создание переменной среды и ее значения

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

Эта команда создает переменную среды testvar, которая имеет значение testValue.
Для этого создается новый экземпляр класса **Win32_Environment** WMI.
Для этой операции требуются соответствующие учетные данные, поэтому для просмотра новой переменной среды может потребоваться перезапустить Windows PowerShell.

### Пример 3. Настройка уровня ведения журнала WMI для нескольких удаленных компьютеров

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

Эта команда задает 2 уровень ведения журнала WMI.
Команда передает свойство в значение, которое вместе считается парой значений в параметре argument.
Параметр принимает хэш-таблицу, которая определяется конструкцией @{property = value}.
Возвращаемые сведения о классе отражают новое значение.

## PARAMETERS

### -Arguments
Указывает имя свойства, которое необходимо изменить, и новое значение свойства.
Имя и значение должны быть парой "имя-значение".
Пара "имя-значение" передается в командной строке в виде хэш-таблицы.
Пример:

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Указывает, что этот кмдкет выполняется как фоновое задание.
Используйте этот параметр для запуска команд, на завершение которых требуется много времени.

При указании параметра *AsJob* команда возвращает объект, представляющий фоновое задание, а затем отображает командную строку.
Можно продолжить работу в рамках данного сеанса, пока задание завершается.
Если для удаленного компьютера используется **Set-WmiInstance** , задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.
Для управления заданием используйте командлеты, которые содержат существительное **задания** (командлеты **задания** ).
Чтобы получить результаты задания, используйте командлет Receive-Job.

Чтобы использовать этот параметр вместе с удаленными компьютерами, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.
Кроме того, необходимо запустить Windows PowerShell с помощью команды Запуск от имени администратора в Windows Vista и более поздних версиях операционной системы Windows.
Дополнительные сведения см. в разделе about_Remote_Requirements.

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
Указывает уровень проверки подлинности, который должен использоваться с WMI Connection.
Допустимые значения для этого параметра:

- -1: без изменений.
- 0: по умолчанию.
- 1: нет.
Проверка подлинности не выполняется.
- 2: подключение.
Проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.
- 3: вызов.
Проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос.
- 4: пакет.
Проверка подлинности выполняется для всех данных, получаемых от клиента.
- 5: Паккетинтегрити.
Все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.
- 6: Паккетприваци.
Используются свойства других уровней проверки подлинности, а все данные шифруются.

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
Указывает центр сертификации, используемый для проверки подлинности подключения к WMI.
Можно выбрать стандартную проверку подлинности NTLM или Kerberos.
Чтобы использовать NTLM, установите для параметра authority значение ntlmdomain:\<DomainName\>, где \<DomainName\> указывает допустимое доменное имя NTLM.
Чтобы использовать Kerberos, укажите Kerberos: \<DomainName\> \\ \<ServerName\> .
Параметр authority не может быть указан при подключении к локальному компьютеру.

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
Задает имя класса WMI.

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
Указывает имя компьютера, на котором выполняется этот командлет.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

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
Указывает учетную запись пользователя с разрешением на выполнение этого действия.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например User01 или Domain01\User01, либо укажите объект **PSCredential** , например формируемый командлетом Get-Credential.
При вводе имени пользователя этот командлет запрашивает пароль.

Этот параметр не поддерживается поставщиками, установленными с параметром, не поддерживается какими-либо поставщиками, установленными с помощью Windows PowerShell.

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
Указывает, что этот командлет включает все разрешения текущего пользователя перед выполнением команды WMI.

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
Задает используемый уровень олицетворения.
Допустимые значения для этого параметра:

- 0: по умолчанию.
Считывает локальный реестр для уровня олицетворения по умолчанию, который обычно имеет значение 3: IMPERSONATE.
- 1: анонимный.
Скрывает учетные данные вызывающей стороны.
- 2: выявление.
позволяет объектам запрашивать учетные данные вызывающей стороны.
- 3. олицетворение.
позволяет объектам использовать учетные данные вызывающей стороны.
- 4: делегат.
Позволяет объектам разрешать другим объектам использовать учетные данные вызывающей стороны.

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
Указывает объект **ManagementObject** для использования в качестве входных данных.
При использовании этого параметра все остальные параметры, за исключением параметра *arguments* , игнорируются.

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
Указывает предпочтительный язык для объектов WMI.
Параметр *locale* указывается в массиве в \<LCID\> формате MS_ в предпочтительном порядке.

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

### -Namespace
Указывает пространство имен репозитория WMI, в котором расположен ссылочный класс WMI, если он используется с параметром *класса* .

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
Указывает путь к объекту WMI экземпляра, который необходимо создать или обновить.

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

### -Путтипе
Указывает, следует ли создать или обновить экземпляр WMI.
Допустимые значения для этого параметра:

- Упдатеонли.
обновляет существующий экземпляр WMI.
- Креатеонли.
создает новый экземпляр WMI.
- Упдатеоркреате.
обновляет экземпляр WMI, если он существует, или создает новый экземпляр, если экземпляр не существует.

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Этот параметр используется вместе с параметром *AsJob* .
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
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Этот командлет не принимает входные данные.

## Выходные данные

### Нет
Этот командлет не создает никакие выходные данные.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)
