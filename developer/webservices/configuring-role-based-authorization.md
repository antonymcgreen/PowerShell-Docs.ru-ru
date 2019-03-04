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
ms.openlocfilehash: b73284adb4bf228510bf8134aa4c6a10561b7ea2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859600"
---
# <a name="configuring-role-based-authorization"></a>Настройка авторизации на основе ролей

В этом разделе показано, как настроить политику авторизации на основе ролей для реализации примера [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) интерфейс, описанный в [реализации пользовательских Авторизация для расширение OData IIS для управления](./implementing-custom-authorization-for-a-management-odata-web-service.md).

В этом примере вы настроите XML-файл, который используется образцом приложения OData для управления для определения политики авторизации. Вы создадите две роли и связать различные модули Windows PowerShell, которые содержат рабочих процессов с помощью этих ролей. Указано схему, которая определяет XML-файле в [ролей схема конфигурации авторизации](./role-based-authorization-configuration-schema.md).

## <a name="modifying-the-rbacconfigurationxml-file"></a>Изменение файла RBacConfiguration.xml

Этот файл определяет политику авторизации для приложения. Роли определяются с помощью `Group` узлов. Объект `Group` узел определяет команды Windows PowerShell, которые можно запускать пользователи, назначенные группе. Пользователи назначаются группам с помощью `User` узлов.

В этих примерах вы добавите модуль администратору `Group` узел, и добавьте пользователя к каждой группе.

#### <a name="adding-a-module-to-a-group-node"></a>Добавление модуля в узел группы

1. Создайте файл с именем **RBacConfiguration.xml** в текстовом редакторе. Этот файл должен сохраняться в каталог основного приложения для веб-службы. Вставьте следующий текст в файле.

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

2. Файл содержит два `Group` узлов. Они представляют собой две роли, используемые в этом примере `NonAdminGroup` и `AdminGroup` ролей.

   Непосредственно после закрывающего `Cmdlets` тег в первом `Group` узел, добавьте следующий код XML:

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a>Добавление пользователя в узел группы

1. Откройте **RBacConfiguration.xml** файл в текстовом редакторе. Этот файл находится в папке C:\\\inetpub\wwwroot\Modata Если вы не изменяли имя конечной точки перед установкой.

2. Непосредственно после закрывающего тега в `Users` узел, добавьте следующий код XML:

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. Непосредственно после добавления XML-код на предыдущем шаге, добавьте следующий код XML:

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```