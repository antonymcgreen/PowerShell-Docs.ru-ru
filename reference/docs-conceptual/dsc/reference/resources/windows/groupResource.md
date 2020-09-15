---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Group в DSC
ms.openlocfilehash: 5570d46d872e205917eef49bfa869419b20a77b0
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464219"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="cbd05-103">Ресурс Group в DSC</span><span class="sxs-lookup"><span data-stu-id="cbd05-103">DSC Group Resource</span></span>

> <span data-ttu-id="cbd05-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="cbd05-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="cbd05-105">Ресурс **Group** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="cbd05-105">The **Group** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbd05-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbd05-106">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="cbd05-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="cbd05-107">Properties</span></span>

|<span data-ttu-id="cbd05-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="cbd05-108">Property</span></span> |<span data-ttu-id="cbd05-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cbd05-109">Description</span></span> |
|---|---|
|<span data-ttu-id="cbd05-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="cbd05-110">GroupName</span></span> |<span data-ttu-id="cbd05-111">Имя группы, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="cbd05-111">The name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="cbd05-112">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="cbd05-112">Credential</span></span> |<span data-ttu-id="cbd05-113">Учетные данные, необходимые для доступа к удаленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="cbd05-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="cbd05-114">Учетная запись должна иметь соответствующие разрешения Active Directory на добавление в группу любых нелокальных учетных записей. Иначе во время выполнения конфигурации на целевом узле произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="cbd05-114">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
|<span data-ttu-id="cbd05-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cbd05-115">Description</span></span> |<span data-ttu-id="cbd05-116">Описание группы.</span><span class="sxs-lookup"><span data-stu-id="cbd05-116">The description of the group.</span></span> |
|<span data-ttu-id="cbd05-117">Члены</span><span class="sxs-lookup"><span data-stu-id="cbd05-117">Members</span></span> |<span data-ttu-id="cbd05-118">Используйте это свойство для замены текущего членства в группе заданными участниками.</span><span class="sxs-lookup"><span data-stu-id="cbd05-118">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="cbd05-119">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="cbd05-119">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="cbd05-120">Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-120">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="cbd05-121">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="cbd05-121">Doing so generates an error.</span></span> |
|<span data-ttu-id="cbd05-122">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="cbd05-122">MembersToExclude</span></span> |<span data-ttu-id="cbd05-123">Это свойство используется для удаления участников из существующего членства в группе.</span><span class="sxs-lookup"><span data-stu-id="cbd05-123">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="cbd05-124">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="cbd05-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="cbd05-125">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="cbd05-126">Это приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="cbd05-126">Doing so generates an error.</span></span> |
|<span data-ttu-id="cbd05-127">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="cbd05-127">MembersToInclude</span></span> |<span data-ttu-id="cbd05-128">Это свойство используется для добавления участников в существующее членство в группе.</span><span class="sxs-lookup"><span data-stu-id="cbd05-128">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="cbd05-129">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="cbd05-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="cbd05-130">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="cbd05-131">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="cbd05-131">Doing so will generate an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="cbd05-132">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="cbd05-132">Common properties</span></span>

|<span data-ttu-id="cbd05-133">Свойство</span><span class="sxs-lookup"><span data-stu-id="cbd05-133">Property</span></span> |<span data-ttu-id="cbd05-134">Описание</span><span class="sxs-lookup"><span data-stu-id="cbd05-134">Description</span></span> |
|---|---|
|<span data-ttu-id="cbd05-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="cbd05-135">DependsOn</span></span> |<span data-ttu-id="cbd05-136">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="cbd05-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="cbd05-137">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="cbd05-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="cbd05-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="cbd05-138">Ensure</span></span> |<span data-ttu-id="cbd05-139">Указывает, существует ли группа.</span><span class="sxs-lookup"><span data-stu-id="cbd05-139">Indicates if the group exists.</span></span> <span data-ttu-id="cbd05-140">Чтобы убедиться, что группа не существует, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-140">Set this property to **Absent** to ensure that the group does not exist.</span></span> <span data-ttu-id="cbd05-141">Если группа должна существовать, укажите для этого свойства значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-141">Setting it to **Present** ensures that the group exists.</span></span> <span data-ttu-id="cbd05-142">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="cbd05-142">The default value is **Present**.</span></span> |
|<span data-ttu-id="cbd05-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="cbd05-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="cbd05-144">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="cbd05-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="cbd05-145">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="cbd05-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="cbd05-146">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="cbd05-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensure-group-is-not-present"></a><span data-ttu-id="cbd05-147">Пример 1: Убедитесь, что группа отсутствует</span><span class="sxs-lookup"><span data-stu-id="cbd05-147">Example 1: Ensure group is not present</span></span>

<span data-ttu-id="cbd05-148">Следующий пример показывает, как проверить, что группа с именем TestGroup не существует.</span><span class="sxs-lookup"><span data-stu-id="cbd05-148">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a><span data-ttu-id="cbd05-149">Пример 2. Добавление пользователя домена в локальную группу</span><span class="sxs-lookup"><span data-stu-id="cbd05-149">Example 2: Add domain user to local group</span></span>

<span data-ttu-id="cbd05-150">Следующий пример демонстрирует добавление пользователя Active Directory в группу локальных администраторов в лабораторной сборке с несколькими компьютерами, в которой уже используется объект PSCredential для учетной записи локального администратора.</span><span class="sxs-lookup"><span data-stu-id="cbd05-150">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Administrator account.</span></span> <span data-ttu-id="cbd05-151">Так как этот объект также используется для учетной записи администратора домена (после повышения роли домена), нам потребуется преобразовать этот существующий объект PSCredential в понятные учетные данные домена.</span><span class="sxs-lookup"><span data-stu-id="cbd05-151">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span> <span data-ttu-id="cbd05-152">Затем мы сможем добавить пользователя домена в группу локальных администраторов на рядовом сервере.</span><span class="sxs-lookup"><span data-stu-id="cbd05-152">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

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

## <a name="example-3"></a><span data-ttu-id="cbd05-153">Пример 3</span><span class="sxs-lookup"><span data-stu-id="cbd05-153">Example 3</span></span>

<span data-ttu-id="cbd05-154">В примере ниже показано, как настроить локальную группу TigerTeamAdmins на сервере TigerTeamSource.Contoso.Com, чтобы она не содержала определенную учетную запись домена Contoso\JerryG.</span><span class="sxs-lookup"><span data-stu-id="cbd05-154">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

```powershell
Configuration SecureTigerTeamSource {
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
