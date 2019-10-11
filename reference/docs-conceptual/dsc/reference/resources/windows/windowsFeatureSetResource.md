---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsFeatureSet
ms.openlocfilehash: 1758d248dde4fdee57bd01c157a3f9a8340d6194
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952961"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="5e6b3-103">Ресурс DSC WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="5e6b3-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="5e6b3-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="5e6b3-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="5e6b3-105">Ресурс **WindowsFeatureSet** в DSC Windows PowerShell предоставляет механизм добавления и удаления ролей и компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span> <span data-ttu-id="5e6b3-106">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс WindowsFeature](windowsfeatureResource.md) для каждого компонента, указанного в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="5e6b3-107">Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e6b3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e6b3-108">Syntax</span></span>

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="5e6b3-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="5e6b3-109">Properties</span></span>

|  <span data-ttu-id="5e6b3-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="5e6b3-110">Property</span></span>  |  <span data-ttu-id="5e6b3-111">Описание</span><span class="sxs-lookup"><span data-stu-id="5e6b3-111">Description</span></span>   |
|---|---|
|<span data-ttu-id="5e6b3-112">Name</span><span class="sxs-lookup"><span data-stu-id="5e6b3-112">Name</span></span> |<span data-ttu-id="5e6b3-113">Имена ролей или компонентов, которые необходимо добавить или удалить.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="5e6b3-114">Это свойство аналогично свойству **Name** командлета [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) и не содержит отображаемые имена ролей или компонентов.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-114">This is the same as the **Name** property of the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) cmdlet, and not the display name of the roles or features.</span></span> |
|<span data-ttu-id="5e6b3-115">Источник</span><span class="sxs-lookup"><span data-stu-id="5e6b3-115">Source</span></span> |<span data-ttu-id="5e6b3-116">Указывает расположение исходного файла для установки, если он необходим.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-116">Indicates the location of the source file to use for installation, if necessary.</span></span> |
|<span data-ttu-id="5e6b3-117">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="5e6b3-117">IncludeAllSubFeature</span></span> |<span data-ttu-id="5e6b3-118">Присвойте этому свойству значение `$true`, чтобы включить все необходимые дополнительные компоненты для компонентов, указанных в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-118">Set this property to `$true` to include all required subfeatures with of the features you specify with the **Name** property.</span></span> |
|<span data-ttu-id="5e6b3-119">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="5e6b3-119">Credential</span></span> |<span data-ttu-id="5e6b3-120">Учетные данные для добавления или удаления ролей или компонентов.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-120">The credentials to use to add or remove the roles or features.</span></span> |
|<span data-ttu-id="5e6b3-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="5e6b3-121">LogPath</span></span> |<span data-ttu-id="5e6b3-122">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="5e6b3-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="5e6b3-123">Common properties</span></span>

|<span data-ttu-id="5e6b3-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="5e6b3-124">Property</span></span> |<span data-ttu-id="5e6b3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5e6b3-125">Description</span></span> |
|---|---|
|<span data-ttu-id="5e6b3-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="5e6b3-126">DependsOn</span></span> |<span data-ttu-id="5e6b3-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="5e6b3-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="5e6b3-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="5e6b3-129">Ensure</span></span> |<span data-ttu-id="5e6b3-130">Указывает, добавляются ли роли или компоненты.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-130">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="5e6b3-131">Чтобы гарантировать, что роли или компоненты добавлены, присвойте этому свойству значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-131">To ensure that the roles or features are added, set this property to **Present**.</span></span> <span data-ttu-id="5e6b3-132">Чтобы гарантировать, что роли или компоненты удалены, присвойте этому свойству значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-132">To ensure that the roles or features are removed, set the property to **Absent**.</span></span> <span data-ttu-id="5e6b3-133">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="5e6b3-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="5e6b3-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="5e6b3-135">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="5e6b3-136">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="5e6b3-137">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="5e6b3-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="5e6b3-138">Пример</span><span class="sxs-lookup"><span data-stu-id="5e6b3-138">Example</span></span>

<span data-ttu-id="5e6b3-139">Приведенная ниже конфигурация обеспечивает установку компонентов **Веб-сервер** (IIS) и **SMTP-сервер**, а также всех их дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="5e6b3-139">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```