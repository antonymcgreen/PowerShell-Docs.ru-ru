---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: 71b9ac57b2ab27e26f3a7454662f231b6e1dd764
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228749"
---
# Start-Service

## Краткий обзор
Запускает одну или несколько остановленных служб.

## SYNTAX

### InputObject (по умолчанию)

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Start-Service`Командлет отправляет начальное сообщение в контроллер служб Windows для каждой из указанных служб. Если служба уже запущена, сообщение пропускается без ошибок. Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр **InputObject** для предоставления объекта службы, представляющего службы, которые необходимо запустить.

## Примеры

### Пример 1. Запуск службы с помощью ее имени

В этом примере запускается служба EventLog на локальном компьютере. Параметр **Name** идентифицирует службу по ее имени службы.

```powershell
Start-Service -Name "eventlog"
```

### Пример 2. Отображение сведений без запуска службы

В этом примере показано, что произойдет при запуске служб с отображаемым именем, которое содержит "Remote".

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

Параметр **DisplayName** определяет службы по отображаемому имени, а не по имени службы. Параметр **WhatIf** приводит к тому, что командлет отображает, что произойдет при выполнении команды, но не вносит изменения.

### Пример 3. Запуск службы и запись действия в текстовый файл

В этом примере запускается служба инструментарий управления Windows (WMI) (WMI) на компьютере и добавляется запись действия в файл services.txt.

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

Сначала мы используем `Get-Service` , чтобы получить объект, который представляет службу WMI, и сохранить ее в `$s` переменной. Далее мы начнем службу. Без параметра **PassThru** `Start-Service` не создает никаких выходных данных. Оператор конвейера (|) передает выходные данные объекта `Start-Service` в командлет, `Format-List` чтобы отформатировать объект как список его свойств. Оператор добавления перенаправления ( \> \> ) перенаправляет выходные данные в файл services.txt. Выходные данные добавляются в конец существующего файла.

### Пример 4. Запуск отключенной службы

В этом примере показано, как запустить службу при **отключенном** типе запуска службы.

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

При первой попытке запуска службы Telnet (tlntsvr) происходит сбой. `Get-CimInstance`Команда показывает, что свойство **StartMode** службы tlntsvr **отключено** . `Set-Service`Командлет изменяет тип запуска на **ручной** . Теперь мы можем повторно отправить `Start-Service` команду. В этот раз команда будет успешно выполнена. Чтобы убедиться, что команда выполнена, выполните команду `Get-Service` .

## PARAMETERS

### -DisplayName

Указывает отображаемые имена запускаемых служб. Можно использовать подстановочные знаки.

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

Указывает службы, которые пропускает этот командлет. Значение этого параметра определяет параметр **Name** . Введите элемент имени или шаблон, например `s*` . Можно использовать подстановочные знаки.

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

Указывает службы, которые запускается этим командлетом. Значение этого параметра определяет параметр **Name** . Введите элемент имени или шаблон, например `s*` . Можно использовать подстановочные знаки.

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

Указывает объекты **ServiceController** , представляющие запускаемые службы. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена службы запускаемой службы.

Имя параметра является необязательным. Можно использовать **имя** или его псевдоним, **ServiceName** , или можно опустить имя параметра.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий службу. По умолчанию этот командлет не создает выходные данные.

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

### System.ServiceProcess.ServiceController, System.String

В этот командлет можно передать объекты, представляющие службы или строки, которые содержат имена служб.

## Выходные данные

### Нет или System.ServiceProcess.ServiceController

Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при указании **PassThru** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Также можно ссылаться `Start-Service` по встроенному псевдониму `sasv` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
* `Start-Service` может управлять службами, только если у текущего пользователя есть разрешение на это. Если команда работает неправильно, возможно, у вас нет необходимых разрешений.
* Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.
  Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .
* Можно запускать только службы с типом запуска вручную, автоматически или автоматически (отложенный запуск). Нельзя запустить службы с отключенным типом запуска. Если `Start-Service` команда завершается с сообщением `Cannot start service \<service-name\> on computer` , используйте `Get-CimInstance` для поиска типа запуска службы и при необходимости используйте `Set-Service` командлет, чтобы изменить тип запуска службы.
* Некоторые службы, такие как журналы и оповещения производительности (SysmonLog), останавливаются автоматически, если у них нет работы. Когда служба PowerShell запускает службу, которая останавливается почти сразу же, она отображает следующее сообщение: `Service \<display-name\> start failed.`

## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)

