---
ms.date: 02/03/2020
keywords: powershell,core
title: Критические изменения в PowerShell Core 6.0
description: В этой статье приведены различия между Windows PowerShell 5.1 и PowerShell 6.0.
ms.openlocfilehash: b53365ee72e6a6e85faa56125a8aa7961d3ecc7f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833808"
---
# <a name="breaking-changes-for-powershell-6x"></a>Критические изменения в PowerShell 6.x

## <a name="features-no-longer-available-in-powershell-core"></a>Функции, которые больше недоступны в PowerShell Core

### <a name="modules-not-shipped-for-powershell-6x"></a>Модули, не поставляемые для PowerShell 6.x

По различным причинам совместимости следующие модули не включены в PowerShell 6.

- ISE
- Microsoft.PowerShell.LocalAccounts
- Microsoft.PowerShell.ODataUtils
- Microsoft.PowerShell.Operation.Validation
- PSScheduledJob
- PSWorkflow
- PSWorkflowUtility

### <a name="powershell-workflow"></a>Рабочий процесс PowerShell

[Рабочий процесс PowerShell][workflow] — это компонент Windows PowerShell на основе [Windows Workflow Foundation (WF)][workflow-foundation]. Он позволяет создавать надежные модули Runbook для долго выполняющихся или параллелизованных задач.

Из-за отсутствия поддержки Windows Workflow Foundation в .NET Core мы больше не поддерживаем рабочий процесс PowerShell в PowerShell Core.

В будущем мы хотели бы реализовать собственный параллелизм в языке PowerShell без необходимости использовать рабочий процесс PowerShell.

Если нужно возобновить выполнение скрипта после перезагрузки операционной системы с помощью контрольных точек, рекомендуем использовать планировщик задач. Он позволит запустить скрипт при запуске ОС. Но скрипт должен поддерживать свое собственное состояние (например, сохранять его в файле).

[workflow]: /previous-versions/powershell/scripting/components/workflows-guide
[workflow-foundation]: /dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a>Настраиваемые оснастки

[Оснастки PowerShell][snapin] являются предшественниками модулей PowerShell, которые не имеют широкого распространения в сообществе PowerShell.

Из-за сложности поддержки оснасток и отсутствия их использования в сообществе мы больше не поддерживаем настраиваемые оснастки в PowerShell Core.

В настоящее время это нарушает работу модулей `ActiveDirectory` и `DnsClient` в Windows и Windows Server.

[snapin]: /powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a>Командлеты инструментария WMI версии 1

Из-за сложности поддержки двух наборов модулей на основе инструментария WMI мы удалили командлеты инструментария WMI версии 1 из PowerShell Core:

- `Register-WmiEvent`
- `Set-WmiInstance`
- `Invoke-WmiMethod`
- `Get-WmiObject`
- `Remove-WmiObject`

Вместо этого мы рекомендуем вам использовать командлеты CIM (также называемыми инструментарием WMI версии 2), которые обеспечивают те же функциональные возможности, а также новые возможности и обновленный синтаксис:

- `Get-CimAssociatedInstance`
- `Get-CimClass`
- `Get-CimInstance`
- `Get-CimSession`
- `Invoke-CimMethod`
- `New-CimInstance`
- `New-CimSession`
- `New-CimSessionOption`
- `Register-CimIndicationEvent`
- `Remove-CimInstance`
- `Remove-CimSession`
- `Set-CimInstance`

### <a name="microsoftpowershelllocalaccounts"></a>Microsoft.PowerShell.LocalAccounts

Из-за использования неподдерживаемых API модуль `Microsoft.PowerShell.LocalAccounts` был удален из PowerShell Core, пока не будет найдено лучшее решение.

### <a name="new-webserviceproxy-cmdlet-removed"></a>Командлет `New-WebServiceProxy` удален

.NET Core не поддерживает платформу Windows Communication Framework, которая предоставляет службы для использования протокола SOAP. Этот командлет удален, так как для него нужен протокол SOAP.

### <a name="-transaction-cmdlets-removed"></a>`*-Transaction` командлеты удалены

Эти командлеты использовали очень ограниченный объем использования. Было принято решение о прекращении их поддержки.

- `Complete-Transaction`
- `Get-Transaction`
- `Start-Transaction`
- `Undo-Transaction`
- `Use-Transaction`

### <a name="security-cmdlets-not-available-on-non-windows-platforms"></a>Командлеты безопасности недоступны на платформах, отличных от Windows

- `Get-Acl`
- `Set-Acl`
- `Get-AuthenticodeSignature`
- `Set-AuthenticodeSignature`
- `Get-CmsMessage`
- `Protect-CmsMessage`
- `Unprotect-CmsMessage`
- `New-FileCatalog`
- `Test-FileCatalog`

### <a name="-computerand-other-windows-specific-cmdlets"></a>`*-Computer`и другие командлеты для Windows

Из-за использования неподдерживаемых API следующие командлеты исключены из PowerShell Core, пока не будет найдено лучшее решение.

- `Get-Clipboard`
- `Set-Clipboard`
- `Add-Computer`
- `Checkpoint-Computer`
- `Remove-Computer`
- `Restore-Computer`
- `Reset-ComputerMachinePassword`
- `Disable-ComputerRestore`
- `Enable-ComputerRestore`
- `Get-ComputerRestorePoint`
- `Test-ComputerSecureChannel`
- `Get-ControlPanelItem`
- `Show-ControlPanelItem`
- `Get-HotFix`
- `Clear-RecycleBin`
- `Update-List`
- `Out-Printer`
- `ConvertFrom-String`
- `Convert-String`

### <a name="-counter-cmdlets"></a>Командлеты `*-Counter`

Из-за использования неподдерживаемых API модуль `*-Counter` был удален из PowerShell Core, пока не будет найдено лучшее решение.

### <a name="-eventlog-cmdlets"></a>Командлеты `*-EventLog`

Из-за использования неподдерживаемых API модуль `*-EventLog` был удален из PowerShell Core, пока не будет найдено лучшее решение. `Get-WinEvent` и `New-WinEvent` доступны для получения и создания событий в Windows.

### <a name="cmdlets-that-use-wpf-removed"></a>Командлеты, использующие WPF, удалены

Платформа Windows Presentation Framework не поддерживается в CoreCLR. Затрагиваются следующие командлеты:

- `Show-Command`
- `Out-GridView`
- Параметр **showwindow** для `Get-Help`

### <a name="some-dsc-cmdlets-removed"></a>Некоторые командлеты DSC удалены

- `Get-DscConfiguration`
- `Publish-DscConfiguration`
- `Restore-DscConfiguration`
- `Start-DscConfiguration`
- `Stop-DscConfiguration`
- `Test-DscConfiguration`
- `Update-DscConfiguration`
- `Remove-DscConfigurationDocument`
- `Get-DscConfigurationStatus`
- `Disable-DscDebug`
- `Enable-DscDebug`
- `Get-DscLocalConfigurationManager`
- `Set-DscLocalConfigurationManager`
- `Invoke-DscResource`

## <a name="enginelanguage-changes"></a>Изменения модуля и языка

### <a name="rename-powershellexe-to-pwshexe-5101"></a>`powershell.exe` переименован в `pwsh.exe` [№ 5101](https://github.com/PowerShell/PowerShell/issues/5101)

Чтобы предоставить пользователям детерминированный способ вызова PowerShell Core в Windows (в отличие от Windows PowerShell), двоичный файл PowerShell Core был переименован в `pwsh.exe` на платформах Windows и в `pwsh` на других платформах.

Сокращенное имя также согласуется с именованием оболочек на платформах, отличных от Windows.

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193"></a>Разрывы строк не вставляются в выходные данные (за исключением таблиц) [№ 5193](https://github.com/PowerShell/PowerShell/issues/5193)

Раньше выходные данные выравнивались по ширине консоли, а разрывы строк добавлялись в конце окна консоли. Из-за этого выходные данные не были переформатированы как ожидалось, если размер терминала был изменен. Это изменение не было применено к таблицам, так как разрывы строк необходимы для выравнивания столбцов.

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432"></a>Пропуск проверки элемента NULL для коллекций с типом элемента в виде типа значения [№ 5432](https://github.com/PowerShell/PowerShell/issues/5432)

Для параметра `Mandatory` и атрибутов `ValidateNotNull` и `ValidateNotNullOrEmpty` пропускается проверка элемента NULL, если тип элемента коллекции является типом значения.

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369"></a>Теперь `$OutputEncoding` использует кодирование `UTF-8 NoBOM`, а не ASCII [№ 5369](https://github.com/PowerShell/PowerShell/issues/5369)

Предыдущая кодировка, ASCII (7 бит), в некоторых случаях приводила к неправильному изменению выходных данных. С этим изменением `UTF-8 NoBOM` становится кодировкой по умолчанию, благодаря чему выходные данные в Юникоде остаются в кодировке, поддерживаемой большинством инструментов и операционных систем.

### <a name="remove-allscope-from-most-default-aliases-5268"></a>Атрибут `AllScope` удален из большинства псевдонимов по умолчанию [№ 5268](https://github.com/PowerShell/PowerShell/issues/5268)

Чтобы ускорить создание области, атрибут `AllScope` был удален из большинства псевдонимов по умолчанию. Атрибут `AllScope` был оставлен для нескольких часто используемых псевдонимов, где поиск выполнялся быстрее.

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113"></a>`-Verbose` и `-Debug` больше не переопределяют `$ErrorActionPreference` [№ 5113](https://github.com/PowerShell/PowerShell/issues/5113)

Ранее, если `-Verbose` или `-Debug` были указаны, поведение `$ErrorActionPreference` переопределялось. С этим изменением `-Verbose` и `-Debug` больше не влияют на поведение `$ErrorActionPreference`.

## <a name="cmdlet-changes"></a>Изменения в командлетах

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320"></a>Invoke-RestMethod не возвращает полезные сведения, если данные не возвращаются. [№ 5320](https://github.com/PowerShell/PowerShell/issues/5320)

Если API возвращал только значение `null`, Invoke-RestMethod сериализовал его в качестве строки `"null"`, а не `$null`. Это изменение исправляет логику в `Invoke-RestMethod`, чтобы надлежащим образом сериализовать одно допустимое значение литерала JSON `null` как `$null`.

### <a name="remove--protocol-from--computer-cmdlets-5277"></a>Параметр `-Protocol` удален из командлетов `*-Computer`[№ 5277](https://github.com/PowerShell/PowerShell/issues/5277)

Из-за проблем с удаленным взаимодействием RPC в CoreFX (особенно на платформах не под управлением Windows) и обеспечением согласованного удаленного взаимодействия в PowerShell параметр `-Protocol` был удален из командлетов `\*-Computer`. DCOM больше не поддерживается для удаленного взаимодействия. Следующие командлеты поддерживают только удаленное взаимодействие через WSMAN.

- Rename-Computer
- Restart-Computer
- Stop-Computer

### <a name="remove--computername-from--service-cmdlets-5090"></a>Параметр `-ComputerName` удален из командлетов `*-Service`[№ 5090](https://github.com/PowerShell/PowerShell/issues/5094)

Чтобы способствовать согласованному использованию PSRP, параметр `-ComputerName` был удален из командлетов `*-Service`.

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197"></a>Теперь при обработке `Get-Item -LiteralPath a*b` возвращается ошибка, если `a*b` фактически не существует [№ 5197](https://github.com/PowerShell/PowerShell/issues/5197)

Раньше при указании подстановочного знака `-LiteralPath` обрабатывал его так же, как `-Path`, и если для подстановочного знака не было найдено файлов, автоматически выполнялся выход. Правильное поведение — `-LiteralPath` является литералом, поэтому, если файл не существует, должна возвращаться ошибка. С этим изменением подстановочные знаки, используемые с `-Literal`, рассматриваются в качестве литерала.

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134"></a>`Import-Csv` применяет `PSTypeNames` при импорте, если информация о типе присутствует в CSV [№ 5134](https://github.com/PowerShell/PowerShell/issues/5134)

Ранее объекты, экспортированные с помощью `Export-CSV` с информацией `TypeInformation`, импортированной с помощью `ConvertFrom-Csv`, не сохраняли информацию о типе. Это изменение добавляет информацию о типе в элемент `PSTypeNames`, если она доступна в CSV-файле.

### <a name="-notypeinformation-should-be-default-on-export-csv-5131"></a>`-NoTypeInformation` теперь присутствует по умолчанию в `Export-Csv` [№ 5131](https://github.com/PowerShell/PowerShell/issues/5131)

Это изменение было внесено с учетом отзывов пользователей о том, чтобы `Export-CSV` по умолчанию содержал сведения о типе.

Ранее командлет выводил комментарий в качестве первой строки, содержащей имя типа объекта. Изменение заключается в том, чтобы подавить это поведение по умолчанию, так как оно не распознается большинством инструментов. Используйте `-IncludeTypeInformation`, чтобы сохранить предыдущий режим работы.

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112"></a>Теперь веб-командлеты выдают предупреждение, если `-Credential` отправляется по незашифрованным подключениям [№ 5112](https://github.com/PowerShell/PowerShell/issues/5112)

При использовании HTTP содержимое, включая пароли, отправляется в виде открытого текста. В этом изменении такое поведение запрещено по умолчанию и возвращается ошибка, если учетные данные передаются небезопасным образом. Пользователи могут обойти это с помощью параметра `-AllowUnencryptedAuthentication`.

## <a name="api-changes"></a>Изменения API

### <a name="remove-addtypecommandbase-class-5407"></a>Удален класс `AddTypeCommandBase`[№ 5407](https://github.com/PowerShell/PowerShell/issues/5407)

Класс `AddTypeCommandBase` был удален из `Add-Type` для повышения производительности. Этот класс используется только командлетом Add-Type и не должен влиять на пользователей.

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080"></a>Теперь командлеты с параметром `-Encoding` имеют тип `System.Text.Encoding` [№ 5080](https://github.com/PowerShell/PowerShell/issues/5080)

Значение `-Encoding``Byte` было удалено из командлетов поставщика файловой системы. Новый параметр, `-AsByteStream`, теперь используется для указания того, что в качестве входного потока требуется поток байтов или что выходной поток представляет собой поток байтов.

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055"></a>Добавлено улучшенное сообщение об ошибке для параметра `-UFormat` с пустым или нулевым значением [№ 5055](https://github.com/PowerShell/PowerShell/issues/5055)

Ранее при передаче пустой строки формата в `-UFormat` отображалось бесполезное сообщение об ошибке. Было добавлено более описательное сообщение об ошибке.

### <a name="clean-up-console-code-4995"></a>Очищен код консоли [№ 4995](https://github.com/PowerShell/PowerShell/issues/4995)

Следующие функции были удалены, так как они не поддерживаются в PowerShell Core. Какие-либо планы по реализации их поддержки отсутствуют, так как они относятся к прежним версиям PowerShell. `-psconsolefile` — параметр и код, `-importsystemmodules` — параметр, код, а также код, изменяющий шрифт.

### <a name="removed-runspaceconfiguration-support-4942"></a>Удалена поддержка `RunspaceConfiguration`[№ 4942](https://github.com/PowerShell/PowerShell/issues/4942)

Ранее при создании пространства выполнения PowerShell программными средствами с помощью API можно было использовать прежние версии [`RunspaceConfiguration`][runspaceconfig] или более новые версии [`InitialSessionState`][iss]. Это изменение удалило поддержку `RunspaceConfiguration`, и теперь поддерживается только `InitialSessionState`.

[runspaceconfig]: /dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: /dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923"></a>`CommandInvocationIntrinsics.InvokeScript` — привязка аргументов к `$input`, а не к `$args` [№ 4923](https://github.com/PowerShell/PowerShell/issues/4923)

Из-за неверного положения параметра аргументы передавались в качестве входных данных, а не аргументов.

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903"></a>Удален неподдерживаемый параметр `-showwindow` из `Get-Help` [№ 4903](https://github.com/PowerShell/PowerShell/issues/4903)

`-showwindow` использует WPF, который не поддерживается в CoreCLR.

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866"></a>Разрешено использовать * в пути реестра для `Remove-Item` [№ 4866](https://github.com/PowerShell/PowerShell/issues/4866)

Раньше при указании подстановочного знака `-LiteralPath` обрабатывал его так же, как `-Path`, и если для подстановочного знака не было найдено файлов, автоматически выполнялся выход. Правильное поведение — `-LiteralPath` является литералом, поэтому, если файл не существует, должна возвращаться ошибка. С этим изменением подстановочные знаки, используемые с `-Literal`, рассматриваются в качестве литерала.

### <a name="fix-set-service-failing-test-4802"></a>`Set-Service` исправлено для правильной обработки [№ 4802](https://github.com/PowerShell/PowerShell/issues/4802)

Ранее при использовании `New-Service -StartupType foo` часть `foo` игнорировалась и создавалась служба с определенным типом запуска по умолчанию. Это изменение предназначено, чтобы явно вызывать ошибку недопустимого типа запуска.

### <a name="rename-isosx-to-ismacos-4700"></a>`$IsOSX` переименован в `$IsMacOS` [№ 4700](https://github.com/PowerShell/PowerShell/issues/4700)

Именование в PowerShell должно согласовываться с нашим именованием и соответствовать использованию в Apple ОС macOS вместо OSX. Однако для удобочитаемости и согласованности используется регистр Pascal.

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573"></a>Согласованное сообщение об ошибке при передаче недопустимого скрипта в -File, лучшая ошибка при передаче неоднозначного аргумента [№ 4573](https://github.com/PowerShell/PowerShell/issues/4573)

Коды выхода `pwsh.exe` изменены в соответствии с соглашениями Unix.

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302-4303"></a>Модуль `LocalAccount` и командлеты удалены из модулей `Diagnostics` [№ 4302](https://github.com/PowerShell/PowerShell/issues/4302) [№ 4303](https://github.com/PowerShell/PowerShell/issues/4303)

Из-за неподдерживаемых API модуль `LocalAccounts` и командлеты `Counter` в модуле `Diagnostics` были удалены, пока не будет найдено лучшее решение.

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036"></a>Выполнение скрипта PowerShell с параметром bool не работает [№ 4036](https://github.com/PowerShell/PowerShell/issues/4036)

Ранее при использовании **powershell.exe** (теперь **pwsh.exe**) для выполнения скрипта PowerShell с параметром `-File` было невозможно передать значения `$true`/`$false` в качестве значений параметра. Была добавлена поддержка `$true`/`$false` в качестве анализируемых значений. Значения параметров также поддерживаются, так как в настоящий момент синтаксис документа не работает.

### <a name="remove-clrversion-property-from-psversiontable-4027"></a>Свойство `ClrVersion` удалено из `$PSVersionTable` [№ 4027](https://github.com/PowerShell/PowerShell/issues/4027)

Свойство `ClrVersion` параметра `$PSVersionTable` бесполезно в CoreCLR. Пользователи не должны использовать это значение для определения совместимости.

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019"></a>Позиционный параметр для `powershell.exe` из `-Command` изменен на `-File` [№ 4019](https://github.com/PowerShell/PowerShell/issues/4019)

Разрешите использование знака решетки PowerShell на платформах, отличных от Windows. В системах на основе Unix это означает, что вы можете создать исполняемый файл скрипта, который будет вызывать PowerShell автоматически, а не явно вызывать `pwsh`. Это также означает, что вы можете выполнять такие команды, как `powershell foo.ps1` или `powershell fooScript`, без указания `-File`. Однако это изменение требует явно указать `-c` или `-Command` при попытке запуска таких команд, как `powershell.exe Get-Command`.

### <a name="implement-unicode-escape-parsing-3958"></a>Реализован анализ escape-символов в Юникоде [№ 3958](https://github.com/PowerShell/PowerShell/issues/3958)

`` `u####`` или `` `u{####}`` преобразуются в соответствующий символ Юникода. Для вывода литерала `` `u`` добавьте escape-символ в виде обратного апострофа: ``` ``u```.

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940"></a>Кодирование `New-ModuleManifest` изменено на `UTF8NoBOM` на платформах, отличных от Windows [№ 3940](https://github.com/PowerShell/PowerShell/issues/3940)

Ранее `New-ModuleManifest` создавал манифесты PSD1 в UTF-16 с меткой порядка байтов, создавая проблемы для инструментов Linux. Это критическое изменение, которое изменяет кодировку `New-ModuleManifest` на UTF (без метки порядка байтов) в платформах, отличных от Windows.

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780"></a>Предотвращение рекурсии `Get-ChildItem` в символические ссылки (№ 1875) [№ 3780](https://github.com/PowerShell/PowerShell/issues/3780)

Это изменение приводит `Get-ChildItem` в соответствие с собственными командами `ls -r` Unix и `dir /s` Windows. Подобно упомянутым командам, командлет отображает символические ссылки на каталоги, найденные во время рекурсии, но не рекурсирует в них.

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706"></a>`Get-Content -Delimiter` исправлен таким образом, чтобы в возвращенных строках не содержался разделитель [№ 3706](https://github.com/PowerShell/PowerShell/issues/3706)

Ранее при использовании `Get-Content -Delimiter` выходные данные были несогласованными и неудобными, так как для удаления разделителя требовалась их дальнейшая обработка. Это изменение удаляет разделитель в возвращаемых строках.

### <a name="implement-format-hex-in-c-3320"></a>Реализация Format-Hex в C# [№ 3320](https://github.com/PowerShell/PowerShell/issues/3320)

Параметр `-Raw` теперь не выполняет никаких действий. В дальнейшем все выходные данные будут отображаться с истинным представлением чисел, в том числе все байты для соответствующего типа (что параметр `-Raw` формально делал до этого изменения).

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319"></a>PowerShell как оболочка по умолчанию не работает с командой скрипта [№ 3319](https://github.com/PowerShell/PowerShell/issues/3319)

В Unix оболочки по умолчанию принимают `-i` для интерактивной оболочки. Многие инструменты ожидают такого поведения (например, `script` и при установке PowerShell в качестве оболочки по умолчанию) и вызывают оболочку с помощью параметра `-i`. Это изменение является критическим, так как `-i` ранее можно было использовать как сокращение для сопоставления с параметром `-inputformat`, который теперь должен соответствовать `-in`.

### <a name="typo-fix-in-get-computerinfo-property-name-3167"></a>Исправлена опечатка в имени свойства Get-ComputerInfo [№ 3167](https://github.com/PowerShell/PowerShell/issues/3167)

`BiosSerialNumber` был написан с ошибкой (как `BiosSeralNumber`). Теперь ошибка исправлена.

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024"></a>Добавлены командлеты `Get-StringHash` и `Get-FileHash`[№ 3024](https://github.com/PowerShell/PowerShell/issues/3024)

Это изменение заключается в том, что некоторые хэш-алгоритмы не поддерживаются CoreFX, поэтому они больше недоступны:

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672"></a>Добавлена проверка командлетов `Get-*`, в которых передача значения $null возвращала все объекты вместо ошибки [№ 2672](https://github.com/PowerShell/PowerShell/issues/2672)

Передача `$null` в любой из следующих командлетов теперь вызывает ошибку:

- `Get-Credential -UserName`
- `Get-Event -SourceIdentifier`
- `Get-EventSubscriber -SourceIdentifier`
- `Get-Help -Name`
- `Get-PSBreakpoint -Script`
- `Get-PSProvider -PSProvider`
- `Get-PSSessionConfiguration -Name`
- `Get-PSSnapin -Name`
- `Get-Runspace -Name`
- `Get-RunspaceDebug -RunspaceName`
- `Get-Service -Name`
- `Get-TraceSource -Name`
- `Get-Variable -Name`
- `Get-WmiObject -Class`
- `Get-WmiObject -Property`

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482"></a>Добавлена поддержка расширенного формата файла журнала W3C в `Import-Csv` [№ 2482](https://github.com/PowerShell/PowerShell/issues/2482)

Ранее командлет `Import-Csv` не мог использоваться для непосредственного импорта файлов журнала в расширенный формат журнала W3C и требовалось дополнительное действие. Благодаря этому изменению теперь поддерживается расширенный формат журнала W3C.

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035"></a>Проблема привязки параметра с `ValueFromRemainingArguments` в функциях PS [№ 2035](https://github.com/PowerShell/PowerShell/issues/2035)

`ValueFromRemainingArguments` теперь возвращает значения в виде массива, а не одного значения, которое само по себе являлось массивом.

### <a name="buildversion-is-removed-from-psversiontable-1415"></a>Свойство `BuildVersion` удалено из `$PSVersionTable` [№ 1415](https://github.com/PowerShell/PowerShell/issues/1415)

Свойство `BuildVersion` удалено из `$PSVersionTable`. Это свойство было привязано к версии сборки Windows. Вместо этого мы рекомендуем использовать `GitCommitId` для получения точной версии сборки PowerShell Core.

### <a name="changes-to-web-cmdlets"></a>Изменения в веб-командлетах

Базовый API .NET веб-командлетов был изменен на `System.Net.Http.HttpClient`. Это изменение предоставляет множество преимуществ. Тем не менее это изменение вместе с недостатком взаимодействия с Internet Explorer привело к нескольким критическим изменениям в `Invoke-WebRequest` и `Invoke-RestMethod`.

- `Invoke-WebRequest` теперь поддерживает только основной анализ HTML. `Invoke-WebRequest` всегда возвращает объект `BasicHtmlWebResponseObject`. Свойства `ParsedHtml` и `Forms` были удалены.
- Значения `BasicHtmlWebResponseObject.Headers` теперь имеют тип `String[]`, а не `String`.
- `BasicHtmlWebResponseObject.BaseResponse` теперь является объектом `System.Net.Http.HttpResponseMessage`.
- Свойство `Response` в исключениях веб-командлетов теперь является объектом `System.Net.Http.HttpResponseMessage`.
- Строгий анализ заголовка RFC теперь является поведением по умолчанию для параметров `-Headers` и `-UserAgent`. Это можно обойти с помощью `-SkipHeaderValidation`.
- Схемы URI `file://` и `ftp://` больше не поддерживаются.
- Параметры `System.Net.ServicePointManager` больше не обрабатываются.
- В настоящее время в macOS нет проверки подлинности на основе сертификатов.
- Использование `-Credential` в URI `http://` завершится ошибкой. Используйте URI `https://` или передайте параметр `-AllowUnencryptedAuthentication`, чтобы подавить ошибку.
- `-MaximumRedirection` теперь создает неустранимую ошибку, если попытки перенаправления превышают указанный предел, вместо возвращения результатов последнего перенаправления.
- В PowerShell 6.2 мы внесли изменения в кодировку UTF-8 по умолчанию для ответов JSON. Если для ответа JSON не указан набор символов, по умолчанию должна использоваться кодировка UTF-8 в соответствии с RFC 8259.
