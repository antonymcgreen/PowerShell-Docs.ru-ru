---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0
ms.openlocfilehash: f9bea92f1a2dce94792d72e03bef884d2729f3c0
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34187772"
---
# <a name="setting-up-a-pull-client-using-configuration-id-in-powershell-40"></a>Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0

>Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Для каждого целевого узла нужно задать использование опрашивающего режима и URL-адреса, по которому можно подключиться к опрашивающему серверу для получения конфигураций. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, известный как "метаконфигурация". Дополнительные сведения о настройке LCM см. в разделе [Локальный диспетчер конфигураций для службы настройки требуемого состояния Windows PowerShell 4.0](metaConfig4.md)

Следующий сценарий настраивает LCM для опроса конфигураций с сервера с именем "PullServer".

```powershell
Configuration SimpleMetaConfigurationForPull
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
SimpleMetaConfigurationForPull -Output "."
```

В сценарии **DownloadManagerCustomData** передает URL-адрес опрашивающего сервера и (в этом примере) разрешает небезопасное подключение.

После запуска этого сценария будет создана новая выходная папка **SimpleMetaConfigurationForPull**, в которую будет помещен MOF-файл метаконфигурации.

Для применения конфигурации используйте **Set-DscLocalConfigurationManager** с параметрами **ComputerName** (используйте localhost) и **Path** (путь к расположению файла localhost.meta.mof на целевом узле). Например:
```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path . –Verbose.
```

## <a name="configuration-id"></a>Идентификатор конфигурации
Сценарий заносит в свойство **ConfigurationID** LCM значение GUID, которое было создано специально для этой цели (создать GUID можно, используя командлет **New-Guid**). Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла.

## <a name="pulling-from-an-smb-server"></a>Опрос с SMB-сервера

Если опрашивающий сервер настроен как файловый ресурс SMB, а не веб-служба, укажите **DscFileDownloadManager** вместо **WebDownLoadManager**.
**DscFileDownloadManager** принимает свойство **SourcePath** вместо **ServerUrl**. Следующий сценарий настраивает LCM для опроса конфигураций из общего ресурса SMB "SmbDscShare" на сервере "CONTOSO-SERVER".

```powershell
Configuration SimpleMetaConfigurationForPull
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
SimpleMetaConfigurationForPull -Output "."
```

## <a name="see-also"></a>См. также

- [Настройка опрашивающего веб-сервера DSC](pullServer.md)
- [Настройка опрашивающего SMB-сервера DSC](pullServerSMB.md)