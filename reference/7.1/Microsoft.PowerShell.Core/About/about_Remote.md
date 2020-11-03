---
description: Описание выполнения удаленных команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: d88521eeb2a5a4cd1f7d9e6303b4814b5a1c0bb6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231665"
---
# <a name="about-remote"></a>Об удаленной

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описание выполнения удаленных команд в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Удаленные команды можно выполнять на одном компьютере или на нескольких компьютерах, используя временное или постоянное подключение. Можно также запустить интерактивный сеанс с одним удаленным компьютером.

В этом разделе приводится ряд примеров, демонстрирующих выполнение различных типов удаленных команд. После выполнения этих основных команд ознакомьтесь с разделами справки, описывающими каждый командлет, используемый в этих командах. В этих разделах содержатся сведения и объясняется, как можно изменить команды в соответствии с вашими потребностями.

Примечание. чтобы использовать удаленное взаимодействие PowerShell, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие. Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).

## <a name="how-to-start-an-interactive-session-enter-pssession"></a>КАК ЗАПУСТИТЬ ИНТЕРАКТИВНЫЙ СЕАНС (ENTER-PSSESSION)

Самый простой способ запуска удаленных команд — запустить интерактивный сеанс с удаленным компьютером.

При запуске сеанса команды, которые вы вводите, выполняются на удаленном компьютере, точно так же, как если бы они были введены непосредственно на удаленном компьютере. В каждом интерактивном сеансе можно подключиться только к одному компьютеру.

Чтобы запустить интерактивный сеанс, используйте командлет Enter-PSSession. Следующая команда запускает интерактивный сеанс с компьютером Server01:

```powershell
Enter-PSSession Server01
```

Командная строка изменится, указывая, что вы подключены к компьютеру Server01.

```
Server01\PS>
```

Теперь можно ввести команды на компьютере Server01.

Чтобы завершить интерактивный сеанс, введите:

```powershell
Exit-PSSession
```

Дополнительные сведения см. в разделе Ввод-PSSession.

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a>ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТОВ С ПАРАМЕТРОМ COMPUTERNAME ДЛЯ ПОЛУЧЕНИЯ УДАЛЕННЫХ ДАННЫХ

Несколько командлетов имеют параметр ComputerName, позволяющий получать объекты с удаленных компьютеров.

Поскольку эти командлеты не используют удаленное взаимодействие PowerShell на основе WS-Management, можно использовать параметр ComputerName этих командлетов на любом компьютере с PowerShell. Компьютеры не обязательно должны быть настроены для удаленного взаимодействия PowerShell, и компьютеры не должны отвечать требованиям к системе для удаленного взаимодействия.

Следующие командлеты имеют параметр ComputerName:

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

Например, следующая команда получает службы на удаленном компьютере Server01:

```powershell
Get-Service -ComputerName Server01
```

Как правило, командлеты, поддерживающие удаленное взаимодействие без специальной настройки, имеют параметр **ComputerName** и не имеют параметра **сеанса** . Чтобы найти эти командлеты в сеансе, введите:

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a>ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ

Чтобы выполнить другие команды на удаленных компьютерах, используйте командлет Invoke-Command.

Чтобы выполнить одну команду или несколько несвязанных команд, используйте параметр ComputerName параметра Invoke-Command, чтобы указать удаленные компьютеры. Используйте параметр ScriptBlock для указания команды.

Например, следующая команда выполняет команду Get-Culture на компьютере Server01.

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

Параметр ComputerName предназначен для ситуации, когда на одном или нескольких компьютерах выполняется одна команда или несколько несвязанных команд. Чтобы установить постоянное подключение к удаленному компьютеру, используйте параметр Session.

## <a name="how-to-create-a-persistent-connection-pssession"></a>СОЗДАНИЕ ПОСТОЯННОГО ПОДКЛЮЧЕНИЯ (PSSESSION)

При использовании параметра ComputerName командлета Invoke-Command Windows PowerShell устанавливает соединение только для команды. Затем по завершении команды она закрывает подключение. Все переменные или функции, определенные в команде, теряются.

Чтобы создать постоянное подключение к удаленному компьютеру, используйте командлет New-PSSession. Например, следующая команда создает PSSession на компьютерах Server01 и Server02, а затем сохраняет PSSession в переменной $s.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a>ВЫПОЛНЕНИЕ КОМАНД В PSSESSION

С помощью PSSession можно выполнять ряд удаленных команд, которые совместно используют данные, такие как функции, псевдонимы и значения переменных. Для выполнения команд в PSSession используйте параметр Session командлета Invoke-Command.

Например, следующая команда использует командлет Invoke-Command для выполнения команды Get-Process в PSSession на компьютерах Server01 и Server02.
Команда сохраняет процессы в переменной $p в каждом сеансе PSSession.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

Так как сеанс PSSession использует постоянное подключение, можно выполнить другую команду в том же сеансе PSSession, который использует переменную $p. Следующая команда подсчитывает количество процессов, сохраненных в $p.

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a>ВЫПОЛНЕНИЕ УДАЛЕННОЙ КОМАНДЫ НА НЕСКОЛЬКИХ КОМПЬЮТЕРАХ

Чтобы выполнить удаленную команду на нескольких компьютерах, введите все имена компьютеров в значении параметра ComputerName команды Invoke-Command. Разделяйте имена запятыми.

Например, следующая команда выполняет команду Get-Culture на трех компьютерах:

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

Можно также выполнить команду в нескольких PSSession. Следующие команды создают PSSession на компьютерах Server01, Server02 и Server03, а затем выполняют Get-Cultureную команду в каждом из PSSession.

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

Чтобы включить список компьютеров локального компьютера, введите имя локального компьютера, введите точку (.) или введите localhost.

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a>ЗАПУСК СЦЕНАРИЯ НА УДАЛЕННЫХ КОМПЬЮТЕРАХ

Чтобы запустить локальный скрипт на удаленных компьютерах, используйте параметр FilePath командлета Invoke-Command.

Например, следующая команда запускает сценарий Sample.ps1 на компьютерах S1 и S2:

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

Результаты сценария возвращаются на локальный компьютер. Нет необходимости копировать файлы.

## <a name="how-to-stop-a-remote-command"></a>КАК ПРЕРЫВАТЬ УДАЛЕННУЮ КОМАНДУ

Чтобы прервать выполнение команды, нажмите клавиши CTRL + C. Запрос на прерывание передается на удаленный компьютер, на котором завершается Удаленная команда.

## <a name="for-more-information"></a>ДОПОЛНИТЕЛЬНЫЕ СВЕДЕНИЯ

- Сведения о требованиях к системе для удаленного взаимодействия см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).

- Справку по форматированию удаленных выходных данных см. в разделе [about_Remote_Output](about_Remote_Output.md).

- Сведения о принципах работы удаленного взаимодействия, об управлении удаленными данными, специальных конфигурациях, проблемах безопасности и других часто задаваемых вопросах см. в разделе [about_Remote_FAQ](about_Remote_FAQ.md).

- Дополнительные сведения об устранении ошибок удаленного взаимодействия см. в разделе about_Remote_Troubleshooting.

- Дополнительные сведения о PSSession и постоянных подключениях см. в разделе [about_PSSessions](about_PSSessions.md).

- Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](about_Jobs.md).

## <a name="keywords"></a>СЛОВАМИ

about_Remoting

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_PSSessions](about_PSSessions.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_FAQ](about_Remote_FAQ.md)

[about_Remote_TroubleShooting](about_Remote_TroubleShooting.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

