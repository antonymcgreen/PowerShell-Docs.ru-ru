---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 42a2b37144d9af188a7204500227fddf4827bdf9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228921"
---
# Update-Module

## Краткий обзор
Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.

## SYNTAX

### Все

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Update-Module`Командлет устанавливает последнюю версию модуля из веб-коллекции. Перед установкой появится запрос на подтверждение обновления. Обновления устанавливаются только для модулей, установленных на локальном компьютере с `Install-Module` . `Update-Module` выполняет поиск `$env:PSModulePath` установленных модулей.

`Update-Module` без указания параметров обновляет все установленные модули. Чтобы указать обновляемый модуль, используйте параметр **Name** . Можно выполнить обновление до определенной версии модуля с помощью параметра **RequiredVersion** .

Если установленный модуль уже является последней версией, модуль не обновляется. Если модуль не найден в `$env:PSModulePath` , выводится сообщение об ошибке.

Чтобы отобразить установленные модули, используйте `Get-InstalledModule` .

## Примеры

### Пример 1. обновление всех модулей

В этом примере все установленные модули обновляются до последней версии в интерактивной коллекции.

```powershell
Update-Module
```

### Пример 2. обновление модуля по имени

В этом примере заданный модуль обновляется до последней версии в интерактивной коллекции.

```powershell
Update-Module -Name SpeculationControl
```

`Update-Module` использует параметр **Name** для обновления конкретного модуля **спекулатионконтрол** .

### Пример 3. Просмотр Update-Module запусков

В этом примере сценарий "что если" показывает, что происходит при `Update-Module` запуске. Команда не выполняется.

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

`Update-Module` использует параметр **WhatIf** , чтобы отобразить, что произойдет при `Update-Module` запуске.

### Пример 4. обновление модуля до указанной версии

В этом примере модуль обновляется до определенной версии. Версия должна существовать в интерактивной коллекции, или отображается ошибка.

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол** . Параметр **RequiredVersion** указывает версию **1.0.14** .

### Пример 5. обновление модуля без подтверждения

В этом примере не запрашивается подтверждение для обновления модуля до последней версии из интерактивной коллекции. Если модуль уже установлен, параметр **Force** переустанавливает модуль.

```powershell
Update-Module -Name SpeculationControl -Force
```

`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол** . Параметр **Force** обновляет модуль без запроса подтверждения пользователя.

## PARAMETERS

### -AcceptLicense

Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.

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

### -AllowPrerelease

Позволяет обновить модуль, используя новый модуль, помеченный как предварительный выпуск.

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

### -Confirm

Запрашивает подтверждение перед запуском `Update-Module` .

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

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на обновление модуля.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Принудительно обновляет каждый указанный модуль без запроса на подтверждение. Если модуль уже установлен, **принудительно** переустанавливает модуль.

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

### -MaximumVersion

Указывает максимальную версию одного модуля для обновления. Вы не можете добавить этот параметр, если пытаетесь обновить несколько модулей. Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имена одного или нескольких модулей для обновления. `Update-Module` выполняет поиск `$env:PSModulePath` модулей для обновления. Если в `$env:PSModulePath` для указанного имени модуля не найдено совпадений, возникает ошибка.

Подстановочные знаки принимаются в именах модулей. Если добавить подстановочные знаки к указанному имени и совпадений не найдено, ошибка не возникает.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете. По умолчанию этот командлет не создает выходные данные.

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

### Прокси-сервер

Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Указывает точную версию, до которой будет обновлен существующий установленный модуль. Версия, указанная в параметре **RequiredVersion** , должна существовать в интерактивной коллекции, иначе отображается ошибка. Если в одной команде обновляется несколько модулей, нельзя использовать **RequiredVersion** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope

Задает область установки модуля. Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser** . Если **область** не указана, обновление устанавливается в области **CurrentUser** .

Область **ALLUSERS** требует повышенных разрешений и устанавливает модули в расположение, доступное всем пользователям компьютера:

`$env:ProgramFiles\PowerShell\Modules`

Параметр **CurrentUser** не требует повышенных разрешений и устанавливает модули в расположении, доступном только текущему пользователю компьютера:

`$home\Documents\PowerShell\Modules`

Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.

- В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser** , что не требует повышения прав для установки.
- В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS** , что требует повышения прав для установки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при `Update-Module` запуске. Командлет не выполняется.

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

### System.String[]

### System.String

### System.Management.Automation.PSCredential

### System.Uri

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

Для PowerShell версии 6,0 и более поздней областью установки по умолчанию всегда является **CurrentUser** .
Обновления модулей для **CurrentUser** , `$home\Documents\PowerShell\Modules` не требуют повышенных разрешений. Обновления модулей для **ALLUSERS** , `$env:ProgramFiles\PowerShell\Modules` требуют повышенных разрешений.

`Update-Module` работает в PowerShell 3,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.

Если модуль, указанный с параметром **Name** , не был установлен с помощью `Install-Module` , возникает ошибка.

Вы можете работать только с `Update-Module` модулями, установленными из коллекции в Интернете, запустив `Install-Module` .

При `Update-Module` попытке обновить двоичные файлы, которые используются, `Update-Module` возвращает ошибку, определяющую проблемные процессы. Пользователю будет сообщено повторить попытку `Update-Module` после остановки процессов.

## Связанные ссылки

[Find-Module](Find-Module.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Uninstall-Module](Uninstall-Module.md)
