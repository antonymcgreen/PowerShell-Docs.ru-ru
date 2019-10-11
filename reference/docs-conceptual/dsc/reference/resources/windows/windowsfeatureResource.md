---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsFeature в DSC
ms.openlocfilehash: d3384b1f45324df6b6b209f25b64d9d77615ad7f
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954631"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="c98b0-103">Ресурс WindowsFeature в DSC</span><span class="sxs-lookup"><span data-stu-id="c98b0-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="c98b0-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="c98b0-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="c98b0-105">Ресурс **WindowsFeature** в DSC Windows PowerShell предоставляет механизм добавления и удаления ролей и компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="c98b0-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="c98b0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c98b0-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ Source = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="c98b0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c98b0-107">Properties</span></span>

|<span data-ttu-id="c98b0-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="c98b0-108">Property</span></span> |<span data-ttu-id="c98b0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c98b0-109">Description</span></span> |
|---|---|
|<span data-ttu-id="c98b0-110">Name</span><span class="sxs-lookup"><span data-stu-id="c98b0-110">Name</span></span> |<span data-ttu-id="c98b0-111">Указывает имя роли или компонента, которые необходимо добавить или удалить.</span><span class="sxs-lookup"><span data-stu-id="c98b0-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="c98b0-112">Это свойство аналогично свойству **Name** командлета [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) и не является отображаемым именем роли или компонента.</span><span class="sxs-lookup"><span data-stu-id="c98b0-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="c98b0-113">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="c98b0-113">Credential</span></span> |<span data-ttu-id="c98b0-114">Указывает учетные данные для добавления или удаления роли или компонента.</span><span class="sxs-lookup"><span data-stu-id="c98b0-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="c98b0-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="c98b0-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="c98b0-116">Присвойте этому свойству значение `$true` для синхронизации состояния всех необходимых дополнительных компонентов с состоянием компонента, указанного в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="c98b0-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="c98b0-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="c98b0-117">LogPath</span></span> |<span data-ttu-id="c98b0-118">Указывает путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="c98b0-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |
|<span data-ttu-id="c98b0-119">Источник</span><span class="sxs-lookup"><span data-stu-id="c98b0-119">Source</span></span> |<span data-ttu-id="c98b0-120">Указывает расположение исходного файла для установки, если он необходим.</span><span class="sxs-lookup"><span data-stu-id="c98b0-120">Indicates the location of the source file to use for installation, if necessary.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="c98b0-121">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="c98b0-121">Common properties</span></span>

|<span data-ttu-id="c98b0-122">Свойство</span><span class="sxs-lookup"><span data-stu-id="c98b0-122">Property</span></span> |<span data-ttu-id="c98b0-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c98b0-123">Description</span></span> |
|---|---|
|<span data-ttu-id="c98b0-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="c98b0-124">DependsOn</span></span> |<span data-ttu-id="c98b0-125">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="c98b0-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="c98b0-126">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="c98b0-126">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="c98b0-127">Ensure</span><span class="sxs-lookup"><span data-stu-id="c98b0-127">Ensure</span></span> |<span data-ttu-id="c98b0-128">Указывает, добавляется или удаляется роль или компонент.</span><span class="sxs-lookup"><span data-stu-id="c98b0-128">Indicates if the role or feature is added.</span></span> <span data-ttu-id="c98b0-129">Чтобы гарантировать, что роль или компонент добавлены, присвойте этому свойству значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="c98b0-129">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="c98b0-130">Чтобы гарантировать, что роль или компонент удалены, присвойте этому свойству значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="c98b0-130">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="c98b0-131">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="c98b0-131">The default value is **Present**.</span></span> |
|<span data-ttu-id="c98b0-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c98b0-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="c98b0-133">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="c98b0-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="c98b0-134">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c98b0-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="c98b0-135">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="c98b0-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="c98b0-136">Пример</span><span class="sxs-lookup"><span data-stu-id="c98b0-136">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```