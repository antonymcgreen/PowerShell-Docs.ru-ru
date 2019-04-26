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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080685"
---
# <a name="configuring-role-based-authorization"></a><span data-ttu-id="36e25-102">Настройка авторизации на основе ролей</span><span class="sxs-lookup"><span data-stu-id="36e25-102">Configuring Role-based Authorization</span></span>

<span data-ttu-id="36e25-103">В этом разделе показано, как настроить политику авторизации на основе ролей для реализации примера [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) интерфейс, описанный в [реализации пользовательских Авторизация для расширение OData IIS для управления](./implementing-custom-authorization-for-a-management-odata-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="36e25-103">This topic demonstrates how to configure the role-based authorization policy for the sample implementation of the [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) interface described in [Implementing Custom Authorization for Management OData IIS Extension](./implementing-custom-authorization-for-a-management-odata-web-service.md).</span></span>

<span data-ttu-id="36e25-104">В этом примере вы настроите XML-файл, который используется образцом приложения OData для управления для определения политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="36e25-104">In this example, you will configure an XML file that is used by the sample Management OData application to define the authorization policy.</span></span> <span data-ttu-id="36e25-105">Вы создадите две роли и связать различные модули Windows PowerShell, которые содержат рабочих процессов с помощью этих ролей.</span><span class="sxs-lookup"><span data-stu-id="36e25-105">You will create two roles and associate different Windows PowerShell modules that contain workflows with those roles.</span></span> <span data-ttu-id="36e25-106">Указано схему, которая определяет XML-файле в [ролей схема конфигурации авторизации](./role-based-authorization-configuration-schema.md).</span><span class="sxs-lookup"><span data-stu-id="36e25-106">The schema that defines the XML file is listed at [Role-Based Authorization Configuration Schema](./role-based-authorization-configuration-schema.md).</span></span>

## <a name="modifying-the-rbacconfigurationxml-file"></a><span data-ttu-id="36e25-107">Изменение файла RBacConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="36e25-107">Modifying the RBacConfiguration.xml File</span></span>

<span data-ttu-id="36e25-108">Этот файл определяет политику авторизации для приложения.</span><span class="sxs-lookup"><span data-stu-id="36e25-108">This file defines the authorization policy for the application.</span></span> <span data-ttu-id="36e25-109">Роли определяются с помощью `Group` узлов.</span><span class="sxs-lookup"><span data-stu-id="36e25-109">Roles are defined by using `Group` nodes.</span></span> <span data-ttu-id="36e25-110">Объект `Group` узел определяет команды Windows PowerShell, которые можно запускать пользователи, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="36e25-110">A `Group` node defines the Windows PowerShell commands that users assigned to that group can run.</span></span> <span data-ttu-id="36e25-111">Пользователи назначаются группам с помощью `User` узлов.</span><span class="sxs-lookup"><span data-stu-id="36e25-111">Users are assigned to groups by using `User` nodes.</span></span>

<span data-ttu-id="36e25-112">В этих примерах вы добавите модуль администратору `Group` узел, и добавьте пользователя к каждой группе.</span><span class="sxs-lookup"><span data-stu-id="36e25-112">In these examples, you will add a module to the Administrator `Group` node, and add a user to each group.</span></span>

#### <a name="adding-a-module-to-a-group-node"></a><span data-ttu-id="36e25-113">Добавление модуля в узел группы</span><span class="sxs-lookup"><span data-stu-id="36e25-113">Adding a Module to a Group Node</span></span>

1. <span data-ttu-id="36e25-114">Создайте файл с именем **RBacConfiguration.xml** в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="36e25-114">Create a file named **RBacConfiguration.xml** in a text editor.</span></span> <span data-ttu-id="36e25-115">Этот файл должен сохраняться в каталог основного приложения для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="36e25-115">This file should be saved to the main application directory for your web service.</span></span> <span data-ttu-id="36e25-116">Вставьте следующий текст в файле.</span><span class="sxs-lookup"><span data-stu-id="36e25-116">Insert the following text in the file.</span></span>

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

2. <span data-ttu-id="36e25-117">Файл содержит два `Group` узлов.</span><span class="sxs-lookup"><span data-stu-id="36e25-117">The file contains two `Group` nodes.</span></span> <span data-ttu-id="36e25-118">Они представляют собой две роли, используемые в этом примере `NonAdminGroup` и `AdminGroup` ролей.</span><span class="sxs-lookup"><span data-stu-id="36e25-118">These represent the two roles used in this example, the `NonAdminGroup` and the `AdminGroup` roles.</span></span>

   <span data-ttu-id="36e25-119">Непосредственно после закрывающего `Cmdlets` тег в первом `Group` узел, добавьте следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="36e25-119">Directly after the closing `Cmdlets` tag in the first `Group` node, add the following XML:</span></span>

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a><span data-ttu-id="36e25-120">Добавление пользователя в узел группы</span><span class="sxs-lookup"><span data-stu-id="36e25-120">Adding a User to a Group Node</span></span>

1. <span data-ttu-id="36e25-121">Откройте **RBacConfiguration.xml** файл в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="36e25-121">Open the **RBacConfiguration.xml** file in a text editor.</span></span> <span data-ttu-id="36e25-122">Этот файл находится в папке C:\\\inetpub\wwwroot\Modata Если вы не изменяли имя конечной точки перед установкой.</span><span class="sxs-lookup"><span data-stu-id="36e25-122">This file is located in the folder C:\\\inetpub\wwwroot\Modata  if you did not change the endpoint name before installation.</span></span>

2. <span data-ttu-id="36e25-123">Непосредственно после закрывающего тега в `Users` узел, добавьте следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="36e25-123">Directly after the closing tag in the `Users` node, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. <span data-ttu-id="36e25-124">Непосредственно после добавления XML-код на предыдущем шаге, добавьте следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="36e25-124">Directly after the XML added in the previous step, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```