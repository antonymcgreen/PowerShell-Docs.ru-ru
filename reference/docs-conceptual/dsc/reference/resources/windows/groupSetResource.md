---
ms.date: 09/20/2019
ms.topic: reference
title: Ресурс DSC GroupSet
description: Ресурс DSC GroupSet
ms.openlocfilehash: a9d1803aca40ac3571d42a5fd762489c03ed274e
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142894"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="a8ff3-103">Ресурс DSC GroupSet</span><span class="sxs-lookup"><span data-stu-id="a8ff3-103">DSC GroupSet Resource</span></span>

> <span data-ttu-id="a8ff3-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="a8ff3-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="a8ff3-105">Ресурс **GroupSet** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-105">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="a8ff3-106">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Group](groupResource.md) для каждой группы, указанной в параметре `GroupName`.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="a8ff3-107">Используйте этот ресурс, если необходимо добавить один и тот же список участников в несколько групп или удалить его из нескольких групп, а также если необходимо удалить или добавить несколько групп с одинаковым списком участников.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-107">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="a8ff3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8ff3-108">Syntax</span></span>

```Syntax
GroupSet [string] #ResourceName
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

## <a name="properties"></a><span data-ttu-id="a8ff3-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="a8ff3-109">Properties</span></span>

|<span data-ttu-id="a8ff3-110">Свойство.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-110">Property</span></span> |<span data-ttu-id="a8ff3-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a8ff3-111">Description</span></span> |
|---|---|
|<span data-ttu-id="a8ff3-112">GroupName</span><span class="sxs-lookup"><span data-stu-id="a8ff3-112">GroupName</span></span> |<span data-ttu-id="a8ff3-113">Имена групп, для которых требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-113">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="a8ff3-114">Члены</span><span class="sxs-lookup"><span data-stu-id="a8ff3-114">Members</span></span> |<span data-ttu-id="a8ff3-115">Используйте это свойство для замены текущего членства в группе заданными участниками.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-115">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="a8ff3-116">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-116">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="a8ff3-117">Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude** .</span><span class="sxs-lookup"><span data-stu-id="a8ff3-117">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="a8ff3-118">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-118">Doing so will generate an error.</span></span> |
|<span data-ttu-id="a8ff3-119">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="a8ff3-119">MembersToInclude</span></span> |<span data-ttu-id="a8ff3-120">Это свойство используется для добавления участников в существующее членство в группе.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-120">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="a8ff3-121">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-121">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="a8ff3-122">Если вы задали это свойство в конфигурации, не используйте свойство **Members** .</span><span class="sxs-lookup"><span data-stu-id="a8ff3-122">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="a8ff3-123">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-123">Doing so will generate an error.</span></span> |
|<span data-ttu-id="a8ff3-124">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="a8ff3-124">MembersToExclude</span></span> |<span data-ttu-id="a8ff3-125">Это свойство используется для удаления участников из существующего членства в группах.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-125">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="a8ff3-126">Значение этого свойства хранится в массиве строк в формате `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-126">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="a8ff3-127">Если вы задали это свойство в конфигурации, не используйте свойство **Members** .</span><span class="sxs-lookup"><span data-stu-id="a8ff3-127">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="a8ff3-128">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-128">Doing so will generate an error.</span></span> |
|<span data-ttu-id="a8ff3-129">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="a8ff3-129">Credential</span></span> |<span data-ttu-id="a8ff3-130">Учетные данные, необходимые для доступа к удаленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-130">The credentials required to access remote resources.</span></span> <span data-ttu-id="a8ff3-131">Учетная запись должна иметь соответствующие разрешения Active Directory для добавления в группу любых нелокальных учетных записей; в противном случае произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-131">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="a8ff3-132">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="a8ff3-132">Common properties</span></span>

|<span data-ttu-id="a8ff3-133">Свойство</span><span class="sxs-lookup"><span data-stu-id="a8ff3-133">Property</span></span> |<span data-ttu-id="a8ff3-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a8ff3-134">Description</span></span> |
|---|---|
|<span data-ttu-id="a8ff3-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a8ff3-135">DependsOn</span></span> |<span data-ttu-id="a8ff3-136">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a8ff3-137">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="a8ff3-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="a8ff3-138">Ensure</span></span> |<span data-ttu-id="a8ff3-139">Указывает, существуют ли группы.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-139">Indicates whether the groups exist.</span></span> <span data-ttu-id="a8ff3-140">Если группы не должны существовать, укажите для этого свойства значение **Absent** .</span><span class="sxs-lookup"><span data-stu-id="a8ff3-140">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="a8ff3-141">Если группы должны существовать, укажите для этого свойства значение **Present** (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a8ff3-141">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="a8ff3-142">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="a8ff3-142">The default value is **Present** .</span></span> |
|<span data-ttu-id="a8ff3-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="a8ff3-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="a8ff3-144">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="a8ff3-145">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="a8ff3-146">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="a8ff3-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="a8ff3-147">Пример 1. Проверка наличия групп</span><span class="sxs-lookup"><span data-stu-id="a8ff3-147">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="a8ff3-148">В приведенном ниже примере показано, как обеспечить существование двух групп: myGroup и myOtherGroup.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-148">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

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
> <span data-ttu-id="a8ff3-149">Для простоты в этом примере используются учетные данные в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="a8ff3-149">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="a8ff3-150">Сведения о шифровании учетных данных в MOF-файле конфигурации см. в разделе [Защита MOF-файла](../../../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="a8ff3-150">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>
