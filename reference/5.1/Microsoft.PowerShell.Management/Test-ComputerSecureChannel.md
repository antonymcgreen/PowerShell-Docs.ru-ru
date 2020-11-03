---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227837"
---
# Test-ComputerSecureChannel

## Краткий обзор
Тестирует и восстанавливает безопасный канал между локальным компьютером и его доменом.

## SYNTAX

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Test-ComputerSecureChannel** проверяет, правильно ли работает канал между локальным компьютером и его доменом. Для этого он проверяет состояние отношений доверия.
В случае сбоя подключения можно использовать параметр *Repair* , чтобы попытаться восстановить его.

Командлет **Test-ComputerSecureChannel** возвращает значение $True, если канал работает правильно, и $False в противном случае.
Это позволяет использовать его в условных операторах в функциях и сценариях.
Чтобы получить более подробные результаты теста, используйте параметр *verbose* .

Этот командлет работает во многом так же, как программа NetDom.exe.
Как NetDom, так и **Test-ComputerSecureChannel** используют службу **Netlogon** для выполнения действий.

## Примеры

### Пример 1. Тестирование канала между локальным компьютером и его доменом

```
PS C:\> Test-ComputerSecureChannel
True
```

Эта команда проверяет канал между локальным компьютером и доменом, в который он входит.

### Пример 2. Тестирование канала между локальным компьютером и контроллером домена

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

Эта команда задает предпочтительный контроллер домена для проверки.

### Пример 3. Тестирование канала между локальным компьютером и его доменом

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

Эта команда переустанавливает канал между локальным компьютером и его доменом.

### Пример 4. Отображение подробных сведений о тесте

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

Эта команда использует параметр *verbose* Common для запроса подробных сообщений об операции.
Сведения о параметре *Verbose* см. в разделе about_CommonParameters.

### Пример 5. Проверка подключения, перед тем как выполнить скрипт

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

В этом примере показано, как использовать командлет **Test-ComputerSecureChannel** для проверки подключения перед выполнением скрипта, которому оно требуется.

В первой команде используется командлет Set-Alias с целью создания псевдонима для имени командлета.
Это позволяет сэкономить место и избежать ошибок при вводе.

Оператор **If** проверяет значение, возвращенное командлетом **Test-ComputerSecureChannel** , перед выполнением скрипта.

## PARAMETERS

### -Credential
Указывает учетную запись пользователя с разрешением на выполнение этого действия.
Введите имя пользователя, например User01, Domain01\User01, либо укажите объект **PSCredential** , например возвращаемый командлетом Get-Credential.
По умолчанию командлет использует учетные данные текущего пользователя.

Параметр *Credential* предназначен для использования в командах, которые используют параметр *Repair* для восстановления канала между компьютером и доменом.

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

### -Repair
Указывает, что этот командлет удаляет и повторно создает канал, установленный службой NetLogon.
Используйте этот параметр, чтобы попытаться восстановить подключение, которое не прошло проверку.

Для использования этого параметра текущий пользователь должен быть участником группы "Администраторы" на локальном компьютере.

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

### -Server
Указывает контроллер домена для выполнения команды.
Если этот параметр не указан, командлет выбирает контроллер домена по умолчанию.

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

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System.Boolean
Этот командлет возвращает значение $True, если подключение работает правильно, и значение $False в противном случае.

## ПРИМЕЧАНИЯ

* Чтобы выполнить команду **Test-ComputerSecureChannel** в Windows Vista и более поздних версиях операционной системы Windows, откройте среду Windows PowerShell, используя параметр "Запуск от имени администратора".
* Командлет **Test-ComputerSecureChannel** реализован с помощью функции **I_NetLogonControl2** , которая контролирует различные аспекты службы Netlogon.

## Связанные ссылки

[Checkpoint-Computer](Checkpoint-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
