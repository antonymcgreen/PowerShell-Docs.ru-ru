---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 7ba9bf66295bcbc2d8f7b7f94007b3fb673882fb
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890980"
---
# New-Service

## Краткий обзор
Создает новую службу Windows.

## SYNTAX

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`New-Service`Командлет создает новую запись для службы Windows в реестре и в базе данных службы. Для новой службы требуется исполняемый файл, который выполняется во время работы службы.

Параметры этого командлета позволяют задать отображаемое имя, описание, тип запуска и зависимости службы.

## Примеры

### Пример 1. Создание службы

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

Эта команда создает службу с именем TestService.

### Пример 2. Создание службы, включающей описание, тип запуска и отображаемое имя

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

Эта команда создает службу с именем TestService. В нем используются параметры `New-Service` для указания описания, типа запуска и отображаемого имени для новой службы.

### Пример 3. Просмотр новой службы

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

Эта команда использует `Get-CimInstance` для получения объекта **Win32_Service** для новой службы. Этот объект содержит режим запуска службы и описание службы.

### Пример 4. Настройка SecurityDescriptor службы при создании.

В этом примере добавляется **SecurityDescriptor** создаваемой службы.

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

**SecurityDescriptor** хранится в `$SDDLToSet` переменной. Параметр **SecurityDescriptorSddl** использует, `$SDDL` чтобы задать **SecurityDescriptor** для новой службы.

## PARAMETERS

### -Бинарипаснаме

Указывает путь к исполняемому файлу службы. Этот параметр обязателен.

Полный путь к двоичному файлу службы. Если путь содержит пробел, он должен быть заключен в кавычки, чтобы правильно интерпретировать его. Например, `d:\my share\myservice.exe` необходимо указать как `'"d:\my share\myservice.exe"'` .

Путь также может включать аргументы для автоматической запуска службы. Например, `'"d:\myshare\myservice.exe arg1 arg2"'`. Эти аргументы передаются в точку входа службы.

Дополнительные сведения см. в описании параметра **лпбинарипаснаме** API [креатесервицев](/windows/win32/api/winsvc/nf-winsvc-createservicew) .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).

Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя этот командлет запрашивает пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -DependsOn

Задает имена других служб, от которых зависит новая служба. Чтобы ввести несколько имен служб, разделите их запятой.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Указывает описание службы.

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

Указывает отображаемое имя службы.

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

### -Name

Указывает имя службы. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupType

Задает тип запуска службы. Допустимые значения для этого параметра:

- **Автоматически** — служба запущена или была запущена операционной системой при запуске системы.
  Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.
- **Аутоматикделайедстарт** — запускается вскоре после загрузки системы.
- **Отключено** — служба отключена и не может быть запущена пользователем или приложением.
- **Инвалидвалуе** — это значение не поддерживается. Использование этого значения приводит к ошибке.
- **Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.

 Значение по умолчанию — **Automatic**.

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
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

В этот командлет нельзя передать входные данные.

## Выходные данные

### System.ServiceProcess.ServiceController

Этот командлет возвращает объект, представляющий новую службу.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
