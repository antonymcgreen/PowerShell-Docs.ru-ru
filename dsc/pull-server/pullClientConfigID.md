---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше
ms.openlocfilehash: 14db98d240bc87aca3ee985db08c14b7c65d8bb8
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "58055722"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a>Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше

> Область применения. Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер. Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно. Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP. При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций. Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.

> [!NOTE]
> Этот раздел относится к PowerShell 5.0. Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)

## <a name="configure-the-pull-client-lcm"></a>Настройка LCM опрашивающего клиента

После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigID**, в которую будет помещен MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>Идентификатор конфигурации

Примеры ниже заносят в свойство **ConfigurationID** LCM значение **GUID**, которое было создано специально для этой цели. Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла. Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).

Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).

```powershell
[System.Guid]::NewGuid()
```

Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](/powershell/dsc/secureserver#guids).

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка опрашивающего клиента для скачивания конфигураций

Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).

### <a name="http-dsc-pull-server"></a>Опрашиваемый сервер DSC HTTP

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

В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер. **ServerUrl** указывает URL-адрес опрашиваемого сервера DSC.

### <a name="smb-share"></a>Общий ресурс SMB

Следующий сценарий настраивает LCM для опроса конфигураций с общего ресурса SMB с именем `\\SMBPullServer\Pull`.

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

В скрипте блок **ConfigurationRepositoryShare** задает опрашиваемый сервер, которым в этом случае является общий ресурс SMB.

## <a name="set-up-a-pull-client-to-download-resources"></a>Настройка опрашивающего клиента для скачивания ресурсов

Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы оттуда же, откуда и конфигурации. Можно также указать различные расположения для ресурсов. Чтобы указать расположение ресурсов как отдельный сервер, используйте блок **ResourceRepositoryWeb**. Чтобы указать расположение ресурсов как общий ресурс SMB, используйте блок **ResourceRepositoryShare**.

> [!NOTE]
> Вы можете объединить **ConfigurationRepositoryWeb** с **ResourceRepositoryShare** или **ConfigurationRepositoryShare** с **ResourceRepositoryWeb** . Примеров этого ниже нет.

### <a name="http-dsc-pull-server"></a>Опрашиваемый сервер DSC HTTP

Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**.

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

В следующем примере показана метаконфигурация, которая настраивает клиент для получения конфигураций с общего ресурса SMB `\\SMBPullServer\Configurations`, а ресурсов — с общего ресурса SMB `\\SMBPullServer\Resources`.

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

#### <a name="automatically-download-resources-in-push-mode"></a>Автоматическое скачивание ресурсов в режиме Push

Начиная с PowerShell 5.0 опрашивающие клиенты могут скачивать модули из общего ресурса SMB даже в том случае, если они настроены в режиме **Push**. Это особенно полезно в сценариях, когда вы не хотите настраивать опрашиваемый сервер. Блок **ResourceRepositoryShare** может использоваться без указания **ConfigurationRepositoryShare**. В следующем примере показана метаконфигурация, которая настраивает клиент для получения ресурсов с общего ресурса SMB `\\SMBPullServer\Resources`. Когда на узел принудительно **отправляется** конфигурация, он автоматически скачивает все необходимые ресурсы с указанного общего ресурса.

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

## <a name="set-up-a-pull-client-to-report-status"></a>Настройка опрашивающего клиента для отчета о состоянии

По умолчанию узлы не отправляют отчеты на настроенный опрашиваемый сервер. Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.

### <a name="http-dsc-pull-server"></a>Опрашиваемый сервер DSC HTTP

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

Сервер отчетов не может быть общим ресурсом SMB.

## <a name="next-steps"></a>Дальнейшие действия

После настройки опрашивающего клиента можно воспользоваться следующими руководствами для выполнения дальнейших шагов:

- [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)](package-upload-resources.md)

## <a name="see-also"></a>См. также

* [Настройка опрашивающего клиента с именами конфигураций](pullClientConfigNames.md)
