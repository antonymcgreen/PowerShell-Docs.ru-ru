---
description: Предотвращает запуск скрипта без необходимых элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: c6b10137ca58da93caff365a50b125929fd4d11a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232537"
---
# <a name="about-requires"></a>О программе требуется

## <a name="short-description"></a>Краткое описание
Предотвращает запуск скрипта без необходимых элементов.

## <a name="long-description"></a>Подробное описание

`#Requires`Инструкция предотвращает выполнение скрипта, если не выполнены версия PowerShell, модули (и версия), а также оснастки (и версия) и предварительные требования к выпуску. Если необходимые условия не соблюдены, PowerShell не выполняет сценарий.

### <a name="syntax"></a>Синтаксис

```
#Requires -Assembly { <Path to .dll> | <.NET assembly specification> }
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

Дополнительные сведения о синтаксисе см. в разделе [скриптрекуирементс](/dotnet/api/system.management.automation.language.scriptrequirements).

### <a name="rules-for-use"></a>Правила использования

Скрипт может включать более одной `#Requires` инструкции. `#Requires`Инструкции могут присутствовать в любой строке скрипта.

Размещение `#Requires` оператора внутри функции не ограничивает ее область действия. Все `#Requires` инструкции всегда применяются глобально и должны выполняться, прежде чем скрипт сможет выполняться.

> [!WARNING]
> Хотя `#Requires` инструкция может присутствовать в любой строке скрипта, ее расположение в скрипте не влияет на последовательность своего приложения. Глобальное состояние, `#Requires` перед выполнением скрипта должна быть удовлетворена инструкция.

Пример

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

Можно подумать, что приведенный выше код не должен выполняться, так как необходимый модуль был удален до `#Requires` инструкции. Однако `#Requires` перед выполнением скрипта должно быть выполнено состояние. Первая строка скрипта не проверяла требуемое состояние.

### <a name="parameters"></a>Параметры

#### <a name="-assembly-assembly-path--net-assembly-specification"></a>-Assembly \<Assembly path> |\<.NET assembly specification>

Указывает путь к DLL-файлу сборки или имени сборки .NET. Параметр **Assembly** появился в PowerShell 5,0. Дополнительные сведения о сборках .NET см. в разделе [имена сборок](/dotnet/standard/assembly/names).

Пример:

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a>-Version \<N\> [. \<n\> ]

Указывает минимальную версию PowerShell, требуемую для скрипта. Введите основной номер версии и необязательный дополнительный номер версии.

Пример:

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a>-PSSnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]

Указывает оснастку PowerShell, требуемую для скрипта. Введите имя оснастки и номер необязательной версии.

Пример:

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a>-Modules \<Module-Name\> |\<Hashtable\>

Указывает модули PowerShell, необходимые для скрипта. Введите имя модуля и номер необязательной версии.

Если необходимые модули не находятся в текущем сеансе, PowerShell импортирует их.
Если не удается импортировать модули, PowerShell выдает ошибку, завершающуюся ошибкой.

Для каждого модуля введите имя модуля ( \<String\> ) или хэш-таблицу. Значение может быть сочетанием строк и хэш-таблиц. Хэш-таблица содержит следующие ключи.

- `ModuleName` - **Обязательное требование** Указывает имя модуля.
- `GUID` - **Необязательно** Указывает идентификатор GUID модуля.
- **Также необходимо** указать один из трех указанных ниже ключей. Эти ключи нельзя использовать совместно.
  - `ModuleVersion` — Указывает минимальную допустимую версию модуля.
  - `RequiredVersion` — Указывает точную, требуемую версию модуля.
  - `MaximumVersion` — Указывает максимально допустимую версию модуля.

> [!NOTE]
> `RequiredVersion` был добавлен в Windows PowerShell 5,0.
> `MaximumVersion` был добавлен в Windows PowerShell 5,1.

Пример:

Требовать `AzureRM.Netcore` установки (версии `0.12.0` или выше).

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

Требовать `AzureRM.Netcore` установку **только** версии `0.12.0` .

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

Требует `AzureRM.Netcore` установки (версии `0.12.0` или меньше).

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

Требовать установки любой версии `AzureRM.Netcore` и `PowerShellGet` .

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

При использовании `RequiredVersion` ключа убедитесь, что строка версии точно соответствует требуемой строке версии.

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

В следующем примере происходит сбой, так как **0,12** не полностью соответствует **0.12.0**.

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a>-PSEdition \<PSEdition-Name\>

Указывает выпуск PowerShell, который требуется для скрипта. Допустимые значения: **Core** для PowerShell Core и **Desktop** для Windows PowerShell.

Пример:

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a>-Шеллид

Указывает оболочку, требуемую для скрипта. Введите идентификатор оболочки. При использовании параметра **шеллид** необходимо также включить параметр **PSSnapin** .
Текущую **шеллид** можно найти, запросив `$ShellId` автоматическую переменную.

Пример:

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> Этот параметр предназначен для использования в мини-оболочках, которые являются устаревшими.

#### <a name="-runasadministrator"></a>-Рунасадминистратор

Когда этот параметр Switch добавляется к `#Requires` оператору, он указывает, что сеанс PowerShell, в котором выполняется скрипт, должен быть запущен с повышенными правами пользователя. Параметр **рунасадминистратор** игнорируется в операционной системе, отличной от Windows. Параметр **рунасадминистратор** появился в PowerShell 4,0.

Пример:

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a>Примеры

Следующий скрипт содержит две `#Requires` инструкции. Если требования, указанные в обоих инструкциях, не выполняются, скрипт не выполняется. Каждая `#Requires` инструкция должна быть первым элементом в строке:

```powershell
#Requires -Modules AzureRM.Netcore
#Requires -Version 6.0
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a>См. также статью

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Language_Keywords](about_Language_Keywords.md)
