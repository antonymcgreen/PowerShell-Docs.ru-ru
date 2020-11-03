---
description: Описание новых функций, которые входят в Windows PowerShell 5,1.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233118"
---
# <a name="about_windows_powershell_51"></a>about_Windows_PowerShell_5.1

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описание новых функций, которые входят в Windows PowerShell 5,1.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Windows PowerShell 5,1 включает в себя значительные новые функции, расширяющие возможности использования, улучшая удобство использования и позволяя более легко и полно управлять средами на основе Windows и управлять ими.

Windows PowerShell 5,1 обеспечивает обратную совместимость. Командлеты, поставщики, модули, оснастки, сценарии, функции и профили, разработанные для Windows PowerShell 4,0, Windows PowerShell 3,0 и Windows PowerShell 2,0, обычно работают в Windows PowerShell 5,1 без изменений.

- Новые командлеты: локальные пользователи и группы; Get-ComputerInfo.
- Улучшения PowerShellGet включают принудительное подписание модулей и установку модулей JEA.
- Дополнительная поддержка PackageManagement для контейнеров, установка CBS, установка на основе EXE, пакеты CAB.
- Улучшения отладки для классов DSC и PowerShell.
- Улучшения для системы безопасности, включая принудительное использование модулей, подписанных каталогом и полученных от опрашивающего сервера, а также при использовании командлетов PowerShellGet.
- Ответы на разные запросы пользователей и решение проблем.

Windows PowerShell 5,1 устанавливается по умолчанию в Windows Server 2016 и Windows 10. Чтобы установить Windows PowerShell 5,1 на Windows Server 2012 R2, Windows 8.1 Enterprise или Windows 8.1 Pro, см. статью [Установка и настройка WMF 5,1](/powershell/scripting/wmf/setup/install-configure).
Перед установкой Windows Management Framework 5,1 обязательно прочтите сведения о скачивании и выполните все требования к системе.

Вы также можете ознакомиться с изменениями в Windows PowerShell 5,1 в статье [новые возможности Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).

## <a name="new-scenarios-and-features-in-wmf-51"></a>Новые сценарии и возможности в WMF 5.1

> Примечание. Эта информация является предварительной и может быть изменена.

### <a name="powershell-editions"></a>Выпуски PowerShell
Начиная с версии 5.1, среда PowerShell доступна в разных выпусках, обладающих различными наборами функций и совместимостью с платформами.

- **Выпуск Desktop** создан на базе платформы .NET Framework и обеспечивает совместимость со скриптами и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.
- **Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

**Дополнительные сведения об использовании выпусков PowerShell**

- [Определение запущенного выпуска PowerShell с использованием $PSVersionTable](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [Фильтрация результатов командлета Get-Module по CompatiblePSEditions с помощью параметра PSEdition](/powershell/module/microsoft.powershell.core/get-module)
- [Запрет на выполнение сценариев в несовместимых выпусках PowerShell](/powershell/scripting/gallery/concepts/script-psedition-support)
- [Объявление совместимости модуля с определенными версиями PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a>Командлеты для работы с каталогами

Мы добавили два новых командлета для создания и проверки файлов каталога Windows в модуль [Microsoft.Powershell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)).

#### <a name="new-filecatalog"></a>New-FileCatalog

Командлет New-FileCatalog создает файл каталога Windows для набора файлов и папок.
Файл каталога содержит хэши для всех файлов, находящихся по указанным путям. Пользователь может распространять набор папок вместе с соответствующим файлом каталога, представляющим этих папки. С помощью файла каталога получатель может проверить, были ли изменены папки с момента создания каталога.

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

Поддерживаются каталоги версий 1 и 2. В версии 1 для создания хэшей файлов используется алгоритм хэширования SHA1, в версии 2 — SHA256. Каталог версии 2 не поддерживается в *Windows Server 2008 R2* и *Windows 7* . На платформах *Windows 8* , *Windows Server 2012* и более поздней версии рекомендуется использовать каталог версии 2.

Для проверки целостности файла каталога (Pester.cat в приведенном выше примере) его нужно подписать с помощью командлета [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature).

#### <a name="test-filecatalog"></a>Test-FileCatalog

Командлет Test-FileCatalog проверяет каталог, представляющий набор папок.

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

Этот командлет сравнивает все хэши файлов и их относительные пути в *каталоге* с хэшами и относительными путями на *диске* . При обнаружении любого несоответствия между хэшами файлов и путями он возвращает состояние *ValidationFailed* . Все эти данные можно получить с помощью параметра *-Detailed* . Командлет также отображает состояние подписи каталога в свойстве *Signature* . Подпись также можно определить, вызвав командлет [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) и указав файл каталога. Также можно исключить любые файлы из проверки, указав их в параметре *-FilesToSkip* .

### <a name="module-analysis-cache"></a>Кэш анализа модуля

Начиная с версии WMF 5.1 среда PowerShell предоставляет средства управления файлом, в котором кэшируются сведения о модуле, например экспортируемые им команды.

По умолчанию этот кэш хранится в файле `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`. Кэш обычно считывается при запуске в процессе поиска команды и записывается в фоновом потоке через некоторое время после импорта модуля.

Чтобы изменить расположение кэша по умолчанию, присвойте значение переменной среды `$env:PSModuleAnalysisCachePath` перед запуском PowerShell. Изменения, вносимые в эту переменную среды, влияют только на дочерние процессы. Значение должно быть полным путем (включая имя файла), на создание и запись файлов по которому у среды PowerShell есть разрешение. Чтобы отключить файловый кэш, укажите в качестве этого значения недопустимое расположение, например:

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

Таким образом задается путь к недопустимому устройству. Если среда PowerShell не может осуществлять запись по указанному пути, ошибка не выводится; сообщения об ошибках можно получить, используя трассировщик:

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

При выгрузке кэша среда PowerShell ищет модули, которые больше не существуют, чтобы кэш не был излишне большим. Иногда эти проверки нежелательны. В этом случае их можно отключить, задав

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

Новое значение этой переменной среды вступает в силу немедленно в текущем процессе.

### <a name="specifying-module-version"></a>Указание версии модуля

В WMF 5.1 `using module` работает так же, как другие связанные с модулями конструкции в PowerShell. Ранее не было возможности указать определенную версию модуля; при наличии нескольких версий возникала ошибка.

В WMF 5.1:

* Вы можете использовать [конструктор ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).
  Она имеет тот же формат, что и `Get-Module -FullyQualifiedName`.

  **Пример:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* Если имеется несколько версий модуля, в PowerShell используется **та же логика разрешения** , что и в `Import-Module`, и ошибка не выводится. Это поведение аналогично поведению `Import-Module` и `Import-DscResource`.

### <a name="improvements-to-pester"></a>Усовершенствования Pester

В WMF 5,1 версия Pester, входящая в состав PowerShell, была обновлена с 3.3.5 на 3.4.0, с добавлением GitHub [PR # 484](https://github.com/pester/Pester/pull/484), что обеспечивает лучшее поведение для Pester на Nano Server.

Чтобы просмотреть изменения в версиях с 3.3.5 по 3.4.0, откройте файл ChangeLog.md: https://github.com/pester/Pester/blob/master/CHANGELOG.md

## <a name="keywords"></a>СЛОВАМИ

Новые возможности Windows PowerShell 5,1
