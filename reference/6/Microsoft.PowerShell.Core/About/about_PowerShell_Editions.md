---
description: Различные выпуски PowerShell выполняются в разных базовых средах выполнения.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 4649c1b47a69423eb2f11a119583f441191882dd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231353"
---
# <a name="about-powershell-editions"></a>О выпусках PowerShell

## <a name="short-description"></a>Краткое описание
Различные выпуски PowerShell выполняются в разных базовых средах выполнения.

## <a name="long-description"></a>Полное описание

В PowerShell 5,1 существует несколько _выпусков_ PowerShell, которые выполняются в другой среде выполнения .NET. В PowerShell 6,2 существует два выпуска PowerShell:

- **Рабочий стол** , работающий на .NET Framework. PowerShell 4 и ниже, а также PowerShell 5,1 в полнофункциональных выпусках Windows, таких как Windows Desktop, Windows Server, Windows Server Core и большинство других операционных систем Windows, являются настольными выпусками. Это исходный выпуск PowerShell.
- **Ядро** , работающее на .NET Core. PowerShell 6,0 и более поздних версий, а также PowerShell 5,1 в некоторых уменьшенных выпусках Windows, таких как Windows Nano Server и Windows IoT, где .NET Framework недоступна.

Поскольку выпуск PowerShell соответствует среде выполнения .NET, он является основным индикатором совместимости .NET API и модуля PowerShell. Некоторые API-интерфейсы .NET, типы или методы недоступны в обеих средах выполнения .NET, и это влияет на сценарии PowerShell и модули, зависящие от них.

## <a name="the-psedition-automatic-variable"></a>`$PSEdition`Автоматическая переменная

В PowerShell 5,1 и более поздних версиях можно узнать, какой выпуск вы используете с `$PSEdition` автоматической переменной:

```powershell
$PSEdition
```

```Output
Core
```

В PowerShell 4 и ниже эта переменная не существует. `$PSEdition` значение null должно рассматриваться так же, как и при наличии значения `Desktop` .

### <a name="edition-in-psversiontable"></a>Выпуск в `$PSVersionTable`

`$PSVersionTable`Автоматическая переменная также содержит сведения о выпуске в PowerShell 5,1 и более поздних версиях:

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

`PSEdition`Поле будет иметь то же значение, что и `$PSEdition` Автоматическая переменная.

## <a name="the-compatiblepseditions-module-manifest-field"></a>`CompatiblePSEditions`Поле манифеста модуля

Модули PowerShell могут объявлять, какие выпуски PowerShell совместимы с, используя `CompatiblePSEditions` поле манифеста модуля.

Например, манифест модуля, объявляющий совместимость с и с `Desktop` `Core` выпусками PowerShell:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

Пример манифеста модуля только с `Desktop` совместимостью:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

Пропуск `CompatiblePSEditions` поля из манифеста модуля приведет к тому же результату, что и установка `Desktop` , так как модули, созданные до этого поля, были неявно написаны для этого выпуска.

Для модулей, не поставляемых в составе Windows (т. е. модулей, которые вы пишете или устанавливаете из коллекции), это поле является информационным. PowerShell не изменяет поведение на основе `CompatiblePSEditions` поля, но предоставляет его `PSModuleInfo` для объекта (возвращаемого `Get-Module` ) для собственной логики:

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> `CompatiblePSEditions`Поле Module совместимо только с PowerShell 5,1 и более поздних версий. Включение этого поля приведет к тому, что модуль будет несовместим с PowerShell 4 и ниже. Поскольку поле является исключительно информационным, его можно спокойно опустить в последующих версиях PowerShell.

В PowerShell 6,1 `Get-Module -ListAvailable` модуль форматирования был обновлен для просмотра совместимости каждого модуля с выпуском:

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                   PSEdition ExportedCommands
---------- -------    ----                   --------- ----------------
Script     1.4.0      Az                     Core,Desk
Script     1.3.1      Az.Accounts            Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                 Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                 Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer       Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility   Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a>Совместимость выпусков для модулей, поставляемых в составе Windows

Для модулей, входящих в состав Windows (или устанавливаемых в составе роли или компонента), PowerShell 6,1 и выше обрабатывают поле по- `CompatiblePSEditions` разному. Такие модули находятся в каталоге системных модулей Windows PowerShell ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).

Для модулей, загруженных из этого каталога или найденных в этом каталоге, в PowerShell 6,1 и более поздних версий используется `CompatiblePSEditions` поле, чтобы определить, будет ли модуль совместимым с текущим сеансом и работать соответствующим образом.

Если `Import-Module` используется, модуль без `Core` `CompatiblePSEditions` импорта не будет импортирован, и отобразится сообщение об ошибке:

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsT
ransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'.
Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to i
gnore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsT
ransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Com
mands.ImportModuleCommand
```

Когда `Get-Module -ListAvailable` используется, модули без `Core` в `CompatiblePSEditions` не будут отображаться:

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

В обоих случаях `-SkipEditionCheck` параметр switch можно использовать для переопределения этого поведения:

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name             PSEdition ExportedCommands
---------- -------    ----             --------- ----------------
Manifest   2.0.0.0    BitsTransfer     Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...
```

> [!WARNING]
> `Import-Module -SkipEditionCheck` может показаться успешным для модуля, но использование этого модуля вызывает риск возникновения несовместимости позже; При первоначальной загрузке модуля команда может впоследствии вызвать несовместимый API и завершиться неудачно.

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a>Создание перекрестной совместимости для модулей PowerShell

При написании модуля PowerShell, предназначенного для `Desktop` и `Core` выпусков PowerShell, существуют вещи, которые можно выполнить для обеспечения совместимости между выпусками.

Единственным верным способом подтверждения и регулярной проверки совместимости является написание тестов для скрипта или модуля и их запуск во всех версиях и выпусках PowerShell, для которых требуется совместимость с. Рекомендуемая платформа тестирования для этого — [Pester][].

### <a name="powershell-script"></a>Сценарий PowerShell

В качестве языка PowerShell работает одинаково в разных выпусках. Это используемые командлеты, модули и API-интерфейсы .NET, которые зависят от совместимости выпуска.

Как правило, скрипты, работающие в PowerShell 6,1 и выше, будут работать с Windows PowerShell 5,1, но есть некоторые исключения.

Модуль версии 1.18.0 [PSScriptAnalyzer][] имеет такие правила, как [псусекомпатиблекоммандс][] и [псусекомпатиблетипес][] , которые способны обнаружить, возможно, несовместимое использование команд и API-интерфейсов .NET в сценариях PowerShell.

### <a name="net-assemblies"></a>Сборки .NET

При написании двоичного модуля или модуля, включающего сборки .NET (DLL), созданные на основе исходного кода, следует компилироваться с [.NET Standard][] и [PowerShell Standard][] для проверки совместимости во время компиляции для СОВМЕСТИМОСТИ .NET и PowerShell API.

Хотя эти библиотеки могут проверять некоторую совместимость во время компиляции, они не смогут перехватывать возможные различия в поведении между выпусками.
Для этого все еще необходимо писать тесты.

## <a name="see-also"></a>См. также статью

- [about_Automatic_Variables](about_Automatic_Variables.md)
- [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
- [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)
- [Модули с совместимыми выпусками PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
[псусекомпатиблекоммандс]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[псусекомпатиблетипес]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
