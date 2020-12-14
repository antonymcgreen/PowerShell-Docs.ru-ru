---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 2ad1f5991920cecf0a5b494bde698510c1c55b94
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890810"
---
# Update-ModuleManifest

## Краткий обзор
Обновляет файл манифеста модуля.

## SYNTAX

### Все

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Update-ModuleManifest`Командлет обновляет файл манифеста модуля ( `.psd1` ).

## Примеры

### Пример 1. Обновление манифеста модуля

В этом примере обновляется существующий файл манифеста модуля. Сплаттинг используется для передачи значений параметров в `Update-ModuleManifest` . Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

`$Parms` — Это со звездочкой, в котором хранятся значения параметров для **пути**, **автора**, **CompanyName** и **авторских прав**. `Update-ModuleManifest` Возвращает значения параметров из `@Parms` и обновляет манифест модуля **TestManifest.psd1**.

## PARAMETERS

### -Алиасестоекспорт

Задает экспортируемые модулем псевдонимы. Разрешено использовать подстановочные знаки.

Используйте этот параметр, чтобы ограничить псевдонимы, экспортируемые модулем. **Алиасестоекспорт** может удалять псевдонимы из списка экспортируемых псевдонимов, но не может добавлять в список псевдонимы.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Author

Задает автора модуля.

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

### -ClrVersion

Задает минимальную версию среды CLR платформы Microsoft .NET Framework, которая требуется для работы модуля.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CmdletsToExport

Задает экспортируемые модулем командлеты. Разрешено использовать подстановочные знаки.

Используйте этот параметр, чтобы ограничить командлеты, экспортируемые модулем. **CmdletsToExport** может удалять командлеты из списка экспортированных командлетов, но не может добавлять командлеты в список.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -CompanyName

Указывает компанию или поставщика, создавшего модуль.

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

### -CompatiblePSEditions

Указывает совместимый **PSEditions** модуля. Сведения о **PSEdition** см. [в разделе модули с совместимыми выпусками PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед запуском `Update-ModuleManifest` .

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

### -Copyright

Задает заявление об авторских правах на модуль.

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

### -DefaultCommandPrefix

Указывает префикс команды по умолчанию.

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

### -Description

Задает описание модуля.

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

### -Дотнетфрамеворкверсион

Указывает минимальную версию платформу Microsoft .NET, которая требуется для работы модуля.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DscResourcesToExport

Указывает ресурсы настройки требуемого состояния (DSC), которые экспортирует модуль. Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ЕкстерналмодуледепенденЦиес

Указывает массив зависимостей внешних модулей.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileList

Задает все элементы, включенные в модуль.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatsToProcess

Задает файлы форматирования ( `.ps1xml` ), которые выполняются при импорте модуля.

При импорте модуля PowerShell запускает `Update-FormatData` командлет с указанными файлами.
Так как файлы форматирования не находятся в области, они влияют на все состояния сеанса в сеансе.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionsToExport

Задает экспортируемые модулем функции. Разрешено использовать подстановочные знаки.

Используйте этот параметр, чтобы ограничить функции, экспортируемые модулем. **FunctionsToExport** может удалять функции из списка экспортируемых псевдонимов, но не может добавлять функции в список.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Guid

Задает уникальный идентификатор модуля. GUID позволяет отличать модули с одинаковыми именами.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HelpInfoUri

Указывает адрес **XML-** файла модуля HelpInfo в Интернете. Введите универсальный код ресурса (URI), который начинается с **http** или **HTTPS**.

**XML-файл HelpInfo** поддерживает функцию обновляемой справки, которая появилась в PowerShell версии 3,0. Он содержит сведения о расположении загружаемых файлов справки модуля и номера версий самых новых файлов справки для каждого поддерживаемого языкового стандарта.

Сведения об обновляемой справке см. в разделе [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).
Сведения о **XML-файле HelpInfo** см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IconUri

Задает URL-адрес значка для модуля. Указанный значок отображается на веб-странице коллекции модуля.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseUri

Указывает URL-адрес условий лицензирования для модуля.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Модулелист

Указывает массив модулей, которые включены в модуль.

Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion**. Хэш-таблица может иметь дополнительный ключ **GUID**. В значении параметра строки и хэш-таблицы можно объединять.

Этот ключ выполняет функцию полного списка ресурсов модуля. Модули, указанные в значении этого ключа, не обрабатываются автоматически.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Истечение

Указывает версию модуля.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NestedModules

Задает модули скрипта ( `.psm1` ) и двоичные модули ( `.dll` ), которые импортируются в состояние сеанса модуля. Файлы в ключе **NestedModules** выполняются в том порядке, в котором они указаны в значении.

Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion**. Хэш-таблица может иметь дополнительный ключ **GUID**. В значении параметра строки и хэш-таблицы можно объединять.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Паккажеманажементпровидерс

Указывает массив поставщиков управления пакетами.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым выполняется работа. По умолчанию `Update-ModuleManifest` не создает никаких выходных данных.

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

### -Path

Указывает путь и имя файла манифеста модуля. Введите путь и имя файла с `.psd1` расширением имени файла, например `$PSHOME\Modules\MyModule\MyModule.psd1` .

При указании пути к существующему файлу `Update-ModuleManifest` заменяет файл без предупреждения, если только файл не имеет атрибута только для чтения.

Манифест должен находиться в каталоге модуля, а имя файла манифеста должно совпадать с именем каталога модуля, но с `.psd1` расширением.

`$PSHOME` `$HOME` В ответ на запрос значения параметра **path** нельзя использовать переменные, например или. Чтобы использовать переменную, включите параметр **Path** в команду.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Повершеллхостнаме

Указывает имя основной программы PowerShell, требуемой для модуля. Введите имя основной программы, например, узел интегрированной среды сценариев PowerShell или ConsoleHost. Подстановочные знаки не допускаются.

Чтобы найти имя основной программы, в программе введите `$Host.Name` .

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

### -Повершеллхостверсион

Указывает минимальную версию основной программы PowerShell, которая работает с модулем. Введите номер версии, например, 1.1.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellVersion

Указывает минимальную версию PowerShell, которая будет работать с этим модулем. Например, в качестве значения этого параметра можно указать 3,0, 4,0 или 5,0.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Предварительный выпуск

Указывает, что модуль является предварительным выпуском.

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

### -PrivateData

Указывает данные, которые передаются в модуль при его импорте.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessorArchitecture

Указывает архитектуру процессора, необходимую для этого модуля.

Допустимые значения для этого параметра:

- AMD64
- Arm
- IA64
- MSIL
- Нет (неизвестно или не указано)
- X86

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectUri

Указывает URL веб-страницы об этом проекте.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReleaseNotes

Указывает массив строк, содержащий заметки о выпуске или комментарии, которые должны быть доступны для данной версии скрипта.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рекуиредассемблиес

Указывает файлы сборки ( `.dll` ), необходимые для работы модуля. Введите имена файлов сборки.
PowerShell загружает указанные сборки перед обновлением типов или форматов, импортом вложенных модулей или импортом файла модуля, который указан в значении ключа **RootModule** .

Используйте этот параметр, чтобы указать все сборки, необходимые для работы модуля, включая сборки, которые должны быть загружены для обновления любых файлов форматирования или типов, перечисленных в ключах **форматстопроцесс** или **типестопроцесс** , даже если эти сборки также указаны как двоичные модули в ключе **NestedModules** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredModules

Определяет модули, которые должны присутствовать в глобальном состоянии сеанса. Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их. Если требуемые модули недоступны, `Import-Module` команда завершается ошибкой.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireLicenseAcceptance

Указывает, что для модуля требуется принятие условий лицензии.

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

### -RootModule

Указывает первичный или корневой файл модуля. Введите имя файла скрипта ( `.ps1` ), модуля скрипта ( `.psm1` ), манифеста модуля ( `.psd1` ), сборки ( `.dll` ), XML-файла определения командлета ( `.cdxml` ) или рабочего процесса ( `.xaml` ). При импорте модуля элементы, экспортируемые из корневого файла модуля, импортируются в состояние сеанса вызывающего объекта.

Если у модуля есть файл манифеста и корневой файл не указан в ключе **RootModule** , манифест станет первичным файлом для модуля. И модуль превращается в модуль манифеста (ModuleType = manifest).

Чтобы экспортировать элементы из `.psm1` `.dll` файла или в модуль с манифестом, имена этих файлов должны быть указаны в значениях ключей **RootModule** или **NestedModules** в манифесте. В противном случае их члены не экспортируются.

В PowerShell 2,0 этот ключ назывался **модулетопроцесс**.

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

### -ScriptsToProcess

Указывает файлы скрипта ( `.ps1` ), которые выполняются в состоянии сеанса вызывающего объекта при импорте модуля.
Эти скрипты можно использовать для подготовки среды таким же образом, как и скрипт входа в систему.

Чтобы указать скрипты, которые будут выполняться в состоянии сеанса модуля, используйте ключ **NestedModules**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Теги

Задает массив тегов.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypesToProcess

Указывает файлы типов ( `.ps1xml` ), которые выполняются при импорте модуля.

При импорте модуля PowerShell запускает `Update-TypeData` командлет с указанными файлами.
Так как файлы типов не находятся в области, они влияют на все состояния сеанса в сеансе.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вариаблестоекспорт

Задает экспортируемые модулем переменные. Разрешено использовать подстановочные знаки.

Используйте этот параметр, чтобы ограничить переменные, экспортируемые модулем. **Вариаблестоекспорт** может удалять переменные из списка экспортированных переменных, но не может добавлять переменные в список.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -WhatIf

Показывает, что произойдет при `Update-ModuleManifest` запуске. Командлет не выполняется.

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

### System.String

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

> [!IMPORTANT]
> По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1. Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка. Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.

## Связанные ссылки
