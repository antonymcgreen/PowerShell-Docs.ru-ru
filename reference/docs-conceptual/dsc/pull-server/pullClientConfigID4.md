---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 4.0
ms.openlocfilehash: 9259c624c8725f7d76f61e9ad7caa42e1bfa308c
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955151"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a>Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 4.0

>Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер. Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно. Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP. При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций. Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.

## <a name="configure-the-pull-client-lcm"></a>Настройка LCM опрашивающего клиента

После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigID**, в которую будет помещен MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>Идентификатор конфигурации

В следующих примерах свойство **ConfigurationID** LCM заносится в значение **GUID**, которое было создано специально для этой цели. Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла. Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).

Можно создать случайный **GUID**, как показано в следующем примере.

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка опрашивающего клиента для скачивания конфигураций

Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации с помощью блока **LocalConfigurationManager**. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig4.md).

## <a name="http-dsc-pull-server"></a>Опрашиваемый сервер DSC HTTP

Если опрашиваемый сервер настроен как веб-служба, задайте параметру **DownloadManagerName** значение **WebDownloadManager**. Для параметра **WebDownloadManager** необходимо указать значение **ServerUrl** для ключа **DownloadManagerCustomData**. Можно также указать значение для **AllowUnsecureConnection**, как показано в приведенном ниже примере. Следующий сценарий настраивает LCM для опроса конфигураций с сервера PullServer.

```powershell
Configuration PullClientConfigId
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
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = "TRUE"}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a>Общий ресурс SMB

Если опрашиваемый сервер настроен как файловый ресурс SMB, а не веб-служба, укажите **DownloadManagerName** для **DscFileDownloadManager**, а не **WebDownLoadManager**. Для параметра **DscFileDownloadManager** необходимо указать свойство **SourcePath** в разделе **DownloadManagerCustomData**. Следующий сценарий настраивает LCM для опроса конфигураций из общего ресурса SMB "SmbDscShare" на сервере "CONTOSO-SERVER".

```powershell
Configuration PullClientConfigId
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
PullClientConfigId -Output "."
```

## <a name="next-steps"></a>Дальнейшие действия

После настройки опрашивающего клиента можно воспользоваться следующими руководствами для выполнения дальнейших шагов:

- [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)](package-upload-resources.md)

## <a name="see-also"></a>См. также

- [Опрашивающая служба Desired State Configuration](pullServer.md)
- [Настройка опрашиваемого SMB-сервера DSC](pullServerSMB.md)
