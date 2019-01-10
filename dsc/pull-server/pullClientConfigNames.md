---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка клиента на включение внесенных изменений с помощью имен конфигурации в PowerShell 5.0 и более поздних версий
ms.openlocfilehash: fd038a105da7a83ecad9b571e611b65c8ec847b3
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403032"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a>Настройка клиента на включение внесенных изменений с помощью имен конфигурации в PowerShell 5.0 и более поздних версий

> Область применения. Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Перед настройкой опрашивающего клиента, необходимо настроить опрашивающий сервер. На то, что этот порядок не задан, он помогает устранять неполадки и помогает убедиться, что регистрация прошла успешно. Чтобы настроить опрашивающий сервер, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В следующих разделах описана настройка опрашивающего клиента с общий ресурс SMB или опрашивающего сервера DSC HTTP. При обновлении узла LCM, он будет связываться в настроенное расположение для загрузки любого назначенных конфигураций. Если все необходимые ресурсы не существуют на узле, он автоматически скачивает их из настроенного расположения. Если на узле настраивается с помощью [сервер отчетов](reportServer.md), затем он сообщит состояние операции.

> **Примечание**. Этот раздел относится к PowerShell 5.0.
Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)

## <a name="configure-the-pull-client-lcm"></a>Настройка опрашивающего клиента LCM

Выполнение любой из приведенных ниже примерах создается новая выходная папка с именем **PullClientConfigName** и MOF-файл метаконфигурации. В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.

Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации. Например:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a>Имя конфигурации

В примерах ниже наборы **ConfigurationName** в lcm на имя ранее скомпилированные конфигурации, созданные для этой цели. **ConfigurationName** является то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере. MOF-файл конфигурации на опрашивающем сервере должен называться `<ConfigurationName>.mof`, в данном случае «ClientConfig.mof». Дополнительные сведения см. в разделе [конфигураций публикации опрашивающий сервер (v4/v5)](publishConfigs.md).

## <a name="set-up-a-pull-client-to-download-configurations"></a>Настройка клиента на включение внесенных изменений для загрузки конфигураций

Каждый клиент должен быть настроен в **по запросу** режима и URL-адрес сервера по запросу хранения конфигурации. Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию. Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**. Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).

Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.

- В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер. Свойство **ServerURL** указывает конечную точку для опрашивающего сервера.

- Свойство **RegistrationKey** является общим ключом между всеми узлами клиента для опрашивающего сервера и их опрашивающего сервера. Те же значения хранятся в файле на опрашивающем сервере.
  > **Примечание**. Ключи регистрации работают только с **web** опрашивающих серверов. Вам по-прежнему следует использовать **ConfigurationID** с опрашиваемым сервером **SMB**.
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

## <a name="set-up-a-pull-client-to-download-resources"></a>Настройка клиента на включение внесенных изменений для загрузки ресурсов

Если указать только **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** блока в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы из одного расположение, где хранятся в MOF-файлы. Можно также указать другое место, где клиенты смогут загружать ресурсы. Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).

В следующем примере показана метаконфигурация, которая настраивает клиент для загрузки конфигураций с опрашивающего сервера и ресурсы из общей папки SMB.

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

## <a name="set-up-a-pull-client-to-report-status"></a>Настройка клиента на включение внесенных изменений для отчета о состоянии

Для конфигураций, ресурсов и отчетов можно использовать на одном опрашивающем сервере. Отчеты, не настраивается для клиентов по умолчанию. Чтобы настроить клиент для отчета о состоянии, то необходимо создать **ReportRepositoryWeb** блока. В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.

> [!NOTE]
> Сервер отчетов не может быть общей папке SMB.

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
