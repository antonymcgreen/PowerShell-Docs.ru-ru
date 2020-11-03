---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227909"
---
# Reset-ComputerMachinePassword

## Краткий обзор
Сбрасывает пароль учетной записи компьютера для компьютера.

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Reset-компутермачинепассворд** изменяет пароль учетной записи компьютера, используемый компьютерами для проверки подлинности на контроллерах домена в домене.
Этот командлет можно использовать для сброса пароля локального компьютера.

## Примеры

### Пример 1. Сброс пароля для локального компьютера

```
PS C:\> Reset-ComputerMachinePassword
```

Эта команда сбрасывает пароль компьютера для локального компьютера.
Команда выполняется с использованием учетных данных текущего пользователя.

### Пример 2. Сброс пароля для локального компьютера с помощью указанного контроллера домена

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

Эта команда сбрасывает пароль компьютера локального компьютера с помощью контроллера домена DC01.
Параметр *Credential* используется для указания учетной записи пользователя, имеющей разрешение на сброс пароля компьютера в домене.

### Пример 3. Сброс пароля на удаленном компьютере

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

Эта команда использует командлет Invoke-Command для выполнения команды **Reset-компутермачинепассворд** на удаленном компьютере Server01.

Подробнее об удаленных командах в Windows PowerShell см. в разделе about_Remote, а также в разделе, посвященном командлету **Invoke-Command** .

## PARAMETERS

### -Credential
Указывает учетную запись пользователя с разрешением на выполнение этого действия.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например User01 или Domain01\User01, либо укажите объект **PSCredential** , например формируемый командлетом Get-Credential.
При вводе имени пользователя этот командлет запрашивает пароль.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Server
Указывает имя контроллера домена для использования, когда этот командлет задает пароль учетной записи компьютера.

Это необязательный параметр.
Если он не указан, команда выполняется текущим контроллером домена.

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

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

## Связанные ссылки
