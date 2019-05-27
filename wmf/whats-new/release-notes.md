---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,установка
title: Заметки о выпуске WMF 5.x
ms.openlocfilehash: 8bdc423234cf0b104b72b1bee1de35e50783d8a4
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855769"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a>Заметки о выпуске Windows Management Framework (WMF) 5.x

## <a name="wmf-50-changes"></a>Изменения WMF 5.0

- В PowerShell 5.0 добавлен новый структурированный поток **сведений**
- Усовершенствования DSC, включая четыре новых ресурса DSC:
  - WindowsFeatureSet
  - WindowsOptionalFeatureSet
  - ServiceSet
  - ProcessSet
- Добавлена Just Enough Administration для обеспечения ролевого администрирования через удаленное взаимодействие PowerShell
- PowerShell 5.0 расширяет язык, включив пользовательские классы и перечисления
- Усовершенствованы функции отладки в интегрированной среде сценариев PowerShell и добавлена удаленная отладка
- Добавлены модули PowerShellGet и PackageManagement
- Расширено ведение журнала сценариев и записи PowerShell
- Добавлены командлеты Cryptographic Message Syntax
- WMF 5.0 включает в себя модуль NetworkSwitchManager для Windows
- Добавлен модуль Microsoft.PowerShell.ODataUtils
- Добавлена поддержка инвентаризации программного обеспечения (SIL)
- Представлены новые или обновленные командлеты сервера по запросам пользователей и для решения проблем

## <a name="wmf-51-changes"></a>Изменения WMF 5.1

WMF 5.1 включает компоненты PowerShell, WMI, WinRM и Software Inventory Logging (SIL), которые были выпущены с Windows Server 2016. Службу WMF 5.1 можно установить на Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 и 2012 R2; она предоставляет ряд улучшений в WMF 5.0, включая следующие:

- Новые командлеты
- Улучшения PowerShellGet включают принудительное подписание модулей и установку модулей JEA.
- Дополнительная поддержка PackageManagement для контейнеров, установка CBS, установка на основе EXE, пакеты CAB.
- Улучшения отладки для классов DSC и PowerShell.
- Улучшения для системы безопасности, включая принудительное использование модулей, подписанных каталогом и полученных от опрашивающего сервера, а также при использовании командлетов PowerShellGet.
- Ответы на разные запросы пользователей и решение проблем.

## <a name="powershell-editions"></a>Выпуски PowerShell

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

- **Desktop Edition:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.
- **Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

### <a name="learn-more-about-using-powershell-editions"></a>Дополнительные сведения об использовании выпусков PowerShell

- [Определение запущенного выпуска PowerShell с использованием $PSVersionTable](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [Фильтрация результатов командлета Get-Module по CompatiblePSEditions с помощью параметра PSEdition](/powershell/module/microsoft.powershell.core/get-module)
- [Запрет на выполнение сценариев в несовместимых выпусках PowerShell](/powershell/gallery/concepts/script-psedition-support)
- [Объявление совместимости модуля с определенными версиями PowerShell](/powershell/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a>Кэш анализа модуля

Начиная с версии WMF 5.1 среда PowerShell предоставляет средства управления файлом, в котором кэшируются сведения о модуле, например экспортируемые им команды.

По умолчанию этот кэш хранится в файле `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`. Кэш обычно считывается при запуске в процессе поиска команды и записывается в фоновом потоке через некоторое время после импорта модуля.

Чтобы изменить расположение кэша по умолчанию, присвойте значение переменной среды `$env:PSModuleAnalysisCachePath` перед запуском PowerShell. Изменения, вносимые в эту переменную среды, влияют только на дочерние процессы. Значение должно быть полным путем (включая имя файла), на создание и запись файлов по которому у среды PowerShell есть разрешение. Чтобы отключить файловый кэш, укажите в качестве этого значения недопустимое расположение, например:

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

Таким образом задается путь к недопустимому устройству. Если среда PowerShell не может осуществлять запись по указанному пути, ошибка не выводится; сообщения об ошибках можно получить, используя трассировщик:

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

При выгрузке кэша среда PowerShell ищет модули, которые больше не существуют, чтобы кэш не был излишне большим. Иногда эти проверки нежелательны. В этом случае их можно отключить, задав

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

Новое значение этой переменной среды вступает в силу немедленно в текущем процессе.

## <a name="specifying-module-version"></a>Указание версии модуля

В WMF 5.1 `using module` работает так же, как другие связанные с модулями конструкции в PowerShell.
Ранее не было возможности указать определенную версию модуля; при наличии нескольких версий возникала ошибка.

В WMF 5.1:

- Вы можете использовать [конструктор ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).
  Она имеет тот же формат, что и `Get-Module -FullyQualifiedName`.

  **Пример:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

- Если имеется несколько версий модуля, в PowerShell используется **та же логика разрешения**, что и в `Import-Module`, и ошибка не выводится. Это поведение аналогично поведению `Import-Module` и `Import-DscResource`.

## <a name="improvements-to-pester"></a>Усовершенствования Pester

В WMF 5.1 обновлена версия Pester, распространяемая с PowerShell, с 3.3.5 до 3.4.0.
Это обновление улучшает работу Pester на сервере Nano Server.

Изменения в Pest можно просмотреть в [журнале изменений](https://github.com/pester/Pester/blob/master/CHANGELOG.md) в репозитории GitHub.
