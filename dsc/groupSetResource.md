---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
description: Предоставляет механизм для управления локальными группами на целевом узле.
title: Ресурс DSC GroupSet
ms.openlocfilehash: 487a76ca7703b2c57b940b4c5bd176eada6c8019
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892432"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="36140-104">Ресурс DSC GroupSet</span><span class="sxs-lookup"><span data-stu-id="36140-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="36140-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="36140-105">Applies To: Windows Windows PowerShell 5.0</span></span>

<span data-ttu-id="36140-106">Ресурс **GroupSet** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="36140-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="36140-107">Он является [составным ресурсом](authoringResourceComposite.md), который вызывает [ресурс Group](groupResource.md) для каждой группы, указанной в параметре `GroupName`.</span><span class="sxs-lookup"><span data-stu-id="36140-107">This resource is a [composite resource](authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="36140-108">Используйте этот ресурс, если необходимо добавить один и тот же список участников в несколько групп или удалить его из нескольких групп, а также если необходимо удалить или добавить несколько групп с одинаковым списком участников.</span><span class="sxs-lookup"><span data-stu-id="36140-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="36140-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36140-109">Syntax</span></span>

```
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Ensure = [string] { Absent | Present }  ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="36140-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="36140-110">Properties</span></span>

|  <span data-ttu-id="36140-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="36140-111">Property</span></span>  |  <span data-ttu-id="36140-112">Описание</span><span class="sxs-lookup"><span data-stu-id="36140-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="36140-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="36140-113">GroupName</span></span>| <span data-ttu-id="36140-114">Имена групп, для которых требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="36140-114">The names of the groups for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="36140-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="36140-115">MembersToExclude</span></span>| <span data-ttu-id="36140-116">Это свойство используется для удаления участников из существующего членства в группах.</span><span class="sxs-lookup"><span data-stu-id="36140-116">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="36140-117">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="36140-117">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="36140-118">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="36140-118">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="36140-119">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="36140-119">Doing so will generate an error.</span></span>|
| <span data-ttu-id="36140-120">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="36140-120">Credential</span></span>| <span data-ttu-id="36140-121">Учетные данные, необходимые для доступа к удаленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="36140-121">The credentials required to access remote resources.</span></span> <span data-ttu-id="36140-122">**Примечание**. Учетная запись должна иметь соответствующие разрешения Active Directory для добавления в группу любых нелокальных учетных записей; в противном случае произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="36140-122">**Note**: This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span>
| <span data-ttu-id="36140-123">Ensure</span><span class="sxs-lookup"><span data-stu-id="36140-123">Ensure</span></span>| <span data-ttu-id="36140-124">Указывает, существуют ли группы.</span><span class="sxs-lookup"><span data-stu-id="36140-124">Indicates whether the groups exist.</span></span> <span data-ttu-id="36140-125">Если группы не должны существовать, укажите для этого свойства значение Absent.</span><span class="sxs-lookup"><span data-stu-id="36140-125">Set this property to "Absent" to ensure that the groups do not exist.</span></span> <span data-ttu-id="36140-126">Если группы должны существовать, укажите для этого свойства значение Present (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="36140-126">Setting it to "Present" (the default value) ensures that the groups exist.</span></span>|
| <span data-ttu-id="36140-127">Члены группы</span><span class="sxs-lookup"><span data-stu-id="36140-127">Members</span></span>| <span data-ttu-id="36140-128">Используйте это свойство для замены текущего членства в группе заданными участниками.</span><span class="sxs-lookup"><span data-stu-id="36140-128">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="36140-129">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="36140-129">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="36140-130">Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="36140-130">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="36140-131">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="36140-131">Doing so will generate an error.</span></span>|
| <span data-ttu-id="36140-132">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="36140-132">MembersToInclude</span></span>| <span data-ttu-id="36140-133">Это свойство используется для добавления участников в существующее членство в группе.</span><span class="sxs-lookup"><span data-stu-id="36140-133">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="36140-134">Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="36140-134">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="36140-135">Если вы задали это свойство в конфигурации, не используйте свойство **Members**.</span><span class="sxs-lookup"><span data-stu-id="36140-135">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="36140-136">Это приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="36140-136">Doing so will generate an error.</span></span>|
| <span data-ttu-id="36140-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="36140-137">DependsOn</span></span> | <span data-ttu-id="36140-138">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="36140-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="36140-139">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".</span><span class="sxs-lookup"><span data-stu-id="36140-139">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="36140-140">Пример 1. Проверка наличия групп</span><span class="sxs-lookup"><span data-stu-id="36140-140">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="36140-141">В приведенном ниже примере показано, как обеспечить существование двух групп: myGroup и myOtherGroup.</span><span class="sxs-lookup"><span data-stu-id="36140-141">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

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
> <span data-ttu-id="36140-142">Для простоты в этом примере используются учетные данные в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="36140-142">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="36140-143">Сведения о шифровании учетных данных в MOF-файле конфигурации см. в разделе [Защита MOF-файла](secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="36140-143">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](secureMOF.md).</span></span>
