---
ms.date: 12/12/2018
keywords: DSC, powershell, ресурсов, в коллекции, программа установки
title: Установка дополнительных ресурсов DSC
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402907"
---
# <a name="install-additional-dsc-resources"></a>Установка дополнительных ресурсов DSC

PowerShell включает несколько ресурсов Out of box для Desired State Configuration (DSC). **PSDesiredStateConfiguration** модуль содержит все ресурсы DSC OOB, доступные в используемой определенной версии PowerShell.

Это список OOB ресурсы, включенные в PowerShell 4.0 и описание возможностей ресурса.

> [!NOTE]
> Это неполный список, поскольку количество ресурсов OOB выросло с каждой версией PowerShell.

|Ресурс  |Описание  |
|---------|---------|
|**File**|Управляет состоянием файлов и каталогов. Копирует файлы из **источника** для **назначения** и обновляет их при **источника** изменения, сравнивая даты, контрольные суммы и хэши.|
|**Archive**|Распаковывает архивы и указанное расположение. Проверяет архивы с заданным **контрольной суммы**.|
|**Environment**|Управляет переменными среды.|
|**Группа**|Управляет локальными группами и контролирует членство в группе.|
|**Log**|Записывает сообщения в `Microsoft-Windows-Desired State Configuration/Analytic` журнала событий.|
|**Пакет**|Устанавливает или удаляет пакеты с помощью **аргументы**, **LogPath**, **ReturnCode**, другие параметры.|
|**Registry**|Управляет разделы реестра и значения.|
|**Script**|Позволяет разрабатывать собственные [get теста set](../resources/get-test-set.md) блоки сценариев.|
|**Служба**|Настраивает службы Windows.|
|**User** |Управляет локальными пользователями и атрибуты.|
|**WindowsFeature**|Управляет ролей и компонентов.|
|**WindowsProcess**|Настраивает процессов Windows.|

Ресурсы OOB разрешить хорошей отправной точкой для выполнения распространенных операций. Если ресурсы OOB не удовлетворяют вашим потребностям, можно написать собственный [настраиваемый ресурс](../resources/authoringResource.md). Прежде чем писать настраиваемый ресурс решить проблему, при просмотре огромное число ресурсов DSC, которые уже были созданы корпорацией Майкрософт и сообществом PowerShell.

Ресурсы DSC, можно найти в обоих [коллекции PowerShell](https://www.powershellgallery.com/) и [GitHub](https://github.com/). Ресурсы DSC также можно установить непосредственно из консоли PowerShell с помощью [PowerShellGet](/powershell/module/powershellget/).

## <a name="installing-powershellget"></a>Установка PowerShellGet

Чтобы определить, есть ли у вас **PowerShell** получения, или Справка по его установке см. в статье в этом руководстве: [Установка PowerShellGet](/powershell/gallery/installing-psget)

## <a name="finding-dsc-resources-using-powershellget"></a>Поиск ресурсов DSC с помощью PowerShellGet

Один раз **PowerShellGet** устанавливается на компьютере, можно найти и установить ресурсы DSC, размещенные в [коллекции PowerShell](https://www.powershellgallery.com/).

Во-первых, используйте [Find-DSCResource](/powershell/module/powershellget/find-dscresource) командлет, чтобы найти ресурсы DSC. При запуске `Find-DSCResource` в первый раз появится приведенный ниже запрос на установку поставщика NuGet «».

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

После нажатия клавиши «y» «NuGet» поставщик установлен, отобразится список ресурсов DSC, которые можно установить из коллекции PowerShell.

> [!NOTE]
> Список не отображается, поскольку очень велик.

Можно также указать `-Name` с использованием подстановочных знаков, параметр или `-Filter` параметр без подстановочных знаков, чтобы сузить круг поиска. В этом примере предпринимается попытка найти ресурс «Часовой пояс» DSC с использованием подстановочных знаков.

> [!IMPORTANT]
> В настоящее время имеется ошибка в `Find-DSCResource` командлет, который предотвращает использование подстановочных знаков в обоих `-Name` и `-Filter` параметров. Во втором примере ниже показано возможное решение с помощью `Where-Object`.

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

Можно также использовать `Where-Object` для поиска ресурсов DSC с более детализированные фильтрации. Этот подход будет медленнее, чем используя встроенные параметры фильтрации.

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

Дополнительные сведения о фильтрации см. в разделе [Where-Object](/powershell/module/microsoft.powershell.core/where-object).

## <a name="installing-dsc-resources-using-powershellget"></a>Установка ресурсов DSC с помощью PowerShellGet

Для установки ресурсов DSC, используйте [Install-Module](/powershell/module/PowershellGet/Install-Module) командлет, указав имя модуля, отображается в поле **модуль** имя в результатах поиска.

Ресурс «Часовой пояс» существует в модуле «ComputerManagementDSC», чтобы он устанавливает модуль в этом примере.

> [!NOTE]
> Если в коллекции PowerShell не является доверенным, вы увидите предупреждение ниже запроса на подтверждение и инструкциями по избежать последующих запросов на устанавливает.

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Нажмите клавишу «y», чтобы продолжить установку модуля. После установки, можно проверить, что установлен с помощью нового ресурса [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

Можно также просмотреть другие ресурсы в только что установленного модуля, указав `-ModuleName` параметра.

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a>См. также:

- [Общие сведения о ресурсах](../resources/resources.md)
