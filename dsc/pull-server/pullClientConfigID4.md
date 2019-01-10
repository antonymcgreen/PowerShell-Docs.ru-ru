---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0
ms.openlocfilehash: 9adc767e91ff19d373c122a0d493e7b8703d5476
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402992"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a>Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0

>Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента, необходимо настроить опрашивающий сервер. На то, что этот порядок не задан, он помогает устранять неполадки и помогает убедиться, что регистрация прошла успешно. Чтобы настроить опрашивающий сервер, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В следующих разделах описана настройка опрашивающего клиента с общий ресурс SMB или опрашивающего сервера DSC HTTP. При обновлении узла LCM, он будет связываться в настроенное расположение для загрузки любого назначенных конфигураций. Если все необходимые ресурсы не существуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настраивается с помощью [сервер отчетов](reportServer.md), затем он сообщит состояние операции.

## <a name="configure-the-pull-client-lcm"></a>Настройка опрашивающего клиента LCM

Выполнение любой из приведенных ниже примерах создается новая выходная папка с именем **PullClientConfigID** и MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>Идентификатор конфигурации

В примерах ниже набор **ConfigurationID** в lcm на **Guid** , было создано для этой цели. Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла. Дополнительные сведения см. в разделе [конфигураций публикации опрашивающий сервер (v4/v5)](publishConfigs.md).

Можно создать случайный **Guid** в примере ниже.

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка клиента на включение внесенных изменений для загрузки конфигураций

Каждый клиент должен быть настроен в **по запросу** режима и URL-адрес сервера по запросу хранения конфигурации. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, с **LocalConfigurationManager** блока. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig4.md).

## <a name="http-dsc-pull-server"></a>DSC опрашивающий HTTP-сервер

Если опрашивающий сервер настроен как веб-службы, задать **DownloadManagerName** для **WebDownloadManager**. **WebDownloadManager** необходимо указать **ServerUrl** для **DownloadManagerCustomData** ключ. Можно также указать значение для **AllowUnsecureConnection**, как показано в приведенном ниже примере. Следующий сценарий настраивает LCM для опроса конфигураций с сервера PullServer.

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
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a>Общий ресурс SMB

Если опрашивающий сервер настроен как файловый ресурс SMB, а не веб-службы, задать **DownloadManagerName** для **DscFileDownloadManager** вместо **WebDownLoadManager**. **DscFileDownloadManager** необходимо указать **SourcePath** свойство в **DownloadManagerCustomData**. Следующий сценарий настраивает LCM для опроса конфигураций из общего ресурса SMB "SmbDscShare" на сервере "CONTOSO-SERVER".

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

После настройки опрашивающий клиент, можно использовать со следующими руководствами для выполните следующие шаги:

- [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)](package-upload-resources.md)

## <a name="see-also"></a>См. также

- [Настройка опрашивающего веб-сервера DSC](pullServer.md)
- [Настройка опрашиваемого SMB-сервера DSC](pullServerSMB.md)
