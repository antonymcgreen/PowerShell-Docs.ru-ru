---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228366"
---
# Get-Service

## Краткий обзор
Получает службы на локальном или удаленном компьютере.

## SYNTAX

### Default (по умолчанию)

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-Service** возвращает объекты, представляющие службы на локальном компьютере или на удаленном компьютере, включая запуск и остановку служб.

Вы можете направить этот командлет для получения только определенных служб, указав имя службы или отображаемое имя службы, либо можно передать объекты службы в этот командлет.

## Примеры

### Пример 1. получение всех служб на компьютере

```powershell
Get-Service
```

Эта команда возвращает все службы на компьютере.
Он ведет себя так, как будто вы ввели `Get-Service *` .
По умолчанию отображается состояние, имя службы и отображаемое имя каждой службы.

### Пример 2. Получение служб, начинающихся со строки поиска

```powershell
Get-Service "wmi*"
```

Эта команда извлекает службы с именами служб, которые начинаются с WMI (аббревиатура для инструментарий управления Windows (WMI)).

### Пример 3. Отображение служб, содержащих строку поиска

```powershell
Get-Service -Displayname "*network*"
```

Эта команда отображает службы с отображаемым именем, которое содержит слово Network.
При поиске отображаемого имени команда находит службы, связанные с сетью, даже если имя службы не включает слово Net. (Например, служба подготовки сети (Network Provisioning Service) имеет имя xmlprov.)

### Пример 4. Получение служб, начинающихся со строки поиска и исключения

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

Эти команды получают только службы с именами служб, которые начинаются с Win, за исключением службы WinRM.

### Пример 5. отображение активных в данный момент служб

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

Эта команда отображает только те службы, которые активны в данный момент.
Для получения всех служб на компьютере используется командлет **Get-Service** .
Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает только службы со свойством Status, которое равно "выполняется".

Status — это лишь одно из свойств объектов служб.
Чтобы просмотреть все свойства, введите `Get-Service | Get-Member` .

### Пример 6. Получение служб на удаленном компьютере

```powershell
Get-Service -ComputerName "Server02"
```

Эта команда получает службы на удаленном компьютере Server02.

Поскольку параметр *ComputerName* командлета **Get-Service** не использует удаленное взаимодействие Windows PowerShell, этот параметр можно использовать, даже если компьютер не настроен для удаленного взаимодействия в Windows PowerShell.

### Пример 7. Перечисление служб на локальном компьютере с зависимыми службами

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

Первая команда использует командлет **Get-Service** для получения служб на компьютере.
Оператор конвейера (|) отправляет службы в командлет **Where-Object** , который выбирает службы, свойство **DependentServices** которых не равно null.

Другой оператор конвейера отправляет результаты в командлет Format-List.
В команде используется параметр *Property* для отображения имени службы, имени зависимых служб и вычисляемого свойства, отображающего количество зависимых служб, которые имеет каждая служба.

### Пример 8. Сортировка служб по значению свойства

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

Эта команда показывает, что при сортировке служб в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед запуском служб.
Это происходит из-за того, что значение Status является перечислением, в котором значение Stopped равно 1, а параметру выполняется значение 4.

Чтобы сначала получить список выполняющихся служб, используйте параметр *сортировки* командлета Sort-Object.

### Пример 9. Получение служб на нескольких компьютерах

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

Эта команда использует командлет **Get-Service** для выполнения команды Get-Service WinRM на двух удаленных компьютерах и на локальном компьютере ("localhost").

Команда выполняется на удаленных компьютерах, а результаты возвращаются на локальный компьютер.
Оператор конвейера (|) отправляет результаты в командлет **Format-Table** , который форматирует службы в виде таблицы.
Команда **Format-Table** использует параметр *Property* для указания свойств, отображаемых в таблице, включая свойство **MachineName** .

### Пример 10. получение зависимых служб Службы

```powershell
Get-Service "WinRM" -RequiredServices
```

Эта команда получает службы, которые требуются службе WinRM.

Команда возвращает значение свойства **ServicesDependedOn** службы.

### Пример 11. Получение службы с помощью оператора конвейера

```powershell
"WinRM" | Get-Service
```

Эта команда получает службу WinRM на локальном компьютере.
В этом примере показано, что для **Get-Service** можно передать строку имени службы (заключенную в кавычки).

## PARAMETERS

### -ComputerName

Получает службы, выполняемые на указанных компьютерах.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* командлета **Get-Service** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependentServices

Указывает, что этот командлет возвращает только те службы, которые зависят от указанной службы.

По умолчанию этот командлет получает все службы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Указывает в виде массива строк отображаемые имена служб для извлечения.
Разрешено использовать подстановочные знаки.
По умолчанию этот командлет получает все службы на компьютере.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Exclude

Указывает в виде массива строк, службы или служб, которые этот командлет исключает из операции.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Указывает в качестве массива строк, службы или службы, которые этот командлет включает в операцию.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Указывает объекты **ServiceController** , представляющие извлекаемые службы.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.
Объект службы также можно передать в этот командлет по конвейеру.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Задает имена получаемых служб.
Разрешено использовать подстановочные знаки.
По умолчанию этот командлет получает все службы на компьютере.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -RequiredServices

Указывает, что этот командлет получает только те службы, которые требуются этой службе.

Этот параметр возвращает значение свойства **ServicesDependedOn** службы.
По умолчанию этот командлет получает все службы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.ServiceProcess.ServiceController, System.String

В этот командлет можно передать объект службы или имя службы.

## Выходные данные

### System.ServiceProcess.ServiceController

Этот командлет возвращает объекты, представляющие службы на компьютере.

## ПРИМЕЧАНИЯ

Можно также обратиться к **Get-Service** по встроенному псевдониму «ГСВ». Подробнее см. в разделе "about_Aliases".

Этот командлет может отображать службы только в том случае, если у текущего пользователя есть разрешение на их просмотр.
Если этот командлет не отображает службы, возможно, у вас нет разрешения на их просмотр.

Чтобы найти имя службы и отображаемое имя каждой службы в системе, введите `Get-Service` .
Имена служб отображаются в столбце Name, а отображаемые имена — в столбце DisplayName.

При сортировке по возрастанию по значению состояния "остановленные" службы предшествуют "выполняющимся".
Свойство Status службы — это перечисляемое значение, в котором имена состояний представляют целые значения.
Порядок сортировки основан на целочисленном значении, а не на имени.
"Выполняется" отображается до "Остановлена", так как состояние "Остановлена" имеет значение 1, а "Выполняется" — значение "4".

## Связанные ссылки

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
