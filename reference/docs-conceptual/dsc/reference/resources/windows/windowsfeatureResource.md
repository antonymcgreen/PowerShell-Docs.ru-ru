---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsFeature в DSC
ms.openlocfilehash: b15b267c6898697816b386a381e5a6d59acd492a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464117"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="a93c8-103">Ресурс WindowsFeature в DSC</span><span class="sxs-lookup"><span data-stu-id="a93c8-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="a93c8-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="a93c8-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="a93c8-105">Ресурс **WindowsFeature** в DSC Windows PowerShell предоставляет механизм добавления и удаления ролей и компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="a93c8-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="a93c8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a93c8-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="a93c8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="a93c8-107">Properties</span></span>

|<span data-ttu-id="a93c8-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="a93c8-108">Property</span></span> |<span data-ttu-id="a93c8-109">Description</span><span class="sxs-lookup"><span data-stu-id="a93c8-109">Description</span></span> |
|---|---|
|<span data-ttu-id="a93c8-110">Имя</span><span class="sxs-lookup"><span data-stu-id="a93c8-110">Name</span></span> |<span data-ttu-id="a93c8-111">Указывает имя роли или компонента, которые необходимо добавить или удалить.</span><span class="sxs-lookup"><span data-stu-id="a93c8-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="a93c8-112">Это свойство аналогично свойству **Name** командлета [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) и не является отображаемым именем роли или компонента.</span><span class="sxs-lookup"><span data-stu-id="a93c8-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="a93c8-113">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="a93c8-113">Credential</span></span> |<span data-ttu-id="a93c8-114">Указывает учетные данные для добавления или удаления роли или компонента.</span><span class="sxs-lookup"><span data-stu-id="a93c8-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="a93c8-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="a93c8-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="a93c8-116">Присвойте этому свойству значение `$true` для синхронизации состояния всех необходимых дополнительных компонентов с состоянием компонента, указанного в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="a93c8-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="a93c8-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="a93c8-117">LogPath</span></span> |<span data-ttu-id="a93c8-118">Указывает путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="a93c8-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="a93c8-119">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="a93c8-119">Common properties</span></span>

|<span data-ttu-id="a93c8-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="a93c8-120">Property</span></span> |<span data-ttu-id="a93c8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a93c8-121">Description</span></span> |
|---|---|
|<span data-ttu-id="a93c8-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a93c8-122">DependsOn</span></span> |<span data-ttu-id="a93c8-123">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="a93c8-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a93c8-124">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a93c8-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="a93c8-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="a93c8-125">Ensure</span></span> |<span data-ttu-id="a93c8-126">Указывает, добавляется или удаляется роль или компонент.</span><span class="sxs-lookup"><span data-stu-id="a93c8-126">Indicates if the role or feature is added.</span></span> <span data-ttu-id="a93c8-127">Чтобы гарантировать, что роль или компонент добавлены, присвойте этому свойству значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="a93c8-127">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="a93c8-128">Чтобы гарантировать, что роль или компонент удалены, присвойте этому свойству значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="a93c8-128">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="a93c8-129">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="a93c8-129">The default value is **Present**.</span></span> |
|<span data-ttu-id="a93c8-130">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="a93c8-130">PsDscRunAsCredential</span></span> |<span data-ttu-id="a93c8-131">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="a93c8-131">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="a93c8-132">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a93c8-132">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="a93c8-133">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="a93c8-133">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="a93c8-134">Пример</span><span class="sxs-lookup"><span data-stu-id="a93c8-134">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
