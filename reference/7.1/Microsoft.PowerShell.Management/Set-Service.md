---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: 9881dccb78aab973cc6031e28308bbdd27b4da57
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229602"
---
# Set-Service

## Краткий обзор
Запускает, останавливает и приостанавливает службу и изменяет ее свойства.

## SYNTAX

### Имя (по умолчанию)

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### Пример 7. Завершение службы в удаленной системе

В этом примере останавливается служба на удаленном компьютере.
Дополнительные сведения см. в разделе [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

`Get-Credential` запрашивает имя пользователя и пароль и сохраняет учетные данные в `$Cred` переменной. `Get-Service` использует параметр **Name** для указания службы **расписания** . Объект хранится в переменной `$S` .

`Invoke-Command` Задает удаленный компьютер с помощью параметра **ComputerName** . Параметр **Credential** использует `$Cred` переменную для входа на компьютер. Блок **ScriptBlock** вызывает `Set-Service` . Параметр **InputObject** указывает хранимый объект службы `$S` . Параметр **Status** задает **остановку** службы.

### Пример 8. изменение учетных данных службы

В этом примере изменяются учетные данные, используемые для управления службой.

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

`Get-Credential` запрашивает имя пользователя и пароль и сохраняет учетные данные в `$credential` переменной. `Set-Service` использует параметр **Name** для указания службы **расписания** . Параметр **Credential** использует `$credential` переменную и обновляет службу **расписания** .

### Пример 9. изменение SecurityDescriptor службы

В этом примере изменяется **SecurityDescriptor** службы.

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

**SecurityDescriptor** хранится в `$SDDL` переменной. `Set-Service` использует параметр **Name** для указания службы **BITS** . Параметр **SecurityDescriptorSddl** использует, `$SDDL` чтобы изменить **SecurityDescriptor** для службы **BITS** .

## PARAMETERS

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

### -Credential

Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя этот командлет запрашивает пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Этот параметр появился в PowerShell 6,0.

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

### -Force

Указывает режим отмены службы. Этот параметр работает, только если `-Status Stopped` используется. Если параметр включен, `Set-Service` зависимые службы останавливаются до того, как целевая служба будет остановлена. По умолчанию исключения возникают, когда другие работающие службы зависят от целевой службы.

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

### -InputObject

Указывает объект **ServiceController** , представляющий службу, которую необходимо изменить. Введите переменную, содержащую объект, или введите команду или выражение, которое получает объект, например `Get-Service` команду. Для отправки объекта службы в можно использовать конвейер `Set-Service` .

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
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

Указывает режим запуска службы.

Для этого параметра допустимы следующие значения:

- **Автоматически** — служба запущена или была запущена операционной системой при запуске системы.
  Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.
- **Аутоматикделайедстарт** — запускается вскоре после загрузки системы.
- **Отключено** — служба отключена и не может быть запущена пользователем или приложением.
- **Инвалидвалуе** — не действует. Командлет не возвращает ошибку, но StartupType службы не изменяется.
- **Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
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

### -SecurityDescriptorSddl

Указывает **SecurityDescriptor** для службы в формате **SDDL** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

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

[Remove-Service](Remove-Service.md)

