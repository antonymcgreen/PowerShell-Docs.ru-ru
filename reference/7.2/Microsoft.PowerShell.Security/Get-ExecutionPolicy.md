---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d6555f1abc824add4613654461106af34045e1a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602279"
---
# Get-ExecutionPolicy

## Краткий обзор
Получает политики выполнения для текущего сеанса.

## SYNTAX

### Все

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## DESCRIPTION

Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` . Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.

Действующая политика выполнения определяется политиками выполнения, которые задаются `Set-ExecutionPolicy` параметрами и групповая политика.

Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

## Примеры

### Пример 1. получение всех политик выполнения

Эта команда отображает политики выполнения для каждой области в порядке приоритета.

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

`Get-ExecutionPolicy`Командлет использует параметр **List** для вывода политики выполнения каждой области.

### Пример 2. Настройка политики выполнения

В этом примере показано, как задать политику выполнения для локального компьютера.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** . Параметр **Scope** задает значение области по умолчанию — **LocalMachine**. Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .

### Пример 3. получение действующей политики выполнения

В этом примере показано, как отобразить действующую политику выполнения для сеанса PowerShell.

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

`Get-ExecutionPolicy`Командлет использует параметр **List** для вывода политики выполнения каждой области. `Get-ExecutionPolicy`Командлет выполняется без параметра для вывода действующей политики выполнения **AllSigned**.

### Пример 4. Разблокировка скрипта для его запуска без изменения политики выполнения

В этом примере показано, как политика выполнения **RemoteSigned** не позволяет выполнять неподписанные сценарии.

**Перед** использованием командлета рекомендуется прочитать код скрипта и проверить его безопасность `Unblock-File` . `Unblock-File`Командлет разблокирует скрипты для их запуска, но не изменяет политику выполнения.

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** . Политика задается для области по умолчанию, **LocalMachine**.

`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.

Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога. Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.

В этом примере код скрипта был проверен и проверен как надежный для выполнения. `Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.

Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned**.

Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога. Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.

## PARAMETERS

### -List

Получает все значения политики выполнения для сеанса, перечисленные в порядке приоритетности, По умолчанию `Get-ExecutionPolicy` получает только действующую политику выполнения.

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

### -Scope

Указывает область, на которую влияет политика выполнения.

Действующая политика выполнения определяется порядком приоритета следующим образом.

- **Мачинеполици**. Задается групповая политика для всех пользователей компьютера.
- **UserPolicy**. Задается групповая политика для текущего пользователя компьютера.
- **Процесс**. Влияет только на текущий сеанс PowerShell.
- **CurrentUser**. Влияет только на текущего пользователя.
- **Хранилище LocalMachine**. Область по умолчанию, влияющая на всех пользователей компьютера.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

`Get-ExecutionPolicy` не принимает входные данные из конвейера.

## Выходные данные

### Microsoft.PowerShell.ExecutionPolicy

Командлет всегда возвращает **неограниченное** значение на платформах Linux и macOS.

## ПРИМЕЧАНИЯ

Политика выполнения является частью стратегии безопасности PowerShell. Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии. И, если перед запуском скрипты должны иметь цифровую подпись.

## Связанные ссылки

[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)
