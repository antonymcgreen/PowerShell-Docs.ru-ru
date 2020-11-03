---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227937"
---
# Remove-WmiObject

## Краткий обзор
Удаляет экземпляр существующего класса инструментария управления Windows (WMI).

## SYNTAX

### Класс (по умолчанию)

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### объект

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### path

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### вклкуери

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### query

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### list

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Remove-WmiObject** удаляет экземпляр существующего класса инструментарий управления Windows (WMI) (WMI).

## Примеры

### Пример 1. Закрытие всех экземпляров процесса Win32

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

В этом примере закрываются все экземпляры Notepad.exe.

Первая команда запускает экземпляр Блокнота.

Вторая команда использует командлет Get-WmiObject для получения экземпляров Win32_Process, соответствующих Notepad.exe, а затем сохраняет их в переменной $np.

Третья команда передает объект в переменную $np в **Remove-WmiObject** , удаляя все экземпляры Notepad.exe.

### Пример 2. Удаление папки

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

Эта команда удаляет папку C:\Test.

Первая команда использует **Get-WmiObject** для запроса папки C:\test, а затем сохраняет объект в переменной $a.

Вторая команда передает переменную $a в **Remove-WmiObject** , которая удаляет папку.

## PARAMETERS

### -AsJob
Указывает, что этот командлет запускается как фоновое задание.
Используйте этот параметр для запуска команд, на завершение которых требуется много времени.

В Windows PowerShell 3.0 появились новые командлеты CIM, которые выполняют те же задачи, что и командлеты WMI.
Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM), который позволяет командлетам использовать те же методы для управления компьютерами под управлением операционной системы Windows и другими операционными системами.
Вместо использования **Remove-WmiObject** рассмотрите возможность использования командлета Remove-CimInstance https://go.microsoft.com/fwlink/?LinkId=227964 .

При использовании параметра *AsJob* команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку.
Можно продолжить работу в рамках данного сеанса, пока задание завершается.
Если для удаленного компьютера используется **Remove-WmiObject** , задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.
Для управления заданием используйте командлеты, которые содержат существительное **задания** (командлеты **задания** ).
Чтобы получить результаты задания, используйте командлет Receive-Job.

Чтобы использовать этот параметр для удаленных компьютеров, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.
Запустите Windows PowerShell с помощью команды Запуск от имени администратора.
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
Указывает уровень проверки подлинности, используемый для WMI-соединения.
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
Указывает имя класса WMI, который удаляет этот командлет.

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
Если параметр используется, все остальные параметры пропускаются.

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
Параметр *locale* указывается в виде массива в \<LCID\> формате MS_ в предпочтительном порядке.

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
Указывает путь объекта WMI класса WMI или указывает путь объекта WMI удаляемого экземпляра класса WMI.

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

### System. Management. ManagementObject
Объект управления можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет, System. Management. Automation. Ремотингжоб
Этот командлет возвращает объект задания, если указан параметр *AsJob* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Set-WmiInstance](Set-WmiInstance.md)
