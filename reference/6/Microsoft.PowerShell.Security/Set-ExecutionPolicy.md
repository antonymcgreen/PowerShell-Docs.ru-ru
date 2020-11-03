---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: f8575c97c4279f285598e2b1bdf94786d92c841a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229105"
---
# Set-ExecutionPolicy

## Краткий обзор
Задает политики выполнения PowerShell для компьютеров Windows.

## SYNTAX

### Все

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-ExecutionPolicy`Командлет изменяет политики выполнения PowerShell для компьютеров Windows. Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Начиная с PowerShell 6,0 для компьютеров, отличных от Windows, политика выполнения по умолчанию не **ограничена** и не может быть изменена. `Set-ExecutionPolicy`Командлет доступен, но PowerShell отображает сообщение консоли, которое не поддерживается.

Политика выполнения является частью стратегии безопасности PowerShell. Политики выполнения определяют, можно ли загружать файлы конфигурации, например профиль PowerShell, или выполнять сценарии. И, если перед запуском скрипты должны иметь цифровую подпись.

`Set-ExecutionPolicy`По умолчанию командлет имеет область **LocalMachine** , которая влияет на всех, кто использует этот компьютер. Чтобы изменить политику выполнения для **LocalMachine** , запустите PowerShell с **запуском от имени администратора** .

Чтобы отобразить политики выполнения для каждой области в порядке приоритета, используйте `Get-ExecutionPolicy -List` . Чтобы просмотреть действующую политику выполнения для сеанса PowerShell, используйте параметр `Get-ExecutionPolicy` без параметров.

## Примеры

### Пример 1. Настройка политики выполнения

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
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** . Параметр **Scope** задает значение области по умолчанию — **LocalMachine** . Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .

### Пример 2. Настройка политики выполнения, конфликтующей с групповая политика

Эта команда пытается установить **ограничение** для политики выполнения в области **LocalMachine** .
**Хранилище LocalMachine** является более узким, но не является действующей политикой, так как она конфликтует с групповая политика. Политика **ограниченного** доступа записывается в куст реестра **HKEY_LOCAL_MACHINE** .

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

`Set-ExecutionPolicy`Командлет использует параметр **ExecutionPolicy** для указания политики **ограничения** . Параметр **Scope** задает значение области по умолчанию — **LocalMachine** .
`Get-ChildItem`Командлет использует параметр **path** с поставщиком **HKLM** для указания расположения реестра.

### Пример 3. Применение политики выполнения с удаленного компьютера к локальному компьютеру

Эта команда получает объект политики выполнения с удаленного компьютера и устанавливает политику на локальном компьютере. `Get-ExecutionPolicy` отправляет объект **Microsoft.PowerShell.Exeкутионполици** вниз по конвейеру. `Set-ExecutionPolicy` принимает входные данные конвейера и не требует параметра **ExecutionPolicy** .

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

`Invoke-Command`Командлет выполняется на локальном компьютере и отправляет **ScriptBlock** на удаленный компьютер. Параметр **ComputerName** указывает удаленный компьютер **Server01** . Параметр **ScriptBlock** выполняется `Get-ExecutionPolicy` на удаленном компьютере. `Get-ExecutionPolicy`Объект отправляется по конвейеру в `Set-ExecutionPolicy` .
`Set-ExecutionPolicy` применяет политику выполнения к области по умолчанию локального компьютера, **LocalMachine** .

### Пример 4. Задание области для политики выполнения

В этом примере показано, как задать политику выполнения для указанной области, **CurrentUser** . Область **CurrentUser** влияет только на пользователя, который устанавливает эту область.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
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

`Set-ExecutionPolicy`Задает политику **AllSigned** с помощью параметра **ExecutionPolicy** .
Параметр **Scope** указывает **CurrentUser** . Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .

Действующая политика выполнения для пользователя преобразуется в **AllSigned** .

### Пример 5. Удаление политики выполнения для текущего пользователя

В этом примере показано, как использовать **неопределенную** политику выполнения для удаления политики выполнения для указанной области.

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy` использует параметр **ExecutionPolicy** для указания **неопределенной** политики.
Параметр **Scope** указывает **CurrentUser** . Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .

### Пример 6. Настройка политики выполнения для текущего сеанса PowerShell

Область **процесса** влияет только на текущий сеанс PowerShell. Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` и удаляется при закрытии сеанса.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **AllSigned** . Параметр **Scope** задает **процесс** value. Чтобы просмотреть параметры политики выполнения, используйте `Get-ExecutionPolicy` командлет с параметром **List** .

### Пример 7. Разблокировка скрипта для его запуска без изменения политики выполнения

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

`Set-ExecutionPolicy`Использует параметр **ExecutionPolicy** для указания политики **RemoteSigned** . Политика задается для области по умолчанию, **LocalMachine** .

`Get-ExecutionPolicy`Командлет показывает, что **RemoteSigned** является действующей политикой выполнения для текущего сеанса PowerShell.

Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога. Сценарий заблокирован **RemoteSigned** , так как сценарий не имеет цифровой подписи.

В этом примере код скрипта был проверен и проверен как надежный для выполнения. `Unblock-File`Командлет использует параметр **path** , чтобы разблокировать скрипт.

Чтобы убедиться, что `Unblock-File` Политика выполнения не изменилась, `Get-ExecutionPolicy` отображает действующую политику выполнения **RemoteSigned** .

Скрипт **Start-ActivityTracker.ps1** выполняется из текущего каталога. Сценарий начинает выполняться, так как он был разблокирован `Unblock-File` командлетом.

## PARAMETERS

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

### -ExecutionPolicy

Задает политику выполнения. Если групповых политик нет, а для каждой политики выполнения каждой области задано значение **undefine** , то **ограничения** становятся действующей политикой для всех пользователей.

Допустимы следующие значения политики выполнения.

- **AllSigned** . Требует, чтобы все сценарии и файлы конфигурации подписаны доверенным издателем, включая сценарии, написанные на локальном компьютере.
- **Обход** . ничего не блокируется, и никакие предупреждения и запросы не появляются.
- **Default** . Задает политику выполнения по умолчанию. **Ограничено** для клиентов Windows или **RemoteSigned** для серверов Windows.
- **RemoteSigned** . Требует, чтобы все скрипты и файлы конфигурации, скачанные из Интернета, были подписаны доверенным издателем. Политика выполнения по умолчанию для компьютеров Windows Server.
- **Ограничено** . Не загружает файлы конфигурации или не выполняет сценарии. Политика выполнения по умолчанию клиентские компьютеры Windows.
- Не **определено** . Для области не задана политика выполнения. Удаляет назначенную политику выполнения из области, которая не задается групповая политика. Если политика выполнения во всех областях не **определена** , действующая политика выполнения **ограничена** .
- Без **ограничений** . Начиная с PowerShell 6,0 это политика выполнения по умолчанию для компьютеров, отличных от Windows, и не может быть изменена. загружает все файлы конфигурации и выполняет все скрипты. При запуске неподписанного скрипта, скачанного из Интернета, перед запуском появится запрос на разрешение.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force

Подавляет все запросы подтверждения. Будьте внимательны с этим параметром, чтобы избежать непредвиденных результатов.

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

### -Scope

Указывает область, на которую влияет политика выполнения. Областью по умолчанию является **хранилище LocalMachine** .

Действующая политика выполнения определяется порядком приоритета следующим образом.

- **Мачинеполици** . Задается групповая политика для всех пользователей компьютера.
- **UserPolicy** . Задается групповая политика для текущего пользователя компьютера.
- **Процесс** . Влияет только на текущий сеанс PowerShell.
- **CurrentUser** . Влияет только на текущего пользователя.
- **Хранилище LocalMachine** . Область по умолчанию, влияющая на всех пользователей компьютера.

Область **процесса** влияет только на текущий сеанс PowerShell. Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре. При закрытии сеанса PowerShell переменная и значение удаляются.

Политики выполнения для области **CurrentUser** записываются в куст реестра **HKEY_LOCAL_USER** .

Политики выполнения для области **LocalMachine** записываются в куст реестра **HKEY_LOCAL_MACHINE** .

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.PowerShell.ExeКутионполици, System. String

Объект политики выполнения или строку, содержащую имя политики выполнения, можно передать в `Set-ExecutionPolicy` .

## Выходные данные

### Нет

`Set-ExecutionPolicy` не возвращает никаких выходных данных.

## ПРИМЕЧАНИЯ

`Set-ExecutionPolicy` не изменяет области **мачинеполици** и **UserPolicy** , так как они задаются групповыми политиками.

`Set-ExecutionPolicy` не переопределяет групповая политика, даже если предпочтение пользователя является более узким, чем политика.

Если групповая политика **включить выполнение скрипта** для компьютера или пользователя, параметры пользователя сохраняются, но не вступают в силу. PowerShell выводит сообщение с объяснением конфликта.

## Связанные ссылки

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Unblock-File](../Microsoft.PowerShell.Utility/Unblock-File.md)
