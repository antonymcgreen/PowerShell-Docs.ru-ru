---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
description: Предоставляет механизм для управления локальными группами на целевом узле.
title: Ресурс DSC GroupSet
ms.openlocfilehash: 90e0c3f0e09c6a300988869265dfdb432ed5d217
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464201"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="0fbf5-104">Ресурс DSC GroupSet</span><span class="sxs-lookup"><span data-stu-id="0fbf5-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="0fbf5-105">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="0fbf5-105">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="0fbf5-106">Ресурс **GroupSet** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="0fbf5-107">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Group](groupResource.md) для каждой группы, указанной в параметре `GroupName`.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-107">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="0fbf5-108">Используйте этот ресурс, если необходимо добавить один и тот же список участников в несколько групп или удалить его из нескольких групп, а также если необходимо удалить или добавить несколько групп с одинаковым списком участников.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fbf5-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fbf5-109">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="0fbf5-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="0fbf5-110">Properties</span></span>

|<span data-ttu-id="0fbf5-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="0fbf5-111">Property</span></span> |<span data-ttu-id="0fbf5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0fbf5-112">Description</span></span> |
|---|---|
|<span data-ttu-id="0fbf5-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="0fbf5-113">GroupName</span></span> |<span data-ttu-id="0fbf5-114">Имена групп, для которых требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-114">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="0fbf5-115">Члены</span><span class="sxs-lookup"><span data-stu-id="0fbf5-115">Members</span></span> |<span data-ttu-id="0fbf5-116">Используйте это свойство для замены текущего членства в группе заданными участниками.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-116">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="0fbf5-117">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-117">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="0fbf5-118">Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-118">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="0fbf5-119">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-119">Doing so will generate an error.</span></span> |
|<span data-ttu-id="0fbf5-120">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="0fbf5-120">MembersToInclude</span></span> |<span data-ttu-id="0fbf5-121">Это свойство используется для добавления участников в существующее членство в группе.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-121">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="0fbf5-122">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-122">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="0fbf5-123">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-123">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="0fbf5-124">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-124">Doing so will generate an error.</span></span> |
|<span data-ttu-id="0fbf5-125">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="0fbf5-125">MembersToExclude</span></span> |<span data-ttu-id="0fbf5-126">Это свойство используется для удаления участников из существующего членства в группах.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-126">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="0fbf5-127">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-127">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="0fbf5-128">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-128">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="0fbf5-129">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-129">Doing so will generate an error.</span></span> |
|<span data-ttu-id="0fbf5-130">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="0fbf5-130">Credential</span></span> |<span data-ttu-id="0fbf5-131">Учетные данные, необходимые для доступа к удаленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-131">The credentials required to access remote resources.</span></span> <span data-ttu-id="0fbf5-132">Учетная запись должна иметь соответствующие разрешения Active Directory для добавления в группу любых нелокальных учетных записей; в противном случае произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-132">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="0fbf5-133">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="0fbf5-133">Common properties</span></span>

|<span data-ttu-id="0fbf5-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="0fbf5-134">Property</span></span> |<span data-ttu-id="0fbf5-135">Описание</span><span class="sxs-lookup"><span data-stu-id="0fbf5-135">Description</span></span> |
|---|---|
|<span data-ttu-id="0fbf5-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0fbf5-136">DependsOn</span></span> |<span data-ttu-id="0fbf5-137">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0fbf5-138">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="0fbf5-139">Ensure</span><span class="sxs-lookup"><span data-stu-id="0fbf5-139">Ensure</span></span> |<span data-ttu-id="0fbf5-140">Указывает, существуют ли группы.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-140">Indicates whether the groups exist.</span></span> <span data-ttu-id="0fbf5-141">Если группы не должны существовать, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-141">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="0fbf5-142">Если группы должны существовать, укажите для этого свойства значение **Present** (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0fbf5-142">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="0fbf5-143">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-143">The default value is **Present**.</span></span> |
|<span data-ttu-id="0fbf5-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="0fbf5-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="0fbf5-145">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="0fbf5-146">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="0fbf5-147">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="0fbf5-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="0fbf5-148">Пример 1. Проверка наличия групп</span><span class="sxs-lookup"><span data-stu-id="0fbf5-148">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="0fbf5-149">В приведенном ниже примере показано, как обеспечить существование двух групп: myGroup и myOtherGroup.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-149">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="0fbf5-150">Для простоты в этом примере используются учетные данные в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="0fbf5-150">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="0fbf5-151">Сведения о шифровании учетных данных в MOF-файле конфигурации см. в разделе [Защита MOF-файла](../../../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="0fbf5-151">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>
