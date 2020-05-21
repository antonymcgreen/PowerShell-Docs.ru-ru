---
title: Настройка авторизации на основе ролей | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2933a6ca-fe92-4ba2-97ee-ef0f0d5fdfcf
caps.latest.revision: 8
ms.openlocfilehash: 2c9d6040b7a9c17dc5204c8eb835fd69780f62c5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564263"
---
# <a name="configuring-role-based-authorization"></a>Настройка авторизации на основе ролей

В этом разделе показано, как настроить политику авторизации на основе ролей для примера реализации интерфейса [Microsoft. Management. OData. кустомаусоризатион](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) , описанного в статье [Реализация пользовательской авторизации для расширения IIS OData для управления](./implementing-custom-authorization-for-a-management-odata-web-service.md).

В этом примере будет настроен XML-файл, используемый примером приложения управления OData для определения политики авторизации. Вы создадите две роли и свяжете различные модули Windows PowerShell, содержащие рабочие процессы с этими ролями. Схема, определяющая XML-файл, указана в [схеме конфигурации авторизации на основе ролей](./role-based-authorization-configuration-schema.md).

## <a name="modifying-the-rbacconfigurationxml-file"></a>Изменение файла Рбакконфигуратион. XML

Этот файл определяет политику авторизации для приложения. Роли определяются с помощью `Group` узлов. `Group`Узел определяет команды Windows PowerShell, которые могут выполняться пользователям, назначенным этой группе. Пользователи назначаются группам с помощью `User` узлов.

В этих примерах вы добавите модуль в `Group` узел администратора и добавите пользователя в каждую группу.

#### <a name="adding-a-module-to-a-group-node"></a>Добавление модуля в узел группы

1. Создайте файл с именем **рбакконфигуратион. XML** в текстовом редакторе. Этот файл должен быть сохранен в основном каталоге приложения для веб-службы. Вставьте следующий текст в файл.

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <RbacConfiguration>
     <Groups>
       <!--Group consists of the following:
         Name:  Name of the group
         UserName (Optional): Windows Identity user name
         Password (Optional): Password of the Windows user name
         DomainName (Optional): Domain for the user. For local machine account either do not include them or give the machine name. Do not give empty string
         MapIncomingUser (Optional): Boolean value indicating whether to execute cmdlet in the context of network client.

         User credentials and MapIncomingUser=true are exclusive.
       -->
       <Group Name="NonAdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Set-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
       </Group>
       <Group Name="AdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
         <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
       </Group>
     </Groups>
     <Users>
       <!-- User consists of the following :
         Name: Name of the user. If a user is from a cer
         AuthenticationType: Authentication type used.
         DomainName (Optional): Domain for the user
       -->
       <User Name="localNonAdmin" AuthenticationType="Basic" GroupName="NonAdminGroup" />
       <User Name="localAdmin" AuthenticationType="Basic" GroupName="AdminGroup" />
     </Users>
   </RbacConfiguration>
   ```

2. Файл содержит два `Group` узла. Они представляют две роли, используемые в этом примере, `NonAdminGroup` и `AdminGroup` роли.

   Сразу после закрывающего `Cmdlets` тега в первом `Group` узле добавьте следующий код XML:

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a>Добавление пользователя в узел группы

1. Откройте файл **рбакконфигуратион. XML** в текстовом редакторе. Этот файл находится в папке C: \Инетпуб\ввврут\модата, \\ Если имя конечной точки не было изменено перед установкой.

2. Сразу после закрывающего тега в `Users` узле добавьте следующий код XML:

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. Сразу после XML-кода, добавленного на предыдущем шаге, добавьте следующий код XML:

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```
