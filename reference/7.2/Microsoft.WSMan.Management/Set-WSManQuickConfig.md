---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e5d50af0551a183b8e9e1995fbd722c331a48486
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602695"
---
# Set-WSManQuickConfig

## Краткий обзор
Настраивает локальный компьютер для удаленного управления.

## SYNTAX

### Все

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## DESCRIPTION

`Set-WSManQuickConfig`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии веб-служб для управления (WS-Management).

Подпрограмма`Set-WSManQuickConfig` выполняет следующие действия:

- Проверяет, запущена ли служба WinRM. Если служба WinRM не запущена, служба запускается.
- Задает автоматический тип запуска службы WinRM.
- Создает прослушиватель для приема запросов по любому IP-адресу. Транспортом по умолчанию является **http**.
- Включает исключение брандмауэра для трафика WinRM.

Для запуска запустите `Set-WSManQuickConfig` PowerShell с параметром **Запуск от имени администратора** .

## Примеры

### Пример 1. Включение удаленного управления локальным компьютером по протоколу HTTP

В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером. По умолчанию эта команда создает прослушиватель WS-Management на **http**.

```powershell
Set-WSManQuickConfig
```

### Пример 2. Включение удаленного управления локальным компьютером по протоколу HTTPS

В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером. Параметр **UseSSL** указывает, что **протокол HTTPS** используется для взаимодействия с компьютером.

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> Для **HTTPS** требуется ручная настройка. Дополнительные сведения см. в описании параметра **UseSSL** .

## PARAMETERS

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

### -SkipNetworkProfileCheck

Настраивает клиентские версии Windows для удаленного взаимодействия, когда компьютер находится в общедоступной сети. Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.

Этот параметр не влияет на серверные версии Windows, по умолчанию имеющий правило брандмауэра локальной подсети для общедоступных сетей. Если правило брандмауэра на локальной подсети отключено на серверной версии Windows, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.

Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .

Этот параметр появился в PowerShell 3,0.

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

### -UseSSL

Указывает, что для подключения к удаленному компьютеру используется протокол SSL. По умолчанию протокол SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети. Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP. Если вы используете этот параметр и протокол SSL недоступен в порте, используемом для подключения, команда завершается ошибкой.

Для **HTTPS** требуется ручная настройка WinRM и правил брандмауэра. Дополнительные сведения см. [в разделе инструкции. Настройка WINRM для HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

Этот командлет не принимает входные данные.

## Выходные данные

### None

Этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-PSRemoting](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Как настроить WINRM для HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Test-WSMan](Test-WSMan.md)

