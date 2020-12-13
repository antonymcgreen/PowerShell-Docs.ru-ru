---
ms.date: 10/16/2019
ms.topic: reference
title: Как написать манифест модуля PowerShell
description: Как написать манифест модуля PowerShell
ms.openlocfilehash: 42db71968ccac1cc3c1c05c5be2e72327e5e28d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647693"
---
# <a name="how-to-write-a-powershell-module-manifest"></a>Написание манифеста модуля PowerShell

После написания модуля PowerShell можно добавить дополнительный манифест модуля, содержащий сведения о модуле. Например, можно описать автора, указать файлы в модуле (например, вложенные модули), выполнить сценарии для настройки среды пользователя, загрузки типов и файлов форматирования, определить требования к системе и ограничить элементы, экспортируемые модулем.

## <a name="creating-a-module-manifest"></a>Создание манифеста модуля

**Манифест модуля** — это файл данных PowerShell ( `.psd1` ), описывающий содержимое модуля и определяющий способ обработки модуля. Файл манифеста — это текстовый файл, содержащий хэш-таблицу ключей и значений. Файл манифеста связывается с модулем путем именования манифеста в качестве модуля и сохранения манифеста в корневом каталоге модуля.

Для простых модулей, содержащих только одну `.psm1` или двоичную сборку, манифест модуля является необязательным. Однако рекомендуется использовать манифест модуля везде, где это возможно, так как они помогают организовать код и поддерживать сведения об управлении версиями. Для экспорта сборки, установленной в [глобальном кэше сборок](/dotnet/framework/app-domains/gac), необходим манифест модуля. Для модулей, поддерживающих функцию обновляемой справки, также требуется манифест модуля. Обновляемая Справка использует ключ **HelpInfoUri** в манифесте модуля, чтобы найти файл справочной информации (HelpInfo XML), содержащий расположение обновленных файлов справки для модуля. Дополнительные сведения об обновляемой справке см. в разделе [Поддержка обновляемой справки](./supporting-updatable-help.md).

### <a name="to-create-and-use-a-module-manifest"></a>Создание и использование манифеста модуля

1. Рекомендуется создать манифест модуля с помощью командлета [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) . Параметры можно использовать для указания одного или нескольких значений по умолчанию и ключей манифеста. Единственное требование — имя файла. `New-ModuleManifest` создает манифест модуля с указанными значениями и включает остальные ключи и их значения по умолчанию. Если необходимо создать несколько модулей, используйте `New-ModuleManifest` для создания шаблона манифеста модуля, который можно изменить для разных модулей. Пример манифеста модуля по умолчанию см. в примере [манифеста модуля](#sample-module-manifest).

   `New-ModuleManifest -Path C:\myModuleName.psd1 -ModuleVersion "2.0" -Author "YourNameHere"`

   Альтернативой является создание хэш-таблицы манифеста модуля вручную с использованием минимальных требуемых **сведений, а** также самого себя. Сохраните файл с тем же именем, что и у модуля, и используйте `.psd1` расширение файла. Затем можно изменить файл и добавить соответствующие ключи и значения.

1. Добавьте в файл манифеста необходимые дополнительные элементы.

   Чтобы изменить файл манифеста, используйте любой текстовый редактор. Но файл манифеста — это файл скрипта, содержащий код, поэтому его можно изменить в среде разработки сценариев или разработке, например Visual Studio Code. Все элементы файла манифеста являются необязательными, за исключением **номера версии** .

   Описание ключей и значений, которые можно включить в манифест модуля, см. в разделе Таблица [элементов манифеста модуля](#module-manifest-elements) . Дополнительные сведения см. в описании параметров в командлете [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) .

1. Для решения любых сценариев, которые могут не охватывать элементы манифеста базового модуля, можно добавить дополнительный код в манифест модуля.

   В целях безопасности PowerShell выполняет только небольшое подмножество доступных операций в файле манифеста модуля. Как правило, можно использовать `if` оператор, арифметические и операторы сравнения, а также базовые типы данных PowerShell.

1. После создания манифеста модуля его можно проверить, чтобы убедиться в правильности всех путей, описанных в манифесте. Чтобы протестировать манифест модуля, используйте [Test-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest).

   `Test-ModuleManifest myModuleName.psd1`

1. Убедитесь, что манифест модуля расположен на верхнем уровне каталога, который содержит ваш модуль.

   Когда вы копируете модуль в систему и импортируете его, PowerShell использует манифест модуля для импорта модуля.

1. При необходимости можно напрямую протестировать манифест модуля с помощью вызова метода [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) , используя точку с этим манифестом.

   `Import-Module .\myModuleName.psd1`

## <a name="module-manifest-elements"></a>Элементы манифеста модуля

В следующей таблице описаны элементы, которые можно включить в манифест модуля.

|Элемент|Значение по умолчанию|Описание|
|-------------|-------------|-----------------|
|**RootModule**<br /> Тип: `String`|`<empty string>`|Модуль скрипта или файл двоичного модуля, связанный с этим манифестом. Предыдущие версии PowerShell вызвали этот элемент **модулетопроцесс**.<br /> Возможные типы для корневого модуля могут быть пустыми, что создает модуль **манифеста** , имя модуля скрипта ( `.psm1` ) или имя двоичного модуля ( `.exe` или `.dll` ). При размещении имени манифеста модуля ( `.psd1` ) или файла скрипта ( `.ps1` ) в этом элементе возникает ошибка. <br /> Например, `RootModule = 'ScriptModule.psm1'`.|
|**ModuleVersion**<br /> Тип: `Version`|`'0.0.1'`|Номер версии этого модуля. Если значение не задано, `New-ModuleManifest`   используется значение по умолчанию. Строка должна иметь возможность преобразования в тип, `Version` например `#.#.#.#.#` . `Import-Module` загружает первый найденный модуль в **$PSModulePath** , который соответствует имени, и имеет по крайней мере **высокое значение в** качестве параметра **MinimumVersion** . Чтобы импортировать определенную версию, используйте `Import-Module` параметр **RequiredVersion** командлета.<br /> Например, `ModuleVersion = '1.0'`.|
|**GUID**<br /> Тип: `GUID`|`'<GUID>'`|Идентификатор, используемый для уникальной идентификации этого модуля. Если значение не указано, `New-ModuleManifest` автоматически создает значение. В настоящее время модуль нельзя импортировать по **идентификатору GUID**. <br /> Например, `GUID = 'cfc45206-1e49-459d-a8ad-5b571ef94857'`.|
|**Автор**<br /> Тип: `String`|`'<Current user>'`|Автор этого модуля. Если значение не указано, `New-ModuleManifest` использует текущего пользователя. <br /> Например, `Author = 'AuthorNameHere'`.|
|**CompanyName**<br /> Тип: `String`|`'Unknown'`|Компания или поставщик этого модуля. Если значение не задано, `New-ModuleManifest` используется значение по умолчанию.<br /> Например, `CompanyName = 'Fabrikam'`.|
|**Авторские права**<br /> Тип: `String`|`'(c) <Author>. All rights reserved.'`| Заявление об авторских правах для этого модуля. Если значение не указано, `New-ModuleManifest` то использует значение по умолчанию с текущим пользователем в качестве `<Author>` . Чтобы указать автора, используйте параметр **Author** . <br /> Например, `Copyright = '2019 AuthorName. All rights reserved.'`.|
|**Описание**<br /> Тип: `String`|`<empty string>`|Описание функциональных возможностей, предоставляемых этим модулем.<br /> Например, `Description = 'This is the module's description.'`.|
|**PowerShellVersion**<br /> Тип: `Version`|`<empty string>`|Минимальная версия модуля PowerShell, необходимая для этого модуля. Допустимые значения: 1,0, 2,0, 3,0, 4,0, 5,0, 5,1, 6 и 7.<br /> Например, `PowerShellVersion = '5.0'`.|
|**повершеллхостнаме**<br /> Тип: `String`|`<empty string>`|Имя узла PowerShell, необходимого для этого модуля. Это имя предоставляется в PowerShell. Чтобы найти имя основной программы, в программе введите: `$host.name` .<br /> Например, `PowerShellHostName = 'ConsoleHost'`.|
|**повершеллхостверсион**<br /> Тип: `Version`|`<empty string>`|Минимальная версия узла PowerShell, необходимая для этого модуля.<br /> Например, `PowerShellHostVersion = '2.0'`.|
|**дотнетфрамеворкверсион**<br /> Тип: `Version`|`<empty string>`|Минимальная версия платформы Microsoft .NET, необходимая для этого модуля. Этот предварительный компонент действителен только для выпуска PowerShell Desktop Edition, например PowerShell 5,1.<br /> Например, `DotNetFrameworkVersion = '3.5'`.|
|**CLRVersion**<br /> Тип: `Version`|`<empty string>`|Минимальная версия среды CLR, необходимая для этого модуля. Этот предварительный компонент действителен только для выпуска PowerShell Desktop Edition, например PowerShell 5,1.<br /> Например, `CLRVersion = '3.5'`.|
|**ProcessorArchitecture**<br /> Тип: `ProcessorArchitecture`|`<empty string>`|Архитектура процессора (отсутствует, x86, AMD64), необходимая для этого модуля. Допустимые значения: x86, AMD64, ARM, IA64, MSIL и None (неизвестный или не указан).<br /> Например, `ProcessorArchitecture = 'x86'`.|
|**RequiredModules**<br /> Тип: `Object[]`|`@()`|Модули, которые необходимо импортировать в глобальную среду перед импортом этого модуля. Это загружает все перечисленные модули, если они еще не загружены. Так, некоторые модули могли быть загружены другим модулем. Можно указать конкретную версию для загрузки с помощью `RequiredVersion` , а не `ModuleVersion` . Когда `ModuleVersion` используется, будет загружена последняя версия, доступная по меньшей мере с указанной версией. В значении параметра строки и хэш-таблицы можно объединять.<br /> Пример: `RequiredModules = @("MyModule", @{ModuleName="MyDependentModule"; ModuleVersion="2.0"; GUID="cfc45206-1e49-459d-a8ad-5b571ef94857"})`<br /> Пример: `RequiredModules = @("MyModule", @{ModuleName="MyDependentModule"; RequiredVersion="1.5"; GUID="cfc45206-1e49-459d-a8ad-5b571ef94857"})`|
|**рекуиредассемблиес**<br /> Тип: `String[]`|`@()`|Сборки, которые должны быть загружены перед импортом этого модуля. Указывает `.dll` имена файлов сборки (), которые требуются для модуля.<br /> PowerShell загружает указанные сборки перед обновлением типов или форматов, импортом вложенных модулей или импортом файла модуля, который указан в значении ключа RootModule. Используйте этот параметр, чтобы получить список всех сборок, необходимых для модуля.<br /> Например, `RequiredAssemblies = @("assembly1.dll", "assembly2.dll", "assembly3.dll")`.|
|**скриптстопроцесс**<br /> Тип: `String[]`|`@()`|Файлы скриптов ( `.ps1` ), которые выполняются в состоянии сеанса вызывающего объекта при импорте модуля. Это может быть глобальное состояние сеанса или, для вложенных модулей, состояние сеанса другого модуля. Эти скрипты можно использовать для подготовки среды точно так же, как в скрипте.<br /> Эти скрипты выполняются до загрузки всех модулей, перечисленных в манифесте. <br /> Например, `ScriptsToProcess = @("script1.ps1", "script2.ps1", "script3.ps1")`.|
|**типестопроцесс**<br /> Тип: `String[]`|`@()`|Файлы типов ( `.ps1xml` ), которые будут загружены при импорте этого модуля. <br /> Например, `TypesToProcess = @("type1.ps1xml", "type2.ps1xml", "type3.ps1xml")`.|
|**форматстопроцесс**<br /> Тип: `String[]`|`@()`|Файлы форматирования ( `.ps1xml` ), которые должны быть загружены при импорте этого модуля. <br /> Например, `FormatsToProcess = @("format1.ps1xml", "format2.ps1xml", "format3.ps1xml")`.|
|**NestedModules**<br /> Тип: `Object[]`|`@()`|Модули для импорта как вложенные модули модуля, указанного в **RootModule** (Alias:**модулетопроцесс**).<br /> Добавление имени модуля в этот элемент аналогично вызову `Import-Module` из скрипта или кода сборки. Основное отличие от использования файла манифеста состоит в том, что проще увидеть, что вы загружаете. Если не удается загрузить модуль, вы еще не загрузили фактический модуль.<br /> Помимо других модулей, здесь также можно загрузить файлы сценариев ( `.ps1` ). Эти файлы будут выполняться в контексте корневого модуля. Это эквивалентно тому, что точка помещает сценарий в корневой модуль. <br /> Например, `NestedModules = @("script.ps1", @{ModuleName="MyModule"; ModuleVersion="1.0.0.0"; GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"})`.|
|**FunctionsToExport**<br /> Тип: `String[]`|`@()`|Указывает функции для экспорта из этого модуля. для лучшей производительности не используйте подстановочные знаки и не удаляйте запись, используйте пустой массив, если нет функций для экспорта. По умолчанию никакие функции не экспортируются. Этот ключ можно использовать для перечисления функций, экспортируемых модулем.<br /> Модуль экспортирует функции в состояние сеанса вызывающего объекта. Состояние сеанса вызывающего объекта может быть глобальным состоянием сеанса или, для вложенных модулей, состояние сеанса другого модуля. При создании цепочки вложенных модулей все функции, экспортированные вложенным модулем, будут экспортированы в глобальное состояние сеанса, если только модуль в цепочке не будет ограничивать функцию с помощью ключа **FunctionsToExport** .<br /> Если манифест экспортирует псевдонимы для функций, этот ключ может удалить функции, псевдонимы которых перечислены в ключе **алиасестоекспорт** , но этот ключ не может добавлять в список псевдонимы функций. <br /> Например, `FunctionsToExport = @("function1", "function2", "function3")`.|
|**CmdletsToExport**<br /> Тип: `String[]`|`@()`|Указывает командлеты для экспорта из этого модуля. для лучшей производительности не используйте подстановочные знаки и не удаляйте запись, используйте пустой массив, если нет командлетов для экспорта. По умолчанию командлеты не экспортируются. Этот ключ можно использовать для перечисления командлетов, экспортируемых модулем.<br /> Состояние сеанса вызывающего объекта может быть глобальным состоянием сеанса или, для вложенных модулей, состояние сеанса другого модуля. При цепочке вложенных модулей все командлеты, экспортированные вложенным модулем, будут экспортированы в глобальное состояние сеанса, если только модуль в цепочке не будет ограничивать командлет с помощью ключа **CmdletsToExport** .<br /> Если манифест экспортирует псевдонимы для командлетов, этот ключ может удалить командлеты, псевдонимы которых перечислены в ключе **алиасестоекспорт** , но этот раздел не может добавлять псевдонимы командлетов в список. <br /> Например, `CmdletsToExport = @("Get-MyCmdlet", "Set-MyCmdlet", "Test-MyCmdlet")`.|
|**вариаблестоекспорт**<br /> Тип: `String[]`|`'*'`|Задает переменные, которые модуль экспортирует в состояние сеанса вызывающего объекта. Можно использовать подстановочные знаки. По умолчанию экспортируются все переменные ( `'*'` ). Этот ключ можно использовать для ограничения переменных, экспортируемых модулем.<br /> Состояние сеанса вызывающего объекта может быть глобальным состоянием сеанса или, для вложенных модулей, состояние сеанса другого модуля. При цепочке вложенных модулей все переменные, экспортированные вложенным модулем, будут экспортированы в глобальное состояние сеанса, если только модуль в цепочке не будет ограничивать переменную с помощью ключа **вариаблестоекспорт** .<br /> Если манифест также экспортирует псевдонимы для переменных, этот ключ может удалить переменные, псевдонимы которых перечислены в ключе **алиасестоекспорт** , но этот ключ не может добавлять в список псевдонимы переменных. <br /> Например, `VariablesToExport = @('$MyVariable1', '$MyVariable2', '$MyVariable3')`.|
|**алиасестоекспорт**<br /> Тип: `String[]`|`@()`|Указывает псевдонимы для экспорта из этого модуля. для лучшей производительности не используйте подстановочные знаки и не удаляйте запись, используйте пустой массив, если нет псевдонимов для экспорта. По умолчанию никакие псевдонимы не экспортируются. Этот ключ можно использовать для перечисления псевдонимов, экспортируемых модулем.<br /> Модуль экспортирует псевдонимы в состояние сеанса вызывающего объекта. Состояние сеанса вызывающего объекта может быть глобальным состоянием сеанса или, для вложенных модулей, состояние сеанса другого модуля. При создании цепочки вложенных модулей все псевдонимы, экспортированные вложенным модулем, будут в конечном итоге экспортироваться в глобальное состояние сеанса, если только модуль в цепочке не будет ограничивать псевдоним с помощью ключа **алиасестоекспорт** . <br /> Например, `AliasesToExport = @("MyAlias1", "MyAlias2", "MyAlias3")`.|
|**DscResourcesToExport**<br /> Тип: `String[]`|`@()`|Указывает ресурсы DSC для экспорта из этого модуля. Разрешено использовать подстановочные знаки. <br /> Например, `DscResourcesToExport = @("DscResource1", "DscResource2", "DscResource3")`.|
|**модулелист**<br /> Тип: `Object[]`|`@()`|Указывает все модули, Упакованные в этот модуль. Эти модули можно вводить по имени, используя строку с разделителями-запятыми или хэш-таблицу с ключами **ModuleName** и **GUID** . Хэш-таблица может также иметь **необязательный** ключ «ключом». Ключ **модулелист** предназначен для выполнения функций инвентаризации модуля. Эти модули не обрабатываются автоматически. <br /> Например, `ModuleList = @("SampleModule", "MyModule", @{ModuleName="MyModule"; ModuleVersion="1.0.0.0"; GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"})`.|
|**Список файлов**<br /> Тип: `String[]`|`@()`|Список всех файлов, упакованных с помощью этого модуля. Как и в случае с **модулелист**, **FileList** — это список инвентаризации, который в противном случае не обрабатывается. <br /> Например, `FileList = @("File1", "File2", "File3")`.|
|**PrivateData**<br /> Тип: `Object`|`@{...}`|Указывает все закрытые данные, которые необходимо передать в корневой модуль, заданный ключом **RootModule** (Alias: **модулетопроцесс**). **PrivateData** — это хэш-таблица, состоящая из нескольких элементов: **Tags**, **LicenseUri**, **ProjectURI**, **IconUri**, **ReleaseNotes**, **Предварительный выпуск**, **RequireLicenseAcceptance** и **екстерналмодуледепенденЦиес**. |
|**Теги** <br /> Тип: `String[]` |`@()`| Теги помогают при поиске модулей в онлайн-галереях. <br /> Например, `Tags = "PackageManagement", "PowerShell", "Manifest"`.|
|**LicenseUri**<br /> Тип: `Uri` |`<empty string>`| URL-адрес лицензии для этого модуля. <br /> Например, `LicenseUri = 'https://www.contoso.com/license'`.|
|**ProjectUri**<br /> Тип: `Uri` |`<empty string>`| URL-адрес основного веб-сайта для этого проекта. <br /> Например, `ProjectUri = 'https://www.contoso.com/project'`.|
|**IconUri**<br /> Тип: `Uri` |`<empty string>`| URL-адрес значка, представляющего этот модуль. <br /> Например, `IconUri = 'https://www.contoso.com/icons/icon.png'`.|
|**ReleaseNotes**<br /> Тип: `String` |`<empty string>`| Указывает заметки о выпуске модуля. <br /> Например, `ReleaseNotes = 'The release notes provide information about the module.`.|
|**Предварительной**<br /> Тип: `String` |`<empty string>`| Этот параметр был добавлен в PowerShellGet 1.6.6. Строка **предварительной** версии, которая определяет модуль как предварительную версию в онлайн-галереях. <br /> Например, `PreRelease = 'This module is a prerelease version.`.|
|**RequireLicenseAcceptance**<br /> Тип: `Boolean`|`$true`| Этот параметр был добавлен в PowerShellGet 1,5. Флаг, указывающий, требует ли модуль явное согласие пользователя на установку, обновление или сохранение. <br /> Например, `RequireLicenseAcceptance = $false`.|
|**екстерналмодуледепенденЦиес**<br /> Тип: `String[]` |`@()`| Этот параметр был добавлен в PowerShellGet v2. Список внешних модулей, от которых зависит этот модуль. <br /> Например, `ExternalModuleDependencies =  @("ExtModule1", "ExtModule2", "ExtModule3")`.|
|**HelpInfoURI**<br /> Тип: `String`|`<empty string>`|Универсальный код ресурса (URI) HelpInfo этого модуля. <br /> Например, `HelpInfoURI = 'https://www.contoso.com/help'`.|
|**DefaultCommandPrefix**<br /> Тип: `String`|`<empty string>`|Префикс по умолчанию для команд, экспортированных из этого модуля. Переопределите префикс по умолчанию с помощью `Import-Module -Prefix` . <br /> Например, `DefaultCommandPrefix = 'My'`.|

## <a name="sample-module-manifest"></a>Пример манифеста модуля

Следующий пример манифеста модуля был создан `New-ModuleManifest` в PowerShell 7 и содержит ключи и значения по умолчанию.

```powershell
#
# Module manifest for module 'SampleModuleManifest'
#
# Generated by: User01
#
# Generated on: 10/15/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'b632e90c-df3d-4340-9f6c-3b832646bf87'

# Author of this module
Author = 'User01'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) User01. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

        # Prerelease string of this module
        # Prerelease = ''

        # Flag to indicate whether the module requires explicit user acceptance for install/update/save
        RequireLicenseAcceptance = $true

        # External dependent modules of this module
        # ExternalModuleDependencies = @()

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

## <a name="see-also"></a>См. также раздел

[about_Comparison_Operators](/powershell/module/microsoft.powershell.core/about/about_comparison_operators)

[about_If](/powershell/module/microsoft.powershell.core/about/about_if)

[Глобальный кэш сборок](/dotnet/framework/app-domains/gac)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[New-ModuleManifest](/powershell/module/microsoft.powershell.core/new-modulemanifest)

[Test-ModuleManifest](/powershell/module/microsoft.powershell.core/test-modulemanifest)

[Update-ModuleManifest](/powershell/module/powershellget/update-modulemanifest)

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
