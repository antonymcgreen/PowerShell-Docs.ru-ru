---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше
ms.openlocfilehash: d591e2a757130ccecaf4eaf9f363f607fca82b93
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953631"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a>Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше

> Область применения: Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер. Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно. Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP. При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций. Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.

> [!NOTE]
> Этот раздел относится к PowerShell 5.0.
> Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)

## <a name="configure-the-pull-client-lcm"></a>Настройка LCM опрашивающего клиента

После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigNames**, в которую будет помещен MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a>Имя конфигурации

В примерах ниже в свойстве **ConfigurationName** LCM задается имя ранее скомпилированной конфигурации, созданной для этой цели. Имя **ConfigurationName** — это то, что LCM использует для поиска соответствующей конфигурации на опрашиваемом сервере. MOF-файл конфигурации на опрашиваемом сервере должен называться `<ConfigurationName>.mof`, в данном случае "ClientConfig.mof". Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка опрашивающего клиента для скачивания конфигураций

Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).

Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.

- В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер. Свойство **ServerURL** указывает конечную точку для опрашивающего сервера.

- Свойство **RegistrationKey** является общим ключом между всеми узлами клиента для опрашивающего сервера и их опрашивающего сервера. Те же значения хранятся в файле на опрашивающем сервере.
  > [!NOTE]
  > Ключи регистрации работают только с опрашиваемыми **веб-серверами**. Вам по-прежнему следует использовать **ConfigurationID** с опрашиваемым сервером **SMB**.
  > Сведения о настройке опрашивающего сервера с использованием **ConfigurationID** см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigId.md)

- Свойство **ConfigurationNames** представляет собой массив, указывающий имена конфигураций, предназначенных для узла клиента.
  >**Примечание**. Если для параметра **ConfigurationNames** указано больше одного значения, в конфигурации необходимо также указать блоки **PartialConfiguration**.
  >Сведения о частичных конфигурациях см. в статье [Частичные конфигурации службы настройки требуемого состояния PowerShell](partialConfigs.md).

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-download-resources"></a>Настройка опрашивающего клиента для скачивания ресурсов

Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы оттуда же, где хранятся ваши MOF-файлы. Можно также указать другое место, откуда клиенты смогут скачивать ресурсы. Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).

В следующем примере показана метаконфигурация, которая настраивает клиент для скачивания конфигураций с опрашиваемого сервера, а ресурсов — с общего ресурса SMB.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a>Настройка опрашивающего клиента для отчета о состоянии

Можно использовать один и тот же опрашиваемый сервер для конфигурации, ресурсов и создания отчетов. Отчеты не настраиваются для клиентов по умолчанию. Чтобы настроить клиент для отчета о состоянии, необходимо создать блок **ReportRepositoryWeb**. В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.

> [!NOTE]
> Сервер отчетов не может быть общим ресурсом SMB.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a>См. также

* [Настройка опрашивающего клиента с идентификатором конфигурации](PullClientConfigNames.md)
* [Настройка опрашивающего веб-сервера DSC](pullServer.md)
