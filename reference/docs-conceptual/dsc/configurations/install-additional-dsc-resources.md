---
ms.date: 12/12/2018
keywords: dsc,powershell,resource,gallery,setup
title: Установка дополнительных ресурсов DSC
ms.openlocfilehash: 7a6a935349358e11a77d2f00c0bf88e0ad18c097
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417794"
---
# <a name="install-additional-dsc-resources"></a>Установка дополнительных ресурсов DSC

PowerShell включает в себя несколько установочных ресурсов для Desired State Configuration (DSC). Модуль **PSDesiredStateConfiguration** содержит все OOB ресурсы DSC, доступные в конкретно вашем экземпляре PowerShell.

Это список OOB ресурсов, включенных в PowerShell 4.0, и описание возможностей ресурса.

> [!NOTE]
> Этот список неполный, так как количество OOB ресурсов увеличивалось с каждой версией PowerShell.

|Ресурс  |Описание  |
|---------|---------|
|**File**|Управляет состоянием файлов и каталогов. Копирует файлы из **Источника** в **Место назначения** и обновляет их при изменении **Источника** путем сравнения дат, контрольных сумм и хэшей.|
|**Archive**|Распаковывает архивы и указывает местоположение. Проверяет архивы с указанной **Контрольной суммой**.|
|**Environment**|Управляет переменными среды.|
|**Группа**|Управляет локальными группами и контролирует членство в группах.|
|**Log**|Записывает сообщения в журнал событий `Microsoft-Windows-Desired State Configuration/Analytic`.|
|**Пакет**|Устанавливает или удаляет пакеты, используя **Аргументы**, **LogPath**, **ReturnCode**, другие параметры.|
|**Registry**|Управляет разделами и значениями реестра.|
|**Script**|Позволяет разрабатывать собственные блоки сценариев [get-test-set](../resources/get-test-set.md).|
|**Служба**|Настраивает службы Windows.|
|**User** |Управляет локальными пользователями и атрибутами.|
|**WindowsFeature**|Управляет ролями и функциями.|
|**WindowsProcess**|Настраивает процессы Windows.|

Ресурсы OOB обеспечивают обычным операциям хорошую отправную точку. Если ресурсы OOB не соответствуют вашим потребностям, вы можете написать свой собственный [Пользовательский ресурс](../resources/authoringResource.md). Прежде чем написать собственный ресурс для решения проблемы, вы должны просмотреть огромное количество уже созданных как Microsoft, так и сообществом PowerShell ресурсов DSC.

Ресурсы DSC можно найти как в [коллекции PowerShell](https://www.powershellgallery.com/), так и на [GitHub](https://github.com/). Вы также можете установить ресурсы DSC непосредственно из консоли PowerShell, используя [PowerShellGet](/powershell/module/powershellget/).

## <a name="installing-powershellget"></a>Установка PowerShellGet

Чтобы определить, есть ли у вас **PowerShell**, или получить справку по его установке, см. руководство [Установка PowerShellGet](/powershell/scripting/gallery/installing-psget).

## <a name="finding-dsc-resources-using-powershellget"></a>Поиск ресурсов DSC с помощью PowerShellGet

После установки **PowerShellGet** на компьютер, вы можете найти и установить ресурсы DSC, размещенные в [коллекции PowerShell](https://www.powershellgallery.com/).

Сначала используйте командлет [Find-DSCResource](/powershell/module/powershellget/find-dscresource), чтобы найти ресурсы DSC. При первом запуске `Find-DSCResource` вы увидите следующую подсказку для установки "поставщика NuGet".

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

После нажатия "y" (установки поставщика NuGet) вы увидите список ресурсов DSC, которые вы можете установить из коллекции PowerShell.

> [!NOTE]
> Список не отображается, поскольку очень велик.

Вы также можете указать параметр `-Name`, используя подстановочные знаки, или параметр `-Filter` без подстановочных знаков, чтобы сузить область поиска. В этом примере предпринимается попытка найти ресурс DSC TimeZone с использованием подстановочных знаков.

> [!IMPORTANT]
> В настоящее время в командлете `Find-DSCResource` есть ошибка, которая не позволяет использовать подстановочные знаки в параметрах `-Name` и `-Filter`. Во втором примере, поданном ниже, показано возможное решение с помощью `Where-Object`.

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

Вы также можете использовать `Where-Object` для поиска ресурсов DSC с более детальной фильтрацией. Этот подход будет медленнее, чем использование встроенных параметров фильтрации.

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

Дополнительные сведения о фильтрации см. в разделе [Where-Object](/powershell/module/microsoft.powershell.core/where-object).

## <a name="installing-dsc-resources-using-powershellget"></a>Установка ресурсов DSC с помощью PowerShellGet

Чтобы установить ресурс DSC, используйте командлет [Install-Module](/powershell/module/PowershellGet/Install-Module), указав имя модуля, отображаемого в имени **модуля** в результатах поиска.

Ресурс TimeZone существует в модуле ComputerManagementDSC, поэтому в этом примере устанавливается этот модуль.

> [!NOTE]
> Если коллекция PowerShell не является надежной, вы увидите предупреждение ниже с запросом подтверждения и указанием, как избежать последующих запросов при установке.

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Нажмите "y", чтобы продолжить установку модуля. После установки вы можете проверить, установлен ли ваш новый ресурс, используя [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).

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

Вы также можете просмотреть другие ресурсы в только что установленном модуле, указав параметр `-ModuleName`.

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
