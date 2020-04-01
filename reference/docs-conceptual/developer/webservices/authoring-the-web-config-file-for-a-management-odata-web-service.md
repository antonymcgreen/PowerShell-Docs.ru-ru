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
ms.openlocfilehash: eee515252cf03c05d15368ee6e2a1cb62dc82647
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500786"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>Создание файла Web.config для веб-службы управления OData

Перед развертыванием веб-службы OData управления необходимо настроить файл Web. config так, чтобы он указывал на файлы схемы XML и библиотеки DLL, реализующие интерфейсы [Microsoft. Management. OData. кустомаусоризатион](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) и [System. Management. Automation. Remoting. PSSessionConfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) .

## <a name="sample-config-file"></a>Пример файла конфигурации

Ниже приведен пример того, как выглядит файл Web. config для веб-службы.

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

## <a name="see-also"></a>См. также:

[Реализация пользовательской авторизации для веб-службы OData управления](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[Реализация Сессионконфигуратион для веб-службы OData управления](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[Создание файла схемы MOF для веб-службы OData управления](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[Создание файла схемы XML для веб-службы OData управления](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[Создание веб-службы OData для управления](./creating-a-management-odata-web-service.md)