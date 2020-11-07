---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 2fc21594a4765a0901f61dba7b7f1a79f3259886
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346145"
---
# Rename-Computer

## Краткий обзор
Переименовывает компьютер.

## SYNTAX

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Rename-Computer`Командлет переименовывает локальный компьютер или удаленный компьютер.
Он переименовывает один компьютер в каждой команде.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Переименование локального компьютера

Эта команда переименовывает локальный компьютер в `Server044` , а затем перезапускает его, чтобы сделать изменение эффективным.

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### Пример 2. Переименование удаленного компьютера

Эта команда переименовывает `Srv01` компьютер в `Server001` . Компьютер не перезагружается.

Параметр **домаинкредентиал** указывает учетные данные пользователя, имеющего разрешение на переименование компьютеров в домене.

Параметр **Force** подавляет вывод запроса на подтверждение.

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## PARAMETERS

### -ComputerName

Переименовывает указанный удаленный компьютер.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или `localhost` .

Этот параметр не зависит от удаленного взаимодействия PowerShell.
Параметр **ComputerName** можно использовать, `Rename-Computer` даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Домаинкредентиал

Указывает учетную запись пользователя, имеющую разрешение на подключение к домену.
Для переименования компьютера, присоединенного к домену, необходимо явно указать учетные данные.

Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.

При вводе имени пользователя этот командлет запрашивает пароль.

Чтобы указать учетную запись пользователя, имеющую разрешение на подключение к компьютеру, который задается параметром **ComputerName** , используйте параметр **LocalCredential**.

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

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

### -Локалкредентиал

Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютеру, заданному параметром **ComputerName**. По умолчанию используется текущий пользователь.

Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.

При вводе имени пользователя этот командлет запрашивает пароль.

Чтобы указать учетную запись, имеющую разрешение на подключение к домену, используйте параметр **DomainCredential**.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName

Задает новое имя для компьютера.
Этот параметр обязателен.

Стандартные имена могут содержать буквы ( `a-z` ), ( `A-Z` ), цифры ( `0-9` ) и дефисы ( `-` ), но без пробелов и точек ( `.` ). Имя не может состоять только из цифр и может содержать не более 63 символов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает результаты выполнения команды.
В противном случае командлет не формирует никаких выходных данных.

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

### -Restart

Указывает, что этот командлет перезапускает переименованный компьютер.
Чтобы изменения вступили в силу, часто требуется перезагрузка.

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

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan. Допустимые значения для этого параметра:

- **Основной**
- **CredSSP**
- **Default**
- **Digest** (дайджест)
- **Kerberos**
- **Новое**

Значение по умолчанию ― **Default**.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.
> Этот механизм повышает риск безопасности удаленной операции.
> Если удаленный компьютер скомпрометирован, передаваемые ему учетные данные можно использовать для управления > сетевого сеанса.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Этот командлет не имеет параметров, которые принимают входные данные по значению. Тем не менее в этот командлет можно передавать значения свойств **ComputerName** и **NewName** объектов.

## Выходные данные

### Microsoft. PowerShell. Commands. Компутерчанжеинфо

Этот командлет возвращает объект **компутерчанжеинфо** , если указан параметр **PassThru** .
В противном случае не возвращает никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
