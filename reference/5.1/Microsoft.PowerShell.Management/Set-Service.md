---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227873"
---
# Set-Service

## Краткий обзор
Запускает, останавливает и приостанавливает службу и изменяет ее свойства.

## SYNTAX

### Имя (по умолчанию)

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Service`Командлет изменяет свойства службы, такие как **Status** , **Description** , **DisplayName** и **StartupType** . `Set-Service` может запускать, останавливать, приостанавливать или прирывать работу службы. Чтобы указать службу, введите ее имя службы или отправьте объект службы. Или отправьте имя службы или объект службы по конвейеру в `Set-Service` .

## Примеры

### Пример 1. Изменение отображаемого имени

В этом примере изменяется отображаемое имя службы. Чтобы просмотреть исходное отображаемое имя, используйте `Get-Service` .

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` использует параметр **Name** для указания имени службы **LanmanWorkstation** . Параметр **DisplayName** указывает новое отображаемое имя, **рабочую станцию LanMan** .

### Пример 2. изменение типа запуска служб

В этом примере показано, как изменить тип запуска службы.

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

`Set-Service` использует параметр **Name** для указания имени службы ( **бит** ). Параметр **StartupType** задает **Автоматический** режим службы.

`Get-Service` использует параметр **Name** , чтобы указать службу **BITS** и отправить объект по конвейеру. `Select-Object` использует параметр **Property** для вывода состояния службы **BITS** .

### Пример 3. изменение описания службы

В этом примере изменяется описание службы BITS и отображается результат.

`Get-CimInstance`Используется командлет, так как он возвращает объект **Win32_Service** , содержащий **Описание** службы.

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

`Get-CimInstance` отправляет объект по конвейеру в `Format-List` и отображает имя и описание службы. В целях сравнения команда выполняется до и после обновления описания.

`Set-Service` использует параметр **Name** для указания службы **BITS** . Параметр **Description** указывает обновленный текст для описания служб.

### Пример 4. Запуск службы

В этом примере запускается служба.

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

`Set-Service` использует параметр **Name** для указания службы, **WinRM** . Параметр **Status** использует значение **выполняется** для запуска службы. Параметр **PassThru** выводит объект **ServiceController** , отображающий результаты.

### Пример 5. Приостановка службы

В этом примере используется конвейер для приостановки к службе.

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service` использует параметр **Name** для указания службы **расписания** и отправляет объект по конвейеру. `Set-Service` использует параметр **Status** , чтобы настроить **приостановку** службы.

### Пример 6. Завершение службы

В этом примере используется переменная для завершения службы.

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service` использует параметр **Name** для указания службы, **Schedule** . Объект хранится в переменной `$S` . `Set-Service` использует параметр **InputObject** и указывает хранимый объект `$S` . Параметр **Status** задает **остановку** службы.

## PARAMETERS

### -ComputerName

Указывает один или несколько компьютеров. Для удаленных компьютеров введите имя NetBIOS, IP-адрес или полное доменное имя. Если параметр **ComputerName** не указан, команда выполняется на локальном компьютере.

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед запуском `Set-Service` .

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

### -Description

Задает новое описание службы.

Описание службы отображается в оснастке « **Управление компьютером», «службы** ». **Описание** не является свойством `Get-Service` объекта **ServiceController** . Чтобы просмотреть описание службы, используйте метод `Get-CimInstance` , возвращающий объект **Win32_Service** , представляющий службу.

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

### -DisplayName

Задает новое отображаемое имя службы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объект **ServiceController** , представляющий службу, которую необходимо изменить. Введите переменную, содержащую объект, или введите команду или выражение, которое получает объект, например `Get-Service` команду. Для отправки объекта службы в можно использовать конвейер `Set-Service` .

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имя службы, которую нужно изменить. Подстановочные знаки не допускаются. Вы можете использовать конвейер для отправки имени службы в `Set-Service` .

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект **ServiceController** , представляющий измененные службы. По умолчанию `Set-Service` не создает никаких выходных данных.

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

### -StartupType

Задает тип запуска службы. Допустимые значения для этого параметра:

- **Автоматически** — служба запущена или была запущена операционной системой при запуске системы.
  Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.
- **Отключено** — служба отключена и не может быть запущена пользователем или приложением.
- **Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.
- **Загрузка** — указывает, что служба является драйвером устройства, запущенным загрузчиком системы. Это значение допустимо только для драйверов устройств.
- **Система** — указывает, что служба является драйвером устройства, запущенным функцией "иоинитсистем ()". Это значение допустимо только для драйверов устройств.

 Значение по умолчанию — **Automatic** .

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -Состояние

Указывает состояние службы.

Для этого параметра допустимы следующие значения:

- **Приостановлено** . приостанавливает службу.
- **Работает** . запускает службу.
- **Остановлена** . останавливает службу.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при `Set-Service` запуске. Командлет не выполняется.

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

Конвейер можно использовать для отправки объекта службы или строки, содержащей имя службы, в `Set-Service` .

## Выходные данные

### System.ServiceProcess.ServiceController

По умолчанию `Set-Service` не возвращает никаких объектов. Используйте параметр **PassThru** для вывода объекта **ServiceController** .

## ПРИМЕЧАНИЯ

`Set-Service` требуются повышенные разрешения. Используйте команду **Запуск от имени администратора** .

`Set-Service` может управлять только службами, если у текущего пользователя есть разрешения на управление службами. Если команда работает неправильно, возможно, у вас нет необходимых разрешений.

Чтобы найти имя службы или отображаемое имя службы, используйте `Get-Service` . Имена служб находятся в столбце **имя** , а отображаемые имена — в столбце **DisplayName** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
