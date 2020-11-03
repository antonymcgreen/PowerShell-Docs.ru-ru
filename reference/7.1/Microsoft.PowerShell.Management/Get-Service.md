---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 7f44f1d363c5fae79722fdfb5bd894cb24e00d0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229605"
---
# Get-Service

## Краткий обзор
Возвращает службы на компьютере.

## SYNTAX

### Default (по умолчанию)

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Service`Командлет возвращает объекты, представляющие службы на компьютере, включая запуск и остановку служб. По умолчанию, если `Get-Service` выполняется без параметров, возвращаются все службы локального компьютера.

Вы можете направить этот командлет для получения только определенных служб, указав имя службы или отображаемое имя службы, либо можно передать объекты службы в этот командлет.

## Примеры

### Пример 1. получение всех служб на компьютере

Этот пример возвращает все службы на компьютере. Он ведет себя так, как будто вы ввели `Get-Service *` . По умолчанию отображается состояние, имя службы и отображаемое имя каждой службы.

```powershell
Get-Service
```

### Пример 2. Получение служб, начинающихся со строки поиска

В этом примере извлекаются службы с именами служб, которые начинаются с WMI (инструментарий управления Windows (WMI)).

```powershell
Get-Service "wmi*"
```

### Пример 3. Отображение служб, содержащих строку поиска

В этом примере отображаются службы с отображаемым именем, которое содержит слово Network. При поиске отображаемого имени выполняется поиск служб, связанных с сетью, даже если имя службы не содержит NET, например ксмлпров, службы подготовки сети.

```powershell
Get-Service -Displayname "*network*"
```

### Пример 4. Получение служб, начинающихся со строки поиска и исключения

Этот пример получает только службы с именами служб, которые начинаются с **Win** , за исключением службы WinRM.

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### Пример 5. отображение активных в данный момент служб

В этом примере отображаются только службы с состоянием работает.

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

`Get-Service` Получает все службы на компьютере и отправляет объекты по конвейеру. `Where-Object`Командлет выбирает только службы со свойством **Status** , которое равно "работает".

Status — это лишь одно из свойств объектов служб. Чтобы просмотреть все свойства, введите `Get-Service | Get-Member` .

### Пример 6. Перечисление служб на компьютере с зависимыми службами

Этот пример получает службы, имеющие зависимые службы.

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

`Get-Service`Командлет получает все службы на компьютере и отправляет объекты по конвейеру. `Where-Object`Командлет выбирает службы, свойство **DependentServices** которых не имеет значение null.

Результаты отправляются в командлет по конвейеру `Format-List` . Параметр **Property** отображает имя службы, имя зависимых служб и вычисляемое свойство, которое отображает количество зависимых служб для каждой службы.

### Пример 7. Сортировка служб по значению свойства

В этом примере показано, что при сортировке служб в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед запуском служб. Причина заключается в том, что значение **Status** — это перечисление, в котором Stopped имеет значение 1, а параметр выполняется значение 4. Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

Чтобы сначала получить список выполняющихся служб, используйте параметр по **убыванию** `Sort-Object` командлета.

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

### Пример 8. получение зависимых служб Службы

В этом примере получаются службы, необходимые службе WinRM. Возвращается значение свойства **ServicesDependedOn** службы.

```powershell
Get-Service "WinRM" -RequiredServices
```

### Пример 9. Получение службы с помощью оператора конвейера

В этом примере получается служба WinRM на локальном компьютере. Строка имени службы, заключенная в кавычки, отправляется в конвейер в `Get-Service` .

```powershell
"WinRM" | Get-Service
```

## PARAMETERS

### -DependentServices

Указывает, что этот командлет возвращает только те службы, которые зависят от указанной службы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Указывает в виде массива строк отображаемые имена служб для извлечения. Разрешено использовать подстановочные знаки.

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
Значение этого параметра определяет параметр **Name** . Введите элемент имени или шаблон, например `s*` . Разрешено использовать подстановочные знаки.

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

Указывает в качестве массива строк, службы или службы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Name** . Введите элемент имени или шаблон, например `s*` . Разрешено использовать подстановочные знаки.

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

Указывает объекты **ServiceController** , представляющие извлекаемые службы. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Объект службы можно передать в этот командлет по конвейеру.

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

Задает имена получаемых служб. Разрешено использовать подстановочные знаки.

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

Указывает, что этот командлет получает только те службы, которые требуются этой службе. Этот параметр возвращает значение свойства **ServicesDependedOn** службы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
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

Начиная с PowerShell 6,0 в объекты **ServiceController** добавляются следующие свойства: **username** , **Description** , **делайедаутостарт** , **бинарипаснаме** и **StartupType** .

Также можно ссылаться `Get-Service` по встроенному псевдониму `gsv` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Этот командлет может отображать службы только в том случае, если у текущего пользователя есть разрешение на их просмотр. Если этот командлет не отображает службы, возможно, у вас нет разрешения на их просмотр.

Чтобы найти имя службы и отображаемое имя каждой службы в системе, введите `Get-Service` . Имена служб отображаются в столбце имя, а отображаемые имена отображаются в столбце **DisplayName** .

При сортировке в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед выполнением служб. Свойство **Status** службы имеет перечислимое значение, а имена состояний представляют целочисленные значения. Порядок сортировки основан на целочисленном значении, а не на имени. Остановлено перед запуском, так как параметр Stopped имеет значение 1, а для параметра работает значение 4. Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

## Связанные ссылки

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)

