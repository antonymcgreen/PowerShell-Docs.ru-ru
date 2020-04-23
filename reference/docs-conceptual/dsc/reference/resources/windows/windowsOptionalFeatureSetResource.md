---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeatureSet
ms.openlocfilehash: f378006a6c362ee9890d70dd76fb552dd262a544
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952871"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="abe3f-103">Ресурс DSC WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="abe3f-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="abe3f-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="abe3f-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="abe3f-105">Ресурс **WindowsOptionalFeatureSet** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="abe3f-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="abe3f-106">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс WindowsOptionalFeature](windowsOptionalFeatureResource.md) для каждого компонента, указанного в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="abe3f-107">Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких дополнительных компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="abe3f-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="abe3f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abe3f-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="abe3f-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="abe3f-109">Properties</span></span>

|<span data-ttu-id="abe3f-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="abe3f-110">Property</span></span> |<span data-ttu-id="abe3f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="abe3f-111">Description</span></span> |
|---|---|
|<span data-ttu-id="abe3f-112">Имя</span><span class="sxs-lookup"><span data-stu-id="abe3f-112">Name</span></span> |<span data-ttu-id="abe3f-113">Указывает имена компонентов, которые необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="abe3f-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="abe3f-114">Источник</span><span class="sxs-lookup"><span data-stu-id="abe3f-114">Source</span></span> |<span data-ttu-id="abe3f-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="abe3f-115">Not implemented.</span></span> |
|<span data-ttu-id="abe3f-116">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="abe3f-116">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="abe3f-117">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонентов.</span><span class="sxs-lookup"><span data-stu-id="abe3f-117">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="abe3f-118">Если задано значение `$true`, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="abe3f-118">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="abe3f-119">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="abe3f-119">RemoveFilesOnDisable</span></span> |<span data-ttu-id="abe3f-120">Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентами, когда свойству **Ensure** присваивается значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-120">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="abe3f-121">LogLevel</span><span class="sxs-lookup"><span data-stu-id="abe3f-121">LogLevel</span></span> |<span data-ttu-id="abe3f-122">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="abe3f-122">The maximum output level shown in the logs.</span></span> <span data-ttu-id="abe3f-123">Допустимые значения: **ErrorsOnly**, **ErrorsAndWarning** и **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-123">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="abe3f-124">LogPath</span><span class="sxs-lookup"><span data-stu-id="abe3f-124">LogPath</span></span> |<span data-ttu-id="abe3f-125">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="abe3f-125">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="abe3f-126">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="abe3f-126">Common properties</span></span>

|<span data-ttu-id="abe3f-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="abe3f-127">Property</span></span> |<span data-ttu-id="abe3f-128">Описание</span><span class="sxs-lookup"><span data-stu-id="abe3f-128">Description</span></span> |
|---|---|
|<span data-ttu-id="abe3f-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="abe3f-129">DependsOn</span></span> |<span data-ttu-id="abe3f-130">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="abe3f-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="abe3f-131">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="abe3f-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="abe3f-132">Ensure</span><span class="sxs-lookup"><span data-stu-id="abe3f-132">Ensure</span></span> |<span data-ttu-id="abe3f-133">Указывает, включены ли компоненты.</span><span class="sxs-lookup"><span data-stu-id="abe3f-133">Specifies whether the features are enabled.</span></span> <span data-ttu-id="abe3f-134">Чтобы гарантировать, что компоненты включены, присвойте этому свойству значение **Enable**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-134">To ensure that the features are enabled, set this property to **Enable**.</span></span> <span data-ttu-id="abe3f-135">Чтобы гарантировать, что компоненты отключены, присвойте этому свойству значение **Disable**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-135">To ensure that the features are disabled, set the property to **Disable**.</span></span> <span data-ttu-id="abe3f-136">По умолчанию используется значение **Enable**.</span><span class="sxs-lookup"><span data-stu-id="abe3f-136">The default value is **Enable**.</span></span> |
|<span data-ttu-id="abe3f-137">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="abe3f-137">PsDscRunAsCredential</span></span> |<span data-ttu-id="abe3f-138">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="abe3f-138">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="abe3f-139">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="abe3f-139">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="abe3f-140">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="abe3f-140">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>