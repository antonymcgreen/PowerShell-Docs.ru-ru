---
title: Новые возможности PowerShell Core 6.1
description: Новые возможности и изменения в PowerShell Core 6.1
ms.date: 09/13/2018
ms.openlocfilehash: 7a50bc3a909df38d21a604399d590a2805359593
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837550"
---
# <a name="whats-new-in-powershell-core-61"></a>Новые возможности PowerShell Core 6.1

Ниже указаны некоторые основные новые функции и изменения, которые были введены в PowerShell Core 6.1.

Кроме того, доступно **множество** добавлений, позволяющих повысить быстродействие и стабильность PowerShell (а также целый ряд исправлений ошибок). Полный список изменений см. в нашем [журнале изменений на сайте GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).

Несмотря на то что далее мы называем лишь часть имен, мы выражаем благодарность [всем участникам сообщества](https://github.com/PowerShell/PowerShell/graphs/contributors), которые внесли свой вклад в этот выпуск.

## <a name="net-core-21"></a>.NET Core 2.1

После [выпуска в мае](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) среда PowerShell Core 6.1 перемещена на .NET Core 2.1, что привело к ряду улучшений в PowerShell, включая:

- повышение производительности (см. [ниже](#performance-improvements));
- поддержку Alpine Linux (предварительная версия);
- [поддержку глобального средства .NET](/dotnet/core/tools/global-tools) — выходит в ближайшее время в PowerShell.
- [`Span<T>`](/dotnet/api/system.span-1?view=netcore-2.1)

## <a name="windows-compatibility-pack-for-net-core"></a>Пакет обеспечения совместимости Windows для .NET Core

Команда разработчиков .NET добавила [пакет обеспечения совместимости Windows для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/11/16/announcing-the-windows-compatibility-pack-for-net-core/) — набор сборок, которые добавляют несколько удаленных API-интерфейсов обратно в .NET Core в Windows.

Мы добавили пакет обеспечения совместимости Windows в выпуск PowerShell Core 6.1, чтобы сделать доступными все модули или сценарии, использующие эти API-интерфейсы.

Благодаря пакету обеспечения совместимости Windows в PowerShell Core можно использовать **более 1900 командлетов, входящих в состав обновления Windows от 10 октября 2018 г. и Windows Server 2019**.

## <a name="support-for-application-allow-lists"></a>Поддержка списков разрешенных приложений

В PowerShell Core 6.1 реализована та же поддержка, что и в Windows PowerShell 5.1, которая позволяет добавлять приложения в список разрешенных в [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) и [Device Guard](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control). Добавление приложений в список разрешенных обеспечивает более детализированное управление двоичными файлами, которые могут выполняться с помощью [ограниченного языкового режима](https://blogs.msdn.microsoft.com/powershell/2017/11/02/powershell-constrained-language-mode/) PowerShell.

## <a name="performance-improvements"></a>Повышение производительности

В PowerShell Core 6.0 внесены значительные усовершенствования производительности. PowerShell Core 6.1 и далее повышает скорость выполнения определенных операций.

Например, скорость выполнения `Group-Object` была увеличена до 66 %.

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Group-Object }
```

|              | Windows PowerShell 5.1 | PowerShell Core 6.0 | PowerShell Core 6.1 |
|--------------|------------------------|---------------------|---------------------|
| Время (с)   | 25,178                 | 19,653              | 6,641               |
| Ускорение (%) | Недоступно                    | 21,9 %               | 66,2 %               |

Аналогично, более чем на 15 % улучшена производительность сценариев сортировки следующего вида.

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Sort-Object }
```

|              | Windows PowerShell 5.1 | PowerShell Core 6.0 | PowerShell Core 6.1 |
|--------------|------------------------|---------------------|---------------------|
| Время (с)   | 12,170                 | 8,493               | 7,08                |
| Ускорение (%) | Недоступно                    | 30,2 %               | 16,6 %               |

После регрессии из Windows PowerShell также было значительно ускорено выполнение `Import-Csv`.
В следующем примере используется тестовый CSV-файл с 26 616 строками и шестью столбцами.

```powershell
Measure-Command {$a = Import-Csv foo.csv}
```

|              | Windows PowerShell 5.1 | PowerShell Core 6.0 | PowerShell Core 6.1    |
|--------------|------------------------|---------------------|------------------------|
| Время (с)   | 0,441                  | 1,069               | 0,268                  |
| Ускорение (%) | Недоступно                    | –142,4 %             | 74,9 % (39,2 % в WPS) |

Наконец, преобразование из формата JSON в `PSObject` было ускорено более чем на 50 % по сравнению с Windows PowerShell.
В следующем примере используется тестовый JSON-файл размером около 2 МБ.

```powershell
Measure-Command {Get-Content .\foo.json | ConvertFrom-Json}
```

|              | Windows PowerShell 5.1 | PowerShell Core 6.0 | PowerShell Core 6.1    |
|--------------|------------------------|---------------------|------------------------|
| Время (с)   | 0,259                  | 0,577               | 0.125                  |
| Ускорение (%) | Недоступно                    | –122,8 %             | 78,3 % (51,7 % в WPS) |

## <a name="check-system32-for-compatible-built-in-modules-on-windows"></a>Проверка `system32` на наличие совместимых встроенных модулей в Windows

В обновлении 1809 Windows 10 и Windows Server 2019 мы обновили несколько встроенных модулей PowerShell, и теперь они могут помечаться как совместимые с PowerShell Core.

При запуске PowerShell Core 6.1 будет автоматически включать `$windir\System32` как часть переменной среды `PSModulePath`. Однако она предоставляет модули в `Get-Module` и `Import-Module`, только если `CompatiblePSEdition` помечен как совместимый с `Core`.

```powershell
Get-Module -ListAvailable
```

> [!NOTE]
> В зависимости от установленных ролей и компонентов будут доступны самые разные модули.

```Output
...
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, Get-AppxPackage, Get-AppxPacka...
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, Suspend-BitLocker, Resume-Bit...
Manifest   1.0.0.0    DnsClient                           Core,Desk {Resolve-DnsName, Clear-DnsClientCache, Get-DnsC...
Manifest   1.0.0.0    HgsDiagnostics                      Core,Desk {New-HgsTraceTarget, Get-HgsTrace, Get-HgsTraceF...
Binary     2.0.0.0    Hyper-V                             Core,Desk {Add-VMAssignableDevice, Add-VMDvdDrive, Add-VMF...
Binary     1.1        Hyper-V                             Core,Desk {Add-VMDvdDrive, Add-VMFibreChannelHba, Add-VMHa...
Manifest   2.0.0.0    NetAdapter                          Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetEventPacketCapture               Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                             Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                              Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                              Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                         Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam                       Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetWNV                              Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   2.0.0.0    TrustedPlatformModule               Core,Desk {Get-Tpm, Initialize-Tpm, Clear-Tpm, Unblock-Tpm...
...
```

С помощью параметра `-SkipEditionCheck` это поведение можно переопределить для отображения всех модулей.
Мы также добавили свойство `PSEdition` в выходные данные таблицы.

```powershell
Get-Module Net* -ListAvailable -SkipEditionCheck
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                        PSEdition ExportedCommands
---------- -------    ----                        --------- ----------------
Manifest   2.0.0.0    NetAdapter                  Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetConnection               Core,Desk {Get-NetConnectionProfile, Set-NetConnectionProf...
Manifest   1.0.0.0    NetDiagnostics              Desk      Get-NetView
Manifest   1.0.0.0    NetEventPacketCapture       Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                     Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                      Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                      Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                 Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam               Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetTCPIP                    Core,Desk {Get-NetIPAddress, Get-NetIPInterface, Get-NetIP...
Manifest   1.0.0.0    NetWNV                      Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   1.0.0.0    NetworkConnectivityStatus   Core,Desk {Get-DAConnectionStatus, Get-NCSIPolicyConfigura...
Manifest   1.0.0.0    NetworkSwitchManager        Core,Desk {Disable-NetworkSwitchEthernetPort, Enable-Netwo...
Manifest   1.0.0.0    NetworkTransition           Core,Desk {Add-NetIPHttpsCertBinding, Disable-NetDnsTransi...
```

Дополнительные сведения об этом поведении см. в [PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md).

## <a name="markdown-cmdlets-and-rendering"></a>Командлеты и отрисовка Markdown

Markdown — это стандарт для создания документов с читаемым открытым текстом с базовым форматированием, которое может отображаться в формате HTML.

Мы добавили в версию 6.1 несколько командлетов, которые позволяют преобразовывать и отображать документы Markdown.

- `ConvertFrom-Markdown`
- `Get-MarkdownOption`
- `Set-MarkdownOption`
- `Show-Markdown`

Например, `Show-Markdown` отрисовывает файл Markdown в консоли.

![Пример Show-Markdown](media/What-s-New-in-PowerShell-Core-61/markdown_example.png)

Дополнительные сведения об использовании этих командлетов см. в [этом документе RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md).

## <a name="experimental-feature-flags"></a>Флаги экспериментальных функций

Мы включили поддержку [Экспериментальные возможности][]. Это позволяет разработчикам PowerShell предлагать новые функций и получать отзывы до завершения разработки новой версии. Благодаря этому мы можем не вносить критические изменения пока версия разрабатывается.

Используйте командлет `Get-ExperimentalFeature`, чтобы получить список доступных экспериментальных возможностей. Их можно включить и отключить с помощью `Enable-ExperimentalFeature` и `Disable-ExperimentalFeature` соответственно.

Дополнительные сведения об этой функции см. в [PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md).

## <a name="web-cmdlet-improvements"></a>Усовершенствования веб-командлетов

Выражаем благодарность [@markekraus](https://github.com/markekraus) за улучшения, внесенные в веб-командлеты: [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)
и [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod).

- [PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) — по умолчанию задана кодировка UTF-8 для ответов `application-json`
- [PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - — параметр `-SkipHeaderValidation`, позволяющий использовать заголовки `Content-Type`, которые не соответствуют стандартам
- [PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - — параметр `Form` для упрощенной поддержки `multipart/form-data`
- [PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) — соответствующая, не учитывающая регистр обработка ключей отношения
- [PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) — добавление параметра `-Resume` для веб-командлетов

## <a name="remoting-improvements"></a>Усовершенствования удаленного взаимодействия

### <a name="powershell-direct-for-containers-tries-to-use-powershell-core-first"></a>PowerShell Direct для контейнеров сначала пытается использовать PowerShell Core

[PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) входит в состав PowerShell и Hyper-V и позволяет подключаться к виртуальной машине Hyper-V или контейнеру без сетевого соединения или других служб удаленного управления PowerShell.

В прошлом для подключения PowerShell Direct использовался встроенный экземпляр Windows PowerShell в контейнере. Теперь PowerShell Direct сначала пытается подключиться с помощью любого доступного `pwsh.exe` в переменной среды`PATH`. Если `pwsh.exe` недоступен, PowerShell Direct переключается на использование `powershell.exe`.

### <a name="enable-psremoting-now-creates-separate-remoting-endpoints-for-preview-versions"></a>`Enable-PSRemoting` теперь создает отдельные конечные точки удаленного взаимодействия для предварительных версий

`Enable-PSRemoting` теперь создает две конфигурации сеанса удаленного взаимодействия.

- Одна для основного номера версии PowerShell. Например, `PowerShell.6`. Эта конечная точка может быть основной в обновлениях дополнительного номера версии как конфигурация сеанса PowerShell 6 на уровне системы.
- Одна конфигурация сеанса для конкретной версии, например: `PowerShell.6.1.0`

Это полезно, если вы хотите, чтобы на одном компьютере было установлено и доступно несколько версий PowerShell 6.

Кроме того, теперь в предварительных версиях PowerShell доступны собственные конфигурации сеанса удаленного взаимодействия после выполнения командлета `Enable-PSRemoting`.

```powershell
C:\WINDOWS\system32> Enable-PSRemoting
```

Если вы еще не настроили WinRM, выходные данные могут отличаться.

```Output
WinRM is already set up to receive requests on this computer.
WinRM is already set up for remote management on this computer.
```

Затем вы увидите отдельные конфигурации сеанса PowerShell для предварительных и стабильных сборок PowerShell 6, а также для каждой конкретной версии.

```powershell
Get-PSSessionConfiguration
```

```Output
Name          : PowerShell.6.2-preview.1
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6-preview
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6.1.0
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

### <a name="userhostport-syntax-supported-for-ssh"></a>Синтаксис `user@host:port`, поддерживаемый для SSH

SSH-клиенты обычно поддерживают строки подключения в формате `user@host:port`. С появлением SSH как протокола для удаленного взаимодействия PowerShell мы добавили поддержку этого формата строки подключения.

`Enter-PSSession -HostName fooUser@ssh.contoso.com:2222`

## <a name="msi-option-to-add-explorer-shell-context-menu-on-windows"></a>Параметр MSI для добавления контекстного меню оболочки Проводника в Windows

Выражаем благодарность [@bergmeister](https://github.com/bergmeister), так как теперь можно включать контекстное меню в Windows. Вы можете открыть системную установку PowerShell 6.1 из любой папки в Проводнике Windows.

![Контекстное меню оболочки для PowerShell 6](media/What-s-New-in-PowerShell-Core-61/shell_context_menu.png)

## <a name="goodies"></a>Полезные возможности

### <a name="run-as-administrator-in-the-windows-shortcut-jump-list"></a>"Запуск от имени администратора" в списке переходов в Windows

Выражаем благодарность [@bergmeister](https://github.com/bergmeister), так как теперь список переходов ярлыка PowerShell Core содержит возможность "Запуск от имени администратора".

!["Запуск от имени администратора" в списке переходов PowerShell 6](media/What-s-New-in-PowerShell-Core-61/jumplist.png)

### <a name="cd---returns-to-previous-directory"></a>`cd -` возвращается в предыдущий каталог

```powershell
C:\Windows\System32> cd C:\
C:\> cd -
C:\Windows\System32>
```

Или в Linux

```ShellSession
PS /etc> cd /usr/bin
PS /usr/bin> cd -
PS /etc>
```

Кроме того, `cd` и `cd --` изменяются на `$HOME`.

### `Test-Connection`

Выражаем благодарность [@iSazonov](https://github.com/iSazonov) за перенос командлета [`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) в PowerShell Core.

### <a name="update-help-as-non-admin"></a>Запуск `Update-Help` без прав администратора

По многочисленным просьбам `Update-Help` больше не требуется запускать от имени администратора. Теперь `Update-Help` по умолчанию сохраняет справку в папку пользователя.

### <a name="new-methodsproperties-on-pscustomobject"></a>Новые методы и свойства в `PSCustomObject`

Благодаря [@iSazonov](https://github.com/iSazonov) мы добавили новые методы и свойства в `PSCustomObject`. `PSCustomObject` теперь включает свойство `Count`/`Length`, как и другие объекты.

```powershell
$PSCustomObject = [pscustomobject]@{foo = 1}

$PSCustomObject.Length
```

```Output
1
```

```powershell
$PSCustomObject.Count
```

```Output
1
```

Здесь также используются методы `ForEach` и `Where` методы, которые позволяют работать с элементами `PSCustomObject` и фильтровать их.

```powershell
$PSCustomObject.ForEach({$_.foo + 1})
```

```Output
2
```

```powershell
$PSCustomObject.Where({$_.foo -gt 0})
```

```Output
foo
---
  1
```

### `Where-Object -Not`

Благодаря @SimonWahlin мы добавили параметр `-Not` в `Where-Object`. Теперь вы можете отфильтровать объект в конвейере для получения отсутствия свойства или нулевого и пустого значения свойства.

Например, эта команда возвращает все службы, у которых нет зависимых служб.

```powershell
Get-Service | Where-Object -Not DependentServices
```

### <a name="new-modulemanifest-creates-a-bom-less-utf-8-document"></a>`New-ModuleManifest` создает документ в UTF-8 без BOM

Учитывая наш переход на UTF-8 без BOM в PowerShell 6.0, мы обновили командлет `New-ModuleManifest`, чтобы вместо документа в UTF-16 создавать документ в UTF-8 без BOM.

### <a name="conversions-from-psmethod-to-delegate"></a>Преобразования из PSMethod в делегат

Выражаем благодарность [@powercode](https://github.com/powercode), так как теперь поддерживается преобразование `PSMethod` в делегат. Это позволяет выполнять такие действия, как передача `PSMethod` `[M]::DoubleStrLen` в виде значения делегата в `[M]::AggregateString`.

```powershell
class M {
    static [int] DoubleStrLen([string] $value) { return 2 * $value.Length }

    static [long] AggregateString([string[]] $values, [func[string, int]] $selector) {
        [long] $res = 0
        foreach($s in $values){
            $res += $selector.Invoke($s)
        }
        return $res
    }
}

[M]::AggregateString((gci).Name, [M]::DoubleStrLen)
```

Дополнительные сведения об этом изменении см. в [PR #5287](https://github.com/PowerShell/PowerShell/pull/5287).

### <a name="standard-deviation-in-measure-object"></a>Стандартное отклонение в `Measure-Object`

Благодаря [@CloudyDino](https://github.com/CloudyDino) мы добавили свойство `StandardDeviation` в `Measure-Object`.

```powershell
Get-Process | Measure-Object -Property CPU -AllStats
```

```Output
Count             : 308
Average           : 31.3720576298701
Sum               : 9662.59375
Maximum           : 4416.046875
Minimum           :
StandardDeviation : 264.389544720926
Property          : CPU
```

### `GetPfxCertificate -Password`

Выражаем благодарность [@maybe-hello-world](https://github.com/maybe-hello-world), так как `Get-PfxCertificate` теперь имеет `Password` параметр, который принимает `SecureString`. Это позволяет вам использовать его не интерактивно.

```powershell
$certFile = '\\server\share\pwd-protected.pfx'
$certPass = Read-Host -AsSecureString -Prompt 'Enter the password for certificate: '

$certThumbPrint = (Get-PfxCertificate -FilePath $certFile -Password $certPass ).ThumbPrint
```

### <a name="removal-of-the-more-function"></a>Удаление функции `more`

Раньше в состав PowerShell входила функция Windows `more`, которая упаковывала `more.com`. Сейчас эта функция удалена.

Кроме того, функция `help` теперь использует команду `more.com` в Windows или системную команду просмотра по умолчанию, определяемую `$env:PAGER`, на других платформах.

### <a name="cd-drivename-now-returns-users-to-the-current-working-directory-in-that-drive"></a>Теперь `cd DriveName:` возвращает пользователей в текущий рабочий каталог на этом диске

Раньше при использовании `Set-Location` или `cd` для возврата на PSDrive пользователи отправлялись в расположение по умолчанию для этого диска.

Выражаем благодарность [@mcbobke](https://github.com/mcbobke), так как теперь пользователи отправляются в последний известный текущий рабочий каталог для данного сеанса.

### <a name="windows-powershell-type-accelerators"></a>Ускорители типов Windows PowerShell

Мы включили в Windows PowerShell следующие ускорители типов для упрощения работы с их соответствующими типами.

- `[adsi]`: `System.DirectoryServices.DirectoryEntry`
- `[adsisearcher]`: `System.DirectoryServices.DirectorySearcher`
- `[wmi]`: `System.Management.ManagementObject`
- `[wmiclass]`: `System.Management.ManagementClass`
- `[wmisearcher]`: `System.Management.ManagementObjectSearcher`

Эти ускорители не были включены в PowerShell 6, но были добавлены в PowerShell 6.1 в Windows.

Эти типы полезны при создании объектов AD и WMI.

Например, можно выполнить запрос с помощью LDAP.

```powershell
[adsi]'LDAP://CN=FooUse,OU=People,DC=contoso,DC=com'
```

В следующем примере создается объект CIM Win32_OperatingSystem.

```powershell
[wmi]"Win32_OperatingSystem=@"
```

```Output
SystemDirectory : C:\WINDOWS\system32
Organization    : Contoso IT
BuildNumber     : 18234
RegisteredUser  : Contoso Corp.
SerialNumber    : 12345-67890-ABCDE-F0123
Version         : 10.0.18234
```

Этот пример возвращает объект ManagementClass для класса Win32_OperatingSystem.

```powershell
[wmiclass]"Win32_OperatingSystem"
```

```Output
   NameSpace: ROOT\cimv2

Name                                Methods              Properties
----                                -------              ----------
Win32_OperatingSystem               {Reboot, Shutdown... {BootDevice, BuildNumber, BuildType, Caption...}
```

### <a name="-lp-alias-for-all--literalpath-parameters"></a>Псевдоним `-lp` для всех параметров `-LiteralPath`

Выражаем благодарность [@kvprasoon](https://github.com/kvprasoon), так как теперь у нас есть псевдоним параметра `-lp` для всех встроенных командлетов PowerShell, у которых есть параметр `-LiteralPath`.

## <a name="breaking-changes"></a>Критические изменения

### <a name="msi-based-installation-paths-on-windows"></a>Пути установки на основе MSI в Windows

Теперь в Windows пакет MSI устанавливается по следующему пути:

- `$env:ProgramFiles\PowerShell\6\` для стабильной установки версии 6.x;
- `$env:ProgramFiles\PowerShell\6-preview\` для установки предварительной версии 6.x.

Это изменение гарантирует, что PowerShell Core можно обновлять и обслуживать с помощью Центра обновления Майкрософт.

Дополнительные сведения см. в [PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md).

### <a name="telemetry-can-only-be-disabled-with-an-environment-variable"></a>Данные телеметрии можно отключить только с помощью переменной среды

PowerShell Core отправляет основные данные телеметрии в корпорацию Майкрософт при запуске. В эти данные входят имя ОС, версия ОС и версия PowerShell. Они позволяют нам лучше понимать среды, где используется PowerShell, а также приоритизировать новые функции и исправления.

Чтобы отказаться от использования данных телеметрии, задайте для переменной среды `POWERSHELL_TELEMETRY_OPTOUT` значение `true`, `yes` или `1`. Мы больше не поддерживаем удаление файла `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` для отключения телеметрии.

### <a name="disallowed-basic-auth-over-http-in-powershell-remoting-on-unix-platforms"></a>В системе удаленного взаимодействия PowerShell на платформах Unix запрещена обычная проверка подлинности по протоколу HTTP

Чтобы исключить использование незашифрованного трафика, теперь для удаленного взаимодействия PowerShell на платформах Unix требуется использование NTLM или Negotiate либо HTTPS.

Дополнительные сведения об этих изменениях см. в статье [Проблема № 6779](https://github.com/PowerShell/PowerShell/issues/6779).

### <a name="removed-visualbasic-as-a-supported-language-in-add-type"></a>Удален `VisualBasic` как поддерживаемый язык в Add-Type

Раньше для компиляции кода Visual Basic использовался командлет `Add-Type`. Visual Basic редко использовался с `Add-Type`. Мы удалили эту функцию, чтобы уменьшить размер PowerShell.

### <a name="cleaned-up-uses-of-commandtypesworkflow-and-workflowinfocleaned"></a>Отменено использование `CommandTypes.Workflow` и `WorkflowInfoCleaned`

Дополнительные сведения об этих изменениях см. в статье [PR #6708](https://github.com/PowerShell/PowerShell/pull/6708).

### <a name="group-object-now-sorts-the-groups"></a>Командлет Group-Object теперь умеет сортировать группы

В рамках оптимизации производительности `Group-Object` возвращает отсортированный список групп.
При этом порядок может быть произвольным, и может оказаться, что это не то, что вам нужно, если вам потребуется первая группа. Мы решили, что это изменение стоит реализовать из-за роста производительности и незначительной зависимости от прежнего поведения командлета.

Дополнительные сведения об этом изменении см. в разделе [проблема № 7409](https://github.com/PowerShell/PowerShell/issues/7409).

<!-- URL references -->
[Экспериментальные возможности]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
