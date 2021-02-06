---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: f4fcf349c439baf4813c37af4bf56c26a46c7877
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604727"
---
# Install-Module

## Краткий обзор
Скачивает один или несколько модулей из репозитория и устанавливает их на локальный компьютер.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Install-Module`Командлет возвращает один или несколько модулей, соответствующих указанным критериям из Интернет-репозитория. Командлет проверяет, что результаты поиска являются допустимыми модулями, и копирует папки модулей в расположение установки. Установленные модули не импортируются автоматически после установки.
Вы можете отфильтровать, какой модуль установлен на основе минимальной, максимальной и точной версий указанных модулей.

Если устанавливаемый модуль имеет то же имя или версию или содержит команды в существующем модуле, отображаются предупреждающие сообщения. Убедившись, что вы хотите установить модуль и переопределить предупреждения, используйте `-Force` `-AllowClobber` Параметры и. В зависимости от параметров репозитория может потребоваться ответить на запрос установки модуля, чтобы продолжить.

В этих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория. `Get-PSRepository` отображает зарегистрированные репозитории. Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.

## Примеры

### Пример 1. Поиск и установка модуля

В этом примере выполняется поиск модуля в репозитории и установка модуля.

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

`Find-Module`Использует параметр **Name** для указания модуля **PowerShellGet** . По умолчанию последняя версия модуля загружается из репозитория. Объект отправляется по конвейеру в `Install-Module` командлет. `Install-Module` устанавливает модуль для всех пользователей в `$env:ProgramFiles\PowerShell\Modules` .

### Пример 2. Установка модуля по имени

В этом примере установлена последняя версия модуля **PowerShellGet** .

```powershell
Install-Module -Name PowerShellGet
```

`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** . По умолчанию последняя версия модуля загружается из репозитория и устанавливается.

### Пример 3. Установка модуля с использованием минимальной версии

В этом примере устанавливается минимальная версия модуля **PowerShellGet** . Параметр **MinimumVersion** указывает самую раннюю версию модуля, который следует установить. Если доступна более новая версия модуля, эта версия скачивается и устанавливается для всех пользователей.

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** . Параметр **MinimumVersion** указывает, что версия **2.0.1** загружается из репозитория и устанавливается. Так как доступна версия **2.0.4** , эта версия скачивается и устанавливается для всех пользователей.

### Пример 4. Установка определенной версии модуля

В этом примере устанавливается определенная версия модуля **PowerShellGet** .

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** . Параметр **RequiredVersion** указывает, что версия **2.0.0** скачивается и устанавливается для всех пользователей.

### Пример 5. Установка модуля только для текущего пользователя

В этом примере загружается и устанавливается последняя версия модуля только для текущего пользователя.

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .
`Install-Module` скачивает и устанавливает последнюю версию **PowerShellGet** в каталог текущего пользователя `$home\Documents\PowerShell\Modules` .

## PARAMETERS

### -AcceptLicense

Для модулей, для которых требуется лицензия, **AcceptLicense** автоматически принимает лицензионное соглашение во время установки. Дополнительные сведения см. в разделе [модули, требующие принятия условий лицензии](/powershell/scripting/gallery/concepts/module-license-acceptance).

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

### -AllowClobber

Переопределяет предупреждающие сообщения о конфликтах установки существующих команд на компьютере.
Перезаписывает существующие команды, имена которых совпадают с именами команд, устанавливаемых модулем.
**AllowClobber** и **Force** можно использовать вместе в `Install-Module` команде.

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

Позволяет установить модуль, помеченный как предварительный выпуск.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед запуском `Install-Module` командлета.

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

Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.

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

Устанавливает модуль и переопределяет предупреждающие сообщения о конфликтах при установке модулей. Если на компьютере уже существует модуль с таким именем, **принудительно** установите несколько версий. Если имеется существующий модуль с тем же именем и версией, **принудительно** перезаписывает эту версию. **Force** и **AllowClobber** можно использовать вместе в `Install-Module` команде.

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

### -InputObject

Используется для входных данных конвейера.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Указывает максимальную версию одного модуля для установки. Установленная версия должна быть меньше или равна **MaximumVersion**. Если вы хотите установить несколько модулей, вы не сможете использовать **MaximumVersion**. В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** `Install-Module` .

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Указывает минимальную версию отдельного модуля для установки. Установленная версия должна быть больше или равна **MinimumVersion**. Если доступен более новая версия модуля, устанавливается более новая версия. Если требуется установить несколько модулей, нельзя использовать параметр **MinimumVersion**.
В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** `Install-Module` .

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает точные имена модулей для установки из Интернет-коллекции. Принимается список имен модулей с разделителями-запятыми. Имя модуля должно совпадать с именем модуля в репозитории. Используйте `Find-Module` для получения списка имен модулей.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

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

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.

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

### — Репозиторий;

Используйте параметр **репозитория** , чтобы указать, какой репозиторий используется для скачивания и установки модуля. Используется при регистрации нескольких репозиториев. Указывает имя зарегистрированного репозитория в `Install-Module` команде. Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` .
Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Указывает точную версию отдельного модуля для установки. Если в репозитории для указанной версии нет совпадения, выводится сообщение об ошибке. Если требуется установить несколько модулей, нельзя использовать **RequiredVersion**. Параметр **RequiredVersion** нельзя использовать в той же `Install-Module` команде, что и **MinimumVersion** или **MaximumVersion**.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope

Задает область установки модуля. Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser**.

Область **ALLUSERS** устанавливает модули в расположение, доступное всем пользователям компьютера:

`$env:ProgramFiles\PowerShell\Modules`

Параметр **CurrentUser** устанавливает модули в расположение, доступное только текущему пользователю компьютера. Пример:

`$home\Documents\PowerShell\Modules`

Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.

- В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser**, что не требует повышения прав для установки.
- В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS**, что требует повышения прав для установки.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скиппублишерчекк

Позволяет установить более новую версию модуля, который уже существует на компьютере. Например, если существующий модуль подписан цифровой подписью доверенного издателя, но в новой версии нет цифровой подписи доверенного издателя.

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

### -WhatIf

Показывает, что произойдет при `Install-Module` выполнении команды. Командлет не выполняется.

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

### PSRepositoryItemInfo

`Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` .

### System.String[]

### System. Management. Automation. PSObject []

### System.String

### System.Management.Automation.PSCredential

### System.Uri

## Выходные данные

### Microsoft. PowerShell. Commands. PSRepositoryItemInfo

При использовании параметра **PassThru** `Install-Module` выводит объект **PSRepositoryItemInfo** для модуля. Это те же сведения, которые вы получаете из `Find-Module` командлета.

## ПРИМЕЧАНИЯ

`Install-Module` работает в PowerShell 5,0 или более поздних версиях, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.

> [!IMPORTANT]
> Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1. Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка. Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.

В целях безопасности рекомендуется оценивать код модуля перед первым запуском командлетов или функций. Чтобы предотвратить выполнение модулей, содержащих вредоносный код, установленные модули не импортируются автоматически после установки.

Если имя модуля, указанное в параметре **Name** , не существует в репозитории, `Install-Module` возвращает ошибку.

Чтобы установить несколько модулей, используйте параметр **Name** и укажите разделенный запятыми массив имен модулей. При указании нескольких имен модулей нельзя использовать **MinimumVersion**, **MaximumVersion** или **RequiredVersion**. `Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` . Конвейер — это еще один способ указать несколько модулей для установки в одной команде.

По умолчанию модули для области **ALLUSERS** устанавливаются в `$env:ProgramFiles\PowerShell\Modules` . Значение по умолчанию предотвращает путаницу при установке ресурсов DSC для требуемого состояния.

Установка модуля завершается сбоем и не может быть импортирована, если в `.psm1` `.psd1` папке отсутствует имя, или `.dll` . Для установки модуля используйте параметр **Force** .

Если версия существующего модуля совпадает с именем, указанным в параметре **Name** , а параметр **MinimumVersion** или **RequiredVersion** не используется, `Install-Module` Автоматическое продолжение не выполняется, но не устанавливает модуль.

Если версия существующего модуля больше значения параметра **MinimumVersion** или равна значению параметра **RequiredVersion** , `Install-Module` Автоматическое продолжение сохраняется, но не устанавливает модуль.

Если существующий модуль не соответствует значениям, указанным в параметрах **MinimumVersion** или **RequiredVersion** , в команде возникает ошибка `Install-Module` . Например, если версия существующего установленного модуля ниже значения **MinimumVersion** или не равна значению **RequiredVersion** .

При установке модуля будут также установлены все зависимые модули, указанные в соответствии с требованиями издателя модуля.
Издатель укажет необходимые модули и их версии в манифесте модуля.

## Связанные ссылки

[Find-Module](Find-Module.md)

[Get-PSRepository](Get-PSRepository.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Publish-Module](Publish-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[about_Module](../Microsoft.PowerShell.Core/About/about_Modules.md)
