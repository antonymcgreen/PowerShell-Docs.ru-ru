---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Group в DSC
ms.openlocfilehash: 9894150f6f749fc23efd4ce2b155b18788557d1d
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047572"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="5e8ca-103">Ресурс Group в DSC</span><span class="sxs-lookup"><span data-stu-id="5e8ca-103">DSC Group Resource</span></span>

> <span data-ttu-id="5e8ca-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5e8ca-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="5e8ca-105">Ресурс Group в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-105">The Group resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e8ca-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e8ca-106">Syntax</span></span>

```
Group [string] #ResourceName
{
    GroupName          = [string]
    [ Credential       = [PSCredential] ]
    [ Description      = [string[]] ]
    [ Ensure           = [string] { Absent | Present }  ]
    [ Members          = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn        = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="5e8ca-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5e8ca-107">Properties</span></span>

|  <span data-ttu-id="5e8ca-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="5e8ca-108">Property</span></span>  |  <span data-ttu-id="5e8ca-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5e8ca-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="5e8ca-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="5e8ca-110">GroupName</span></span>| <span data-ttu-id="5e8ca-111">Имя группы, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-111">The name of the group for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="5e8ca-112">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="5e8ca-112">Credential</span></span>| <span data-ttu-id="5e8ca-113">Учетные данные, необходимые для доступа к удаленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="5e8ca-114">**Примечание**. Учетная запись должна иметь соответствующие разрешения Active Directory на добавление в группу любых нелокальных учетных записей. Иначе во время выполнения конфигурации на целевом узле произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-114">**Note**: This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
| <span data-ttu-id="5e8ca-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5e8ca-115">Description</span></span>| <span data-ttu-id="5e8ca-116">Описание группы.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-116">The description of the group.</span></span>|
| <span data-ttu-id="5e8ca-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="5e8ca-117">Ensure</span></span>| <span data-ttu-id="5e8ca-118">Указывает, существует ли группа.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-118">Indicates if the group exists.</span></span> <span data-ttu-id="5e8ca-119">Чтобы убедиться, что группа не существует, укажите для этого свойства значение Absent.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-119">Set this property to "Absent" to ensure that the group does not exist.</span></span> <span data-ttu-id="5e8ca-120">Чтобы убедиться, что группа существует, укажите для этого свойства значение Present (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5e8ca-120">Setting it to "Present" (the default value) ensures that the group exists.</span></span>|
| <span data-ttu-id="5e8ca-121">Члены группы</span><span class="sxs-lookup"><span data-stu-id="5e8ca-121">Members</span></span>| <span data-ttu-id="5e8ca-122">Используйте это свойство для замены текущего членства в группе заданными участниками.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-122">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="5e8ca-123">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-123">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="5e8ca-124">Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-124">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="5e8ca-125">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-125">Doing so generates an error.</span></span>|
| <span data-ttu-id="5e8ca-126">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="5e8ca-126">MembersToExclude</span></span>| <span data-ttu-id="5e8ca-127">Это свойство используется для удаления участников из существующего членства в группе.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-127">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="5e8ca-128">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-128">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="5e8ca-129">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-129">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="5e8ca-130">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-130">Doing so generates an error.</span></span>|
| <span data-ttu-id="5e8ca-131">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="5e8ca-131">MembersToInclude</span></span>| <span data-ttu-id="5e8ca-132">Это свойство используется для добавления участников в существующее членство в группе.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-132">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="5e8ca-133">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-133">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="5e8ca-134">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-134">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="5e8ca-135">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-135">Doing so will generate an error.</span></span>|
| <span data-ttu-id="5e8ca-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="5e8ca-136">DependsOn</span></span> | <span data-ttu-id="5e8ca-137">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="5e8ca-138">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".</span><span class="sxs-lookup"><span data-stu-id="5e8ca-138">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|

## <a name="example-1"></a><span data-ttu-id="5e8ca-139">Пример 1</span><span class="sxs-lookup"><span data-stu-id="5e8ca-139">Example 1</span></span>

<span data-ttu-id="5e8ca-140">Следующий пример показывает, как проверить, что группа с именем TestGroup не существует.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-140">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present“
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2"></a><span data-ttu-id="5e8ca-141">Пример 2.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-141">Example 2</span></span>

<span data-ttu-id="5e8ca-142">Следующий пример демонстрирует добавление пользователя Active Directory в группу локальных администраторов в лабораторной сборке с несколькими компьютерами, в которой уже используется объект PSCredential для учетной записи локального администратора.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-142">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Adminstrator account.</span></span>
<span data-ttu-id="5e8ca-143">Так как этот объект также используется для учетной записи администратора домена (после повышения роли домена), нам потребуется преобразовать этот существующий объект PSCredential в понятные учетные данные домена.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-143">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span>
<span data-ttu-id="5e8ca-144">Затем мы сможем добавить пользователя домена в группу локальных администраторов на рядовом сервере.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-144">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a><span data-ttu-id="5e8ca-145">Пример 3</span><span class="sxs-lookup"><span data-stu-id="5e8ca-145">Example 3</span></span>

<span data-ttu-id="5e8ca-146">В примере ниже показано, как настроить локальную группу TigerTeamAdmins на сервере TigerTeamSource.Contoso.Com, чтобы она не содержала определенную учетную запись домена Contoso\JerryG.</span><span class="sxs-lookup"><span data-stu-id="5e8ca-146">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

```powershell
Configuration SecureTigerTeamSrouce {
  Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

  Node TigerTeamSource.Contoso.Com {
    Group TigerTeamAdmins {
       GroupName        = 'TigerTeamAdmins'
       Ensure           = 'Present'
       MembersToExclude = "Contoso\JerryG"
    }
  }
}
```