---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,установка
title: Усовершенствования DSC в WMF 5.1
ms.openlocfilehash: 4de295db539b95d0f4ddef297df5e9523892bffc
ms.sourcegitcommit: a35450f420dc10a02379f6e6f08a28ad11fe5a6d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71692422"
---
# <a name="improvements-in-desired-state-configuration-dsc-in-wmf-51"></a><span data-ttu-id="069d6-103">Усовершенствования в настройке требуемого состояния (DSC) в WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="069d6-103">Improvements in Desired State Configuration (DSC) in WMF 5.1</span></span>

## <a name="dsc-class-resource-improvements"></a><span data-ttu-id="069d6-104">Усовершенствования в ресурсах классов DSC</span><span class="sxs-lookup"><span data-stu-id="069d6-104">DSC class resource improvements</span></span>

<span data-ttu-id="069d6-105">В WMF 5.1 были устранены следующие известные проблемы.</span><span class="sxs-lookup"><span data-stu-id="069d6-105">In WMF 5.1, we have fixed the following known issues:</span></span>

- <span data-ttu-id="069d6-106">Командлет Get-DscConfiguration может возвращать пустые значения (NULL) или ошибки, если функция Get() ресурса DSC на основе классов возвращает сложный тип или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="069d6-106">Get-DscConfiguration may return empty values (null) or errors if a complex/hash table type is returned by Get() function of a class-based DSC resource.</span></span>
- <span data-ttu-id="069d6-107">Командлет Get-DscConfiguration возвращает ошибку, если в конфигурации DSC используются учетные данные запуска от имени.</span><span class="sxs-lookup"><span data-stu-id="069d6-107">Get-DscConfiguration returns error if RunAs credential is used in DSC configuration.</span></span>
- <span data-ttu-id="069d6-108">Ресурсы на основе классов не могут использоваться в составной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="069d6-108">Class-based resource cannot be used in a composite configuration.</span></span>
- <span data-ttu-id="069d6-109">Командлет Start-DscConfiguration зависает, если ресурс на основе классов имеет свойство со своим собственным типом.</span><span class="sxs-lookup"><span data-stu-id="069d6-109">Start-DscConfiguration hangs if class-based resource has a property of its own type.</span></span>
- <span data-ttu-id="069d6-110">Ресурсы на основе класса не могут использоваться в качестве монопольных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="069d6-110">Class-based resource cannot be used as an exclusive resource.</span></span>

## <a name="dsc-resource-debugging-improvements"></a><span data-ttu-id="069d6-111">Усовершенствования в отладке ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="069d6-111">DSC resource debugging improvements</span></span>

<span data-ttu-id="069d6-112">В WMF 5.0 отладчик PowerShell не останавливался непосредственно в методах для работы с ресурсами, основанными на классах (Get, Set, Test).</span><span class="sxs-lookup"><span data-stu-id="069d6-112">In WMF 5.0, the PowerShell debugger did not stop at the class-based resource method (Get/Set/Test) directly.</span></span> <span data-ttu-id="069d6-113">В WMF 5.1 отладчик останавливается в методах для работы с ресурсами, основанными на классах, точно так же, как в методах для работы с ресурсами на основе MOF.</span><span class="sxs-lookup"><span data-stu-id="069d6-113">In WMF 5.1, the debugger stops at the class-based resource method in the same way as for MOF-based resources methods.</span></span>

## <a name="dsc-pull-client-supports-tls-11-and-tls-12"></a><span data-ttu-id="069d6-114">Опрашивающий клиент DSC поддерживает TLS 1.1 и TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="069d6-114">DSC pull client supports TLS 1.1 and TLS 1.2</span></span>

<span data-ttu-id="069d6-115">Ранее опрашивающий клиент DSC поддерживал только SSL3.0 и TLS1.0 через подключения по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="069d6-115">Previously, the DSC pull client only supported SSL3.0 and TLS1.0 over HTTPS connections.</span></span> <span data-ttu-id="069d6-116">При принудительном использовании более безопасных протоколов опрашивающий клиент прекращал работу.</span><span class="sxs-lookup"><span data-stu-id="069d6-116">When forced to use more secure protocols, the pull client would stop functioning.</span></span> <span data-ttu-id="069d6-117">В WMF 5.1 опрашивающий клиент DSC больше не поддерживает SSL 3.0, но поддерживает более безопасные протоколы TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="069d6-117">In WMF 5.1, the DSC pull client no longer supports SSL 3.0 and adds support for the more secure TLS 1.1 and TLS 1.2 protocols.</span></span>

## <a name="improved-pull-server-registration"></a><span data-ttu-id="069d6-118">Улучшенная регистрация опрашивающего сервера</span><span class="sxs-lookup"><span data-stu-id="069d6-118">Improved pull server registration</span></span>

<span data-ttu-id="069d6-119">В более ранних версиях WMF одновременные запросы регистрации или отчетов к опрашивающему серверу DSC при использовании базы данных ESENT привели бы к ошибке в LCM при регистрации или получении отчета.</span><span class="sxs-lookup"><span data-stu-id="069d6-119">In the earlier versions of WMF, simultaneous registrations/reporting requests to a DSC pull server while using the ESENT database would lead to LCM failing to register and/or report.</span></span> <span data-ttu-id="069d6-120">В журналах событий на опрашивающем сервере в таких случаях появляется ошибка "Имя экземпляра уже используется".</span><span class="sxs-lookup"><span data-stu-id="069d6-120">In such cases, the event logs on the pull server has the error "Instance Name already in use."</span></span> <span data-ttu-id="069d6-121">Эта ошибка вызывалась тем, что для доступа к базе данных ESENT в сценарии с несколькими потоками использовался неправильный шаблон.</span><span class="sxs-lookup"><span data-stu-id="069d6-121">This was caused by an incorrect pattern being used to access the ESENT database in a multi-threaded scenario.</span></span> <span data-ttu-id="069d6-122">В WMF 5.1 эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="069d6-122">In WMF 5.1, this issue has been fixed.</span></span> <span data-ttu-id="069d6-123">Одновременные запросы регистрации или отчетов (с использованием базы данных ESENT) выполняются корректно в WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="069d6-123">Concurrent registrations or reporting (involving ESENT database) works fine in WMF 5.1.</span></span> <span data-ttu-id="069d6-124">Эта проблема относится только к базе данных ESENT и не касается базы данных OLEDB.</span><span class="sxs-lookup"><span data-stu-id="069d6-124">This issue is applicable only to the ESENT database and does not apply to the OLEDB database.</span></span>

## <a name="enable-circular-log-on-esent-database-instance"></a><span data-ttu-id="069d6-125">Включить циклический журнал в экземпляре базы данных ESENT</span><span class="sxs-lookup"><span data-stu-id="069d6-125">Enable Circular log on ESENT database instance</span></span>

<span data-ttu-id="069d6-126">В более ранней версии DSC-PullServer файлы журнала базы данных ESENT заполняли дисковое пространство опрашивающего сервера, так как экземпляр базы данных был создан без циклического ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="069d6-126">In eariler version of DSC-PullServer, the ESENT database log files were filling up the disk space of the pullserver becouse the database instance was being created without circular logging.</span></span> <span data-ttu-id="069d6-127">В этом выпуске можно управлять поведением циклического ведения журнала экземпляра с помощью web.config опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="069d6-127">In this release, you have the option to control the circular logging behavior of the instance using the web.config of the pullserver.</span></span> <span data-ttu-id="069d6-128">По умолчанию значение CircularLogging равно TRUE.</span><span class="sxs-lookup"><span data-stu-id="069d6-128">By default CircularLogging is set to TRUE.</span></span>

```xml
<appSettings>
    <add key="dbprovider" value="ESENT" />
    <add key="dbconnectionstr" value="C:\Program Files\WindowsPowerShell\DscService\Devices.edb" />
    <add key="CheckpointDepthMaxKB" value="512" />
    <add key="UseCircularESENTLogs" value="TRUE" />
  </appSettings>
```

## <a name="wow64-support-for-configuration-keyword"></a><span data-ttu-id="069d6-129">Поддержка ключевого слова Configuration в WOW64</span><span class="sxs-lookup"><span data-stu-id="069d6-129">WOW64 support for Configuration Keyword</span></span>

<span data-ttu-id="069d6-130">Ключевое слово `Configuration` теперь поддерживается в WOW64 на 64-разрядном компьютере.</span><span class="sxs-lookup"><span data-stu-id="069d6-130">The `Configuration` keyword is now supported in WOW64 on a 64-bit computer.</span></span> <span data-ttu-id="069d6-131">Это означает, что конфигурации DSC можно определить и скомпилировать в 32-разрядном процессе, таком как интегрированная среда сценариев Windows PowerShell (x86), выполняемом на 64-разрядном компьютере.</span><span class="sxs-lookup"><span data-stu-id="069d6-131">This means that a DSC configuration can be defined and compiled within a 32-bit process such as Windows PowerShell ISE (x86) running on a 64-bit computer.</span></span>

## <a name="pull-partial-configuration-naming-convention"></a><span data-ttu-id="069d6-132">Соглашение об именовании для частичной опрашивающей конфигурации</span><span class="sxs-lookup"><span data-stu-id="069d6-132">Pull partial configuration naming convention</span></span>

<span data-ttu-id="069d6-133">В предыдущем выпуске соглашение об именовании для частичной конфигурации было таким, что имя MOF-файла в опрашивающем сервере или службе должно было соответствовать имени частичной конфигурации, указанному в параметрах локального диспетчера конфигурации, которое, в свою очередь, должно соответствовать имени конфигурации, включенному в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="069d6-133">In the previous release, the naming convention for a partial configuration was that the MOF file name in the pull server/service should match the partial configuration name specified in the local configuration manager settings that in turn must match the configuration name embedded in the MOF file.</span></span>

<span data-ttu-id="069d6-134">См. моментальные снимки ниже.</span><span class="sxs-lookup"><span data-stu-id="069d6-134">See the snapshots below:</span></span>

- <span data-ttu-id="069d6-135">Параметры локальной конфигурации, определяющие частичную конфигурацию, которую разрешено получать узлу.</span><span class="sxs-lookup"><span data-stu-id="069d6-135">Local configuration settings which defines a partial configuration that a node is allowed to receive.</span></span>

  ![Пример метаконфигурации](../images/DSC-improvements/MetaConfigPartialOne.png)

- <span data-ttu-id="069d6-137">Пример определения частичной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="069d6-137">Sample partial configuration definition</span></span>

  ```powershell
  Configuration PartialOne
  {
      Node('localhost')
      {
          File test
          {
              DestinationPath = "$env:TEMP\partialconfigexample.txt"
              Contents = 'Partial Config Example'
          }
      }
  }
  PartialOne
  ```

- <span data-ttu-id="069d6-138">Имя конфигурации (ConfigurationName), включенное в созданный MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="069d6-138">'ConfigurationName' embedded in the generated MOF file.</span></span>

  ![Пример созданного MOF-файла](../images/DSC-improvements/PartialGeneratedMof.png)

- <span data-ttu-id="069d6-140">Имя файла в репозитории конфигураций извлечения.</span><span class="sxs-lookup"><span data-stu-id="069d6-140">FileName in the pull configuration repository</span></span>

  ![Имя файла в репозитории конфигураций](../images/DSC-improvements/PartialInConfigRepository.png)

  <span data-ttu-id="069d6-142">Служба автоматизации Azure создавала MOF-файлы с именами `<ConfigurationName>.<NodeName>.mof`.</span><span class="sxs-lookup"><span data-stu-id="069d6-142">Azure Automation service name generated MOF files as `<ConfigurationName>.<NodeName>.mof`.</span></span> <span data-ttu-id="069d6-143">Поэтому следующая конфигурация компилируется в файл PartialOne.Localhost.mof.</span><span class="sxs-lookup"><span data-stu-id="069d6-143">So the configuration below compiles to PartialOne.localhost.mof.</span></span>

  <span data-ttu-id="069d6-144">Это делало невозможным запрос к одной из частичных конфигураций из службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="069d6-144">This made it impossible to pull one of your partial configuration from Azure Automation service.</span></span>

  ```powershell
  Configuration PartialOne
  {
      Node('localhost')
      {
          File test
          {
              DestinationPath = "$env:TEMP\partialconfigexample.txt"
              Contents = 'Partial Config Example'
          }
      }
  }
  PartialOne
  ```

  <span data-ttu-id="069d6-145">В WMF 5.1 частичная конфигурация на опрашивающем сервере или в службе может иметь имя `<ConfigurationName>.<NodeName>.mof`.</span><span class="sxs-lookup"><span data-stu-id="069d6-145">In WMF 5.1, a partial configuration in the pull server/service can be named as `<ConfigurationName>.<NodeName>.mof`.</span></span> <span data-ttu-id="069d6-146">Кроме того, если компьютер запрашивает одну конфигурацию с опрашивающего сервера или службы, то файл конфигурации в репозитории конфигураций опрашивающего сервера может иметь любое имя.</span><span class="sxs-lookup"><span data-stu-id="069d6-146">Moreover, if a machine is pulling a single configuration from a pull server/service then the configuration file on the pull server configuration repository can have any file name.</span></span> <span data-ttu-id="069d6-147">Эта гибкость в именовании позволяет управлять узлами, которые находятся под частичным управлением службы автоматизации Azure. В этом случае часть конфигурации узла поступает из DSC службы автоматизации Azure, а другой частью конфигурации вы управляете локально.</span><span class="sxs-lookup"><span data-stu-id="069d6-147">This naming flexibility allows you to manage your nodes partially by Azure Automation service, where some configuration for your node is coming from Azure Automation DSC and with a partial configuration that you manage locally.</span></span>

  <span data-ttu-id="069d6-148">В следующей метаконфигурации узел находится как под локальным управлением, так и под управлением службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="069d6-148">The metaconfiguration below sets up a node to be managed both locally as well as by Azure Automation service.</span></span>

  ```powershell
  [DscLocalConfigurationManager()]
  Configuration RegistrationMetaConfig
  {
      Settings
      {
          RefreshFrequencyMins = 30
          RefreshMode = "PULL"
      }

      ConfigurationRepositoryWeb web
      {
          ServerURL =  $endPoint
          RegistrationKey = $registrationKey
          ConfigurationNames = $configurationName
      }

      # Partial configuration managed by Azure Automation service.
      PartialConfiguration PartialConfigurationManagedByAzureAutomation
      {
          ConfigurationSource = "[ConfigurationRepositoryWeb]Web"
      }

      # This partial configuration is managed locally.
      PartialConfiguration OnPremisesConfig
      {
          RefreshMode = "PUSH"
          ExclusiveResources = @("Script")
      }

  }

  RegistrationMetaConfig
  Set-DscLocalConfigurationManager -Path .\RegistrationMetaConfig -Verbose
  ```

## <a name="using-psdscrunascredential-with-dsc-composite-resources"></a><span data-ttu-id="069d6-149">Использование параметра PsDscRunAsCredential с составными ресурсами DSC</span><span class="sxs-lookup"><span data-stu-id="069d6-149">Using PsDscRunAsCredential with DSC composite resources</span></span>

<span data-ttu-id="069d6-150">Добавлена поддержка использования параметра [PsDscRunAsCredential](/powershell/dsc/configurations/runAsUser) с [составными](https://msdn.microsoft.com/powershell/dsc/authoringresourcecomposite) ресурсами DSC.</span><span class="sxs-lookup"><span data-stu-id="069d6-150">We have added support for using [PsDscRunAsCredential](/powershell/dsc/configurations/runAsUser) with DSC [Composite](https://msdn.microsoft.com/powershell/dsc/authoringresourcecomposite) resources.</span></span>

<span data-ttu-id="069d6-151">Теперь можно указать значение параметра **PsDscRunAsCredential** при использовании составных ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="069d6-151">You can now specify a value for **PsDscRunAsCredential** when using composite resources inside configurations.</span></span> <span data-ttu-id="069d6-152">Если значение задано, все ресурсы, включенные в составной ресурс, будут запущены от имени этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="069d6-152">When specified, all resources run inside a composite resource as a RunAs user.</span></span> <span data-ttu-id="069d6-153">Если составной ресурс вызывает другой составной ресурс, то все такие ресурсы также будут запущены от имени этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="069d6-153">If a composite resource calls another composite resource, all those resources are also executed as RunAs user.</span></span> <span data-ttu-id="069d6-154">Учетные данные запуска от имени распространяются на любой уровень иерархии составных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="069d6-154">RunAs credentials are propagated to any level of the composite resource hierarchy.</span></span> <span data-ttu-id="069d6-155">Если для одного из ресурсов, входящих в составной ресурс, указано собственное значение параметра **PsDscRunAsCredential**, при компиляции конфигурации возникает ошибка слияния.</span><span class="sxs-lookup"><span data-stu-id="069d6-155">If any resource inside a composite resource specifies its own value for **PsDscRunAsCredential**, a merge error results during configuration compilation.</span></span>

<span data-ttu-id="069d6-156">В этом примере показано, как использовать этот параметр с составным ресурсом [WindowsFeatureSet](/powershell/dsc/reference/resources/windows/windowsfeaturesetresource), включенным в модуль PSDesiredStateConfiguration.</span><span class="sxs-lookup"><span data-stu-id="069d6-156">This example shows usage with the [WindowsFeatureSet](/powershell/dsc/reference/resources/windows/windowsfeaturesetresource) composite resource included in PSDesiredStateConfiguration module.</span></span>

```powershell
Configuration InstallWindowsFeature
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        WindowsFeatureSet features
        {
            Name = @("Telnet-Client","SNMP-Service")
            Ensure = "Present"
            IncludeAllSubFeature = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost'
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

InstallWindowsFeature -ConfigurationData $configData
```

## <a name="allowing-for-identical-duplicate-resources-in-a-configuration"></a><span data-ttu-id="069d6-157">Поддержка идентичных повторяющихся ресурсов в конфигурации</span><span class="sxs-lookup"><span data-stu-id="069d6-157">Allowing for Identical Duplicate Resources in a Configuration</span></span>

<span data-ttu-id="069d6-158">DSC не допускает и не обрабатывает конфликтующие определения ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="069d6-158">DSC does not allow or handle conflicting resource definitions within a configuration.</span></span> <span data-ttu-id="069d6-159">Вместо того чтобы попытаться разрешить конфликт, он просто завершается со сбоем.</span><span class="sxs-lookup"><span data-stu-id="069d6-159">Instead of trying to resolve the conflict, it simply fails.</span></span> <span data-ttu-id="069d6-160">По мере того, как конфигурации все больше используются повторно с помощью составных ресурсов и т. п., конфликты будут возникать все чаще.</span><span class="sxs-lookup"><span data-stu-id="069d6-160">As configuration reuse becomes more utilized through composite resources, etc. conflicts will occur more often.</span></span> <span data-ttu-id="069d6-161">Если конфликтующие определения ресурсов идентичны, DSC необходимо разрешить такую работу.</span><span class="sxs-lookup"><span data-stu-id="069d6-161">When conflicting resource definitions are identical, DSC should be smart and allow this.</span></span> <span data-ttu-id="069d6-162">В этом выпуске мы включаем поддержку нескольких экземпляров ресурсов с одинаковыми определениями:</span><span class="sxs-lookup"><span data-stu-id="069d6-162">With this release, we support having multiple resource instances that have identical definitions:</span></span>

```powershell
Configuration IIS_FrontEnd
{
    WindowsFeature FE_IIS         #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature FTP
    {
        Ensure = 'Present'
        Name = 'Web-FTP-Server'
    }
}

Configuration IIS_Worker
{
    WindowsFeature Worker_IIS      #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature ASP
    {
        Ensure = 'Present'
        Name = 'Web-ASP-Net45'
    }
}

Configuration WebApplication
{
    IIS_Frontend Web {}

    IIS_Worker ASP {}
}
```

<span data-ttu-id="069d6-163">Если бы в предыдущих выпусках имелся конфликт между экземплярами WindowsFeature FE_IIS и WindowsFeature Worker_IIS, пытающимися проверить установку роли "Веб-сервер", компиляция завершилась бы сбоем.</span><span class="sxs-lookup"><span data-stu-id="069d6-163">In previous releases, the result would be a failed compilation due to a conflict between the WindowsFeature FE_IIS and WindowsFeature Worker_IIS instances trying to ensure the 'Web-Server' role is installed.</span></span> <span data-ttu-id="069d6-164">Обратите внимание, что в этих двух конфигурациях *все* настраиваемые свойства идентичны.</span><span class="sxs-lookup"><span data-stu-id="069d6-164">Notice that *all* of the properties that are being configured are identical in these two configurations.</span></span> <span data-ttu-id="069d6-165">И именно благодаря идентичности *всех* свойств в этих двух ресурсах компиляция теперь выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="069d6-165">Since *all* of the properties in these two resources are identical, this will result in a successful compilation now.</span></span>

<span data-ttu-id="069d6-166">Если же какие-либо свойства между двумя ресурсами не совпадают, они не считаются идентичными, и компиляция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="069d6-166">If any of the properties are different between the two resources, they will not be considered identical and compilation will fail.</span></span>

## <a name="dsc-module-and-configuration-signing-validations"></a><span data-ttu-id="069d6-167">Модуль DSC и проверка подписи конфигурации</span><span class="sxs-lookup"><span data-stu-id="069d6-167">DSC module and configuration signing validations</span></span>

<span data-ttu-id="069d6-168">В DSC конфигурации и модули распространяются на управляемые компьютеры с опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="069d6-168">In DSC, configurations and modules are distributed to managed computers from the pull server.</span></span> <span data-ttu-id="069d6-169">При компрометации опрашиваемого сервера злоумышленник может изменить на нем конфигурации и модули и распространить их на все управляемые узлы.</span><span class="sxs-lookup"><span data-stu-id="069d6-169">If the pull server is compromised, an attacker can potentially modify the configurations and modules on the pull server and have it distributed to all managed nodes.</span></span>

<span data-ttu-id="069d6-170">В WMF 5.1 DSC поддерживает проверку цифровых подписей файлов каталогов и конфигурации (MOF-файлов).</span><span class="sxs-lookup"><span data-stu-id="069d6-170">In WMF 5.1, DSC supports validating the digital signatures on catalog and configuration (.MOF) files.</span></span> <span data-ttu-id="069d6-171">Эта функция предотвращает выполнение на узлах конфигураций или файлов модулей, которые не подписаны доверенным лицом или изменены после подписания доверенным лицом.</span><span class="sxs-lookup"><span data-stu-id="069d6-171">This feature prevents nodes from executing configurations or module files which are not signed by a trusted signer or which have been tampered with after they have been signed by trusted signer.</span></span>

### <a name="how-to-sign-configuration-and-module"></a><span data-ttu-id="069d6-172">Подписывание конфигурации и модулей</span><span class="sxs-lookup"><span data-stu-id="069d6-172">How to sign configuration and module</span></span>

- <span data-ttu-id="069d6-173">Файлы конфигурации (MOF-файлы): поддержка подписывания MOF-файлов была добавлена к функциям существующего командлета PowerShell, [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature).</span><span class="sxs-lookup"><span data-stu-id="069d6-173">Configuration Files (.MOFs): The existing PowerShell cmdlet [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) is extended to support signing of MOF files.</span></span>
- <span data-ttu-id="069d6-174">Модули: для подписывания модулей необходимо подписать каталог соответствующего модуля, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="069d6-174">Modules: Signing of modules is done by signing the corresponding module catalog using the following steps:</span></span>
  1. <span data-ttu-id="069d6-175">Создайте файл каталога: файл каталога содержит коллекцию криптографических хэшей или отпечатков.</span><span class="sxs-lookup"><span data-stu-id="069d6-175">Create a catalog file: A catalog file contains a collection of cryptographic hashes or thumbprints.</span></span> <span data-ttu-id="069d6-176">Каждый отпечаток соответствует файлу, включенному в модуль.</span><span class="sxs-lookup"><span data-stu-id="069d6-176">Each thumbprint corresponds to a file that is included in the module.</span></span> <span data-ttu-id="069d6-177">Был добавлен новый командлет [New-FileCatalog](/powershell/module/microsoft.powershell.security/new-filecatalog), благодаря которому пользователи могут создавать файлы каталогов для своих модулей.</span><span class="sxs-lookup"><span data-stu-id="069d6-177">The new cmdlet [New-FileCatalog](/powershell/module/microsoft.powershell.security/new-filecatalog), has been added to enable users to create a catalog file for their module.</span></span>
  2. <span data-ttu-id="069d6-178">Подпишите файл каталога: подпишите файл каталога с помощью командлета [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature).</span><span class="sxs-lookup"><span data-stu-id="069d6-178">Sign the catalog file: Use [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) to sign the catalog file.</span></span>
  3. <span data-ttu-id="069d6-179">Поместите файл каталога в папку модуля.</span><span class="sxs-lookup"><span data-stu-id="069d6-179">Place the catalog file inside the module folder.</span></span> <span data-ttu-id="069d6-180">По соглашению файл каталога модуля должен находиться в папке модуля и имя файла каталога модуля должно совпадать с именем модуля.</span><span class="sxs-lookup"><span data-stu-id="069d6-180">By convention, module catalog file should be placed under the module folder with the same name as the module.</span></span>

### <a name="localconfigurationmanager-settings-to-enable-signing-validations"></a><span data-ttu-id="069d6-181">Параметры локального диспетчера конфигураций для включения проверки подписи</span><span class="sxs-lookup"><span data-stu-id="069d6-181">LocalConfigurationManager settings to enable signing validations</span></span>

#### <a name="pull"></a><span data-ttu-id="069d6-182">По запросу</span><span class="sxs-lookup"><span data-stu-id="069d6-182">Pull</span></span>

<span data-ttu-id="069d6-183">Локальный диспетчер конфигураций узла выполняет проверку подписи модулей и конфигураций в соответствии со своими текущими параметрами.</span><span class="sxs-lookup"><span data-stu-id="069d6-183">The LocalConfigurationManager of a node performs signing validation of modules and configurations based on its current settings.</span></span> <span data-ttu-id="069d6-184">По умолчанию проверка подписи отключена.</span><span class="sxs-lookup"><span data-stu-id="069d6-184">By default, signature validation is disabled.</span></span> <span data-ttu-id="069d6-185">Проверку подписи можно включить, добавив блок "SignatureValidation" в определение метаконфигурации узла, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="069d6-185">Signature validation can enabled by adding the ‘SignatureValidation’ block to the meta-configuration definition of the node as shown below:</span></span>

```powershell
[DSCLocalConfigurationManager()]
Configuration EnableSignatureValidation
{
    Settings
    {
        RefreshMode = 'PULL'
    }

    ConfigurationRepositoryWeb pullserver{
      ConfigurationNames = 'sql'
      ServerURL = 'http://localhost:8080/PSDSCPullServer/PSDSCPullServer.svc'
      AllowUnsecureConnection = $true
      RegistrationKey = 'd6750ff1-d8dd-49f7-8caf-7471ea9793fc' # Replace this with correct registration key.
    }
    SignatureValidation validations{
        # If the TrustedStorePath property is provided then LCM will use the custom path. Otherwise, the LCM will use default trusted store path (Cert:\LocalMachine\DSCStore) to find the signing certificate.
        TrustedStorePath = 'Cert:\LocalMachine\DSCStore'
        SignedItemType = 'Configuration','Module'         # This is a list of DSC artifacts, for which LCM need to verify their digital signature before executing them on the node.
    }

}
EnableSignatureValidation
Set-DscLocalConfigurationManager -Path .\EnableSignatureValidation -Verbose
```

<span data-ttu-id="069d6-186">Установка приведенной выше метаконфигурации для узла включает проверку подписи для загруженных конфигураций и модулей.</span><span class="sxs-lookup"><span data-stu-id="069d6-186">Setting the above metaconfiguration on a node enables signature validation on downloaded configurations and modules.</span></span> <span data-ttu-id="069d6-187">Для проверки цифровых подписей локальный диспетчер конфигураций выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="069d6-187">The Local Configuration Manager performs the following steps to verify the digital signatures.</span></span>

1. <span data-ttu-id="069d6-188">Проверьте подпись в файле конфигурации (MOF-файл) с помощью командлета `Get-AuthenticodeSignature`.</span><span class="sxs-lookup"><span data-stu-id="069d6-188">Verify the signature on a configuration file (.MOF) is valid using the `Get-AuthenticodeSignature` cmdlet.</span></span>
2. <span data-ttu-id="069d6-189">Убедитесь, что центр сертификации, который авторизовал подписывающую сторону, является доверенным.</span><span class="sxs-lookup"><span data-stu-id="069d6-189">Verify the certificate authority that authorized the signer is trusted.</span></span>
3. <span data-ttu-id="069d6-190">Скачайте зависимости модуля или ресурса конфигурации во временный каталог.</span><span class="sxs-lookup"><span data-stu-id="069d6-190">Download module/resource dependencies of the configuration to a temp location.</span></span>
4. <span data-ttu-id="069d6-191">Проверьте подпись каталога, включенного в модуль.</span><span class="sxs-lookup"><span data-stu-id="069d6-191">Verify the signature of the catalog included inside the module.</span></span>
   - <span data-ttu-id="069d6-192">Найдите файл `<moduleName>.cat` и проверьте его подпись с помощью командлета `Get-AuthenticodeSignature`.</span><span class="sxs-lookup"><span data-stu-id="069d6-192">Find a `<moduleName>.cat` file and verify its signature using `Get-AuthenticodeSignature`.</span></span>
   - <span data-ttu-id="069d6-193">Проверьте центр сертификации, который проверил подлинность доверенного лица.</span><span class="sxs-lookup"><span data-stu-id="069d6-193">Verify the certification authority that authenticated the signer is trusted.</span></span>
   - <span data-ttu-id="069d6-194">Проверьте, чтобы содержимое модулей не было изменено, с помощью нового командлета `Test-FileCatalog`.</span><span class="sxs-lookup"><span data-stu-id="069d6-194">Verify the content of the modules has not been tampered using the new cmdlet `Test-FileCatalog`.</span></span>
5. <span data-ttu-id="069d6-195">Запустите командлет `Install-Module` для установки по пути `$env:ProgramFiles\WindowsPowerShell\Modules\`.</span><span class="sxs-lookup"><span data-stu-id="069d6-195">`Install-Module` to `$env:ProgramFiles\WindowsPowerShell\Modules\`</span></span>
6. <span data-ttu-id="069d6-196">Выполните конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="069d6-196">Process configuration</span></span>

> [!NOTE]
> <span data-ttu-id="069d6-197">Проверка подписи каталога модуля и конфигурации выполняется только при первом применении конфигурации к системе или при скачивании и установке модуля.</span><span class="sxs-lookup"><span data-stu-id="069d6-197">Signature validation on module-catalog and configuration is only performed when the configuration is applied to the system for the first time or when the module is downloaded and installed.</span></span>
> <span data-ttu-id="069d6-198">При проверке на согласованность не проверяется подпись файла Current.mof и зависимости для его модулей.</span><span class="sxs-lookup"><span data-stu-id="069d6-198">Consistency runs do not validate the signature of Current.mof or its module dependencies.</span></span> <span data-ttu-id="069d6-199">Если проверка на любом этапе завершается неудачно, например если конфигурация, полученная с опрашивающего сервера, не подписана, обработка конфигурации завершается ошибкой, показанной ниже, и все временные файлы удаляются.</span><span class="sxs-lookup"><span data-stu-id="069d6-199">If verification has failed at any stage, for instance, if the configuration pulled from the pull server is unsigned, then processing of the configuration terminates with the error shown below and all temporary files are deleted.</span></span>

![Пример ошибки конфигурации](../images/DSC-improvements/PullUnsignedConfigFail.png)

<span data-ttu-id="069d6-201">Точно так же при попытке получить модуль, каталог для которого не подписан, появляется следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="069d6-201">Similarly, pulling a module whose catalog is not signed results in the following error:</span></span>

![Пример ошибки модуля](../images/DSC-improvements/PullUnisgnedCatalog.png)

#### <a name="push"></a><span data-ttu-id="069d6-203">Принудительная отправка</span><span class="sxs-lookup"><span data-stu-id="069d6-203">Push</span></span>

<span data-ttu-id="069d6-204">Конфигурация, переданная на узел с помощью принудительной отправки, может быть изменена злоумышленником в месте ее отправки.</span><span class="sxs-lookup"><span data-stu-id="069d6-204">A configuration delivered by using push might be tampered with at its source before it delivered to the node.</span></span> <span data-ttu-id="069d6-205">Локальный диспетчер конфигураций выполняет похожие действия для проверки подписи принудительно отправленных и опубликованных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="069d6-205">The Local Configuration Manager performs similar signature validation steps for pushed or published configuration(s).</span></span> <span data-ttu-id="069d6-206">Ниже приведен полный пример проверки подписи для принудительной отправки.</span><span class="sxs-lookup"><span data-stu-id="069d6-206">Below is a complete example of signature validation for push.</span></span>

- <span data-ttu-id="069d6-207">Включите проверку подписи на узле.</span><span class="sxs-lookup"><span data-stu-id="069d6-207">Enable signature validation on the node.</span></span>

  ```powershell
  [DSCLocalConfigurationManager()]
  Configuration EnableSignatureValidation
  {
      Settings
      {
          RefreshMode = 'PUSH'
      }
      SignatureValidation validations{
          TrustedStorePath = 'Cert:\LocalMachine\DSCStore'
          SignedItemType =  'Configuration','Module'
      }

  }
  EnableSignatureValidation
  Set-DscLocalConfigurationManager -Path .\EnableSignatureValidation -Verbose
  ```

- <span data-ttu-id="069d6-208">Создайте пример файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="069d6-208">Create a sample configuration file.</span></span>

  ```powershell
  # Sample configuration
  Configuration Test
  {

      File foo
      {
          DestinationPath =  "$env:TEMP\signingTest.txt"
          Contents = "ABC"
      }
  }
  Test
  ```

- <span data-ttu-id="069d6-209">Попробуйте принудительно отправить не подписанный файл конфигурации на узел.</span><span class="sxs-lookup"><span data-stu-id="069d6-209">Try pushing the unsigned configuration file in to the node.</span></span>

  ```powershell
  Start-DscConfiguration -Path .\Test -Wait -Verbose -Force
  ```

  ![Ошибка "MOF-файл не подписан"](../images/DSC-improvements/PushUnsignedMof.png)

- <span data-ttu-id="069d6-211">Подпишите файл конфигурации с помощью сертификата подписи кода.</span><span class="sxs-lookup"><span data-stu-id="069d6-211">Sign the configuration file using code-signing certificate.</span></span>

  ![Подписанный MOF-файл](../images/DSC-improvements/SignMofFile.png)

- <span data-ttu-id="069d6-213">Попробуйте отправить подписанный MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="069d6-213">Try pushing the signed MOF file.</span></span>

  ![PushSignedMofFile](../images/DSC-improvements/PushSignedMof.png)
