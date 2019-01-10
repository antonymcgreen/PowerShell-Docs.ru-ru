---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройте опрашивающий клиент, используя идентификаторы конфигурации в PowerShell 5.0 и более поздних версий
ms.openlocfilehash: 8d8cf478f9127e1b7005d1b9e832e84b11612c9c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402784"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a>Настройте опрашивающий клиент, используя идентификаторы конфигурации в PowerShell 5.0 и более поздних версий

> Область применения. Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента, необходимо настроить опрашивающий сервер. На то, что этот порядок не задан, он помогает устранять неполадки и помогает убедиться, что регистрация прошла успешно. Чтобы настроить опрашивающий сервер, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В следующих разделах описана настройка опрашивающего клиента с общий ресурс SMB или опрашивающего сервера DSC HTTP. При обновлении узла LCM, он будет связываться в настроенное расположение для загрузки любого назначенных конфигураций. Если все необходимые ресурсы не существуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настраивается с помощью [сервер отчетов](reportServer.md), затем он сообщит состояние операции.

> **Примечание**. Этот раздел относится к PowerShell 5.0. Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)

## <a name="configure-the-pull-client-lcm"></a>Настройка опрашивающего клиента LCM

Выполнение любой из приведенных ниже примерах создается новая выходная папка с именем **PullClientConfigID** и MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>Идентификатор конфигурации

В примерах ниже наборы **ConfigurationID** в lcm на **Guid** , было создано для этой цели. Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла. Дополнительные сведения см. в разделе [конфигураций публикации опрашивающий сервер (v4/v5)](publishConfigs.md).

Можно создать случайный **Guid** в примере ниже, или с помощью [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) командлета.

```powershell
[System.Guid]::NewGuid()
```

Дополнительные сведения об использовании **идентификаторы GUID** в вашей среде, см. в разделе [планирование идентификаторы GUID](/powershell/dsc/secureserver#guids).

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка клиента на включение внесенных изменений для загрузки конфигураций

Каждый клиент должен быть настроен в **по запросу** режима и URL-адрес сервера по запросу хранения конфигурации. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).

### <a name="http-dsc-pull-server"></a>DSC опрашивающий HTTP-сервер

Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер. **ServerUrl** указывает URL-адрес DSC Pull

### <a name="smb-share"></a>Общий ресурс SMB

Следующий сценарий настраивает LCM для опроса конфигураций из общей папки SMB `\\SMBPullServer\Pull`.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

В скрипте **ConfigurationRepositoryShare** блок задает опрашивающий сервер, который в данном случае является ресурс SMB.

## <a name="set-up-a-pull-client-to-download-resources"></a>Настройка клиента на включение внесенных изменений для загрузки ресурсов

Если указать только **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** блока в конфигурации LCM (как в предыдущих примерах), опрашивающий клиент будет получать ресурсы из того же расположение, он извлекает его конфигурации. Можно также указать различные расположения для ресурсов. Чтобы указать расположение ресурсов как отдельный сервер, используйте **ResourceRepositoryWeb** блока. Чтобы указать расположение ресурсов как ресурс SMB, используйте **ResourceRepositoryShare** блока.

> [!NOTE]
> Вы можете объединить **ConfigurationRepositoryWeb** с **ResourceRepositoryShare** или **ConfigurationRepositoryShare** с **ResourceRepositoryWeb** . Не в качестве примера приведены ниже.

### <a name="http-dsc-pull-server"></a>DSC опрашивающий HTTP-сервер

Следующая метаконфигурация настраивает на опрашивающем клиенте получение конфигураций из **CONTOSO-PullSrv** и его ресурсы из **CONTOSO-ResourceSrv**.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a>Общий ресурс SMB

В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций из общей папки SMB `\\SMBPullServer\Configurations`и ресурсы из общей папки SMB `\\SMBPullServer\Resources`.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a>Автоматически загружать ресурсы в режиме Push

Начиная с PowerShell 5.0, клиенты по запросу можно скачать модули из общей папки SMB, даже в том случае, если они настроены для **Push** режим. Это особенно полезно в сценариях, где вы хотите настроить сервер на включение внесенных изменений. **ResourceRepositoryShare** блок может использоваться без указания **ConfigurationRepositoryShare**. В следующем примере показана метаконфигурация, которая настраивает клиент для извлечения ресурсов из общей папки SMB `\\SMBPullServer\Resources`. Когда этот узел находится **PUSHED** конфигурации, он автоматически скачивает все необходимые ресурсы, указанный общий ресурс.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a>Настройка клиента на включение внесенных изменений для отчета о состоянии

По умолчанию узлы не отправляют отчеты к настроенному серверу на включение внесенных изменений. Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.

### <a name="http-dsc-pull-server"></a>DSC опрашивающий HTTP-сервер

В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

Чтобы указать сервер отчетов, используйте блок **ReportRepositoryWeb**. Сервер отчетов не может быть SMB-сервером.
Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**, а также для отправки отчетов о состоянии на **CONTOSO-ReportSrv**:

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a>Общий ресурс SMB

Сервер отчетов не может быть общей папке SMB.

## <a name="next-steps"></a>Дальнейшие действия

После настройки опрашивающий клиент, можно использовать со следующими руководствами для выполните следующие шаги:

- [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)](package-upload-resources.md)

## <a name="see-also"></a>См. также

* [Настройка опрашивающего клиента с именами конфигураций](pullClientConfigNames.md)
