---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 0b4ec4902df2b2e93def549586e3f6cde70fadee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229857"
---
# Enable-WSManCredSSP

## Краткий обзор
Включает проверку подлинности на компьютере с помощью поставщика поддержки безопасности учетных данных (CredSSP).

## SYNTAX

### Все

```
Enable-WSManCredSSP [-Role] <String> [[-DelegateComputer] <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`Enable-WSManCredSSP`Командлет включает проверку подлинности CredSSP на клиенте или на компьютере сервера.
При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности. Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса. Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.

`Enable-WSManCredSSP` может включить CredSSP на **клиенте** или на **сервере**. Чтобы включить CredSSP на клиенте, укажите **Client** в параметре **Role** . Клиенты делегируют явные учетные данные серверу при достижении проверки подлинности сервера. Чтобы включить CredSSP на сервере, укажите **Server** в параметре **Role** . Сервер выступает в качестве делегата для клиентов. Дополнительные сведения см. в статье **Role** в разделе Parameters.

> [!CAUTION]
> Проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер. Это повышает угрозу безопасности при работе в удаленном режиме. Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

## Примеры

### Пример 1. делегирование учетных данных клиента

Этот пример позволяет делегировать учетные данные клиента компьютеру с помощью полного доменного имени.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Пример 2. делегирование учетных данных клиента на все компьютеры в домене

Этот пример позволяет делегировать учетные данные клиента всем компьютерам в домене **Fabrikam.com** . `*`Подстановочный знак звездочки () задает все компьютеры.

> [!NOTE]
> Использование подстановочных знаков с параметром **DelegateComputer** может включить CredSSP на большем число компьютеров, чем требуется.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Пример 3. делегирование учетных данных клиента нескольким компьютерам

Этот пример позволяет делегировать учетные данные клиента нескольким компьютерам.

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

`$servers`Переменная содержит список имен серверов. `Enable-WSManCredSSP` использует параметр **Role** для указания роли **клиента** . **DelegateComputer** получает имена компьютеров из `$servers` переменной.

### Пример 4. разрешение компьютеру действовать в качестве делегата

Этот пример позволяет компьютеру действовать в качестве делегата для другого. `Enable-WSManCredSSP`Командлет, показанный в предыдущих примерах, включает только проверку подлинности CredSSP на клиенте и указывает удаленные компьютеры, которые могут действовать от его имени. Чтобы удаленный компьютер действовал в качестве делегата для клиента, элемент CredSSP в узле **службы** WSMan должен иметь значение true. В этом примере для элемента CredSSP в узле **службы** WSMan задается значение true.

```powershell
Enable-WSManCredSSP -Role "Server"
```

### Пример 5. разрешение компьютеру действовать в качестве делегата с помощью Set-Item

Этот пример позволяет компьютеру действовать в качестве делегата для другого компьютера. `Enable-WSManCredSSP`Команды, показанные в предыдущих примерах, включают проверку подлинности CredSSP только на клиентском компьютере и указывают удаленные компьютеры, которые могут действовать от имени клиентского компьютера. Чтобы удаленный компьютер выступал в качестве делегата для клиентского компьютера, для элемента CredSSP в каталоге Service WSMan следует установить значение true.

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

`Connect-WSMan` создает подключение к удаленному компьютеру Server02. `Set-Item` использует параметр **path** для указания расположения поставщика **WSMan** . Параметр **value** устанавливает для параметра **службы** значение true.

## PARAMETERS

### -DelegateComputer

Указывает серверы, на которые делегируются учетные данные клиента. Рекомендуется использовать полные доменные имена.

Подстановочные знаки принимаются, но могут включать CredSSP на большем количество компьютеров, чем требуется.

Если параметр **Role** имеет значение **Client** , необходимо указать этот параметр. Если **Role** — **Server** , не указывайте этот параметр.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

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

### -Role

Указывает, следует ли включить CredSSP в качестве клиента или сервера. Допустимые значения для этого параметра: **Client** и **Server**.

При указании **клиента** выполняются следующие действия. Эти параметры позволяют клиенту делегировать явные учетные данные на сервер при выполнении аутентификации сервера.

- Включает CredSSP на клиенте.
- Задает для параметра WS-Management значение `\<localhost|computername\>\Client\Auth\CredSSP` true.
- Задает для политики Windows CredSSP **AllowFreshCredentials** , алловфрешкредентиалс **WSMan/Delegate** на клиенте.

Если указан параметр **Server** , выполняются следующие действия. Этот параметр политики позволяет серверу выступать в качестве делегата для клиентов.

- Включает CredSSP на сервере.
- Задает для параметра WS-Management значение `\<localhost|computername\>\Service\Auth\CredSSP` true.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Этот командлет не принимает входные данные.

## Выходные данные

### System.Xml.XmlElement

Если проверка подлинности CredSSP успешно включена, этот командлет создает объект **XmlElement** .

## ПРИМЕЧАНИЯ

Чтобы отключить проверку подлинности CredSSP, используйте `Disable-WSManCredSSP` командлет.

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
