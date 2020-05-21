---
title: Создание файла Web. config для веб-службы OData управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569f5d5-9746-40c0-be5e-f218bc4560f7
caps.latest.revision: 4
ms.openlocfilehash: 8e5897c3df38689e80d2135dfb82898bf9a05b86
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561487"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a><span data-ttu-id="d6ec2-102">Создание файла Web.config для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-102">Authoring the Web.config file for a Management OData web service</span></span>

<span data-ttu-id="d6ec2-103">Перед развертыванием веб-службы OData управления необходимо настроить файл Web. config так, чтобы он указывал на файлы схемы XML и библиотеки DLL, реализующие интерфейсы [Microsoft. Management. OData. кустомаусоризатион](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) и [System. Management. Automation. Remoting. PSSessionConfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d6ec2-103">Before you can deploy your Management OData web service, you must configure the web.config file to point to the XML schema files and the DLLs that implement the [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) and [System.Management.Automation.Remoting.Pssessionconfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) interfaces.</span></span>

## <a name="sample-config-file"></a><span data-ttu-id="d6ec2-104">Пример файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d6ec2-104">Sample config file</span></span>

<span data-ttu-id="d6ec2-105">Ниже приведен пример того, как выглядит файл Web. config для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="d6ec2-105">The following is an example of what the web.config file for your web service looks like.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
   <configSections>
      <section name="managementOdata" type="Microsoft.Management.Odata.Core.DSConfiguration, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL" />
   </configSections>
   <managementOdata schemaFileName="Schema.mof" resourceMappingFileName="Schema.xml">
      <customAuthorization type="Microsoft.Samples.Management.OData.RoleBasedPlugins.CustomAuthorization" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      <powershell>
         <sessionConfiguration type="Microsoft.Samples.Management.OData.RoleBasedPlugins.SessionConfiguration" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      </powershell>
      <commandInvocation enabled="true" />
      <wcfDataServicesConfig>
      </wcfDataServicesConfig>
   </managementOdata>
   <system.serviceModel>
      <behaviors>
         <serviceBehaviors>
            <behavior>
                  <serviceAuthorization serviceAuthorizationManagerType="Microsoft.Management.Odata.Core.CustomAuthorizationManager, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
            </behavior>
         </serviceBehaviors>
      </behaviors>
      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
   </system.serviceModel>
   <system.webServer>
      <security>
         <authentication>
            <anonymousAuthentication enabled="false" />
            <basicAuthentication enabled="true" />
            <windowsAuthentication enabled="false" />
         </authentication>
      </security>
  </system.webServer>
</configuration>

```

## <a name="see-also"></a><span data-ttu-id="d6ec2-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6ec2-106">See Also</span></span>

[<span data-ttu-id="d6ec2-107">Реализация пользовательской авторизации для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-107">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[<span data-ttu-id="d6ec2-108">Реализация SessionConfiguration для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-108">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[<span data-ttu-id="d6ec2-109">Создание файла схемы MOF для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-109">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[<span data-ttu-id="d6ec2-110">Создание файла схемы XML для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-110">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[<span data-ttu-id="d6ec2-111">Создание веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6ec2-111">Creating a Management OData Web Service</span></span>](./creating-a-management-odata-web-service.md)
