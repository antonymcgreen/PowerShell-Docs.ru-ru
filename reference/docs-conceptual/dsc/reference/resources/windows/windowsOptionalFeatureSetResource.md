---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс DSC WindowsOptionalFeatureSet
description: Ресурс DSC WindowsOptionalFeatureSet
ms.openlocfilehash: f72cc27bfc8847d2c87cfb289f3e2c729a21d1f4
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143047"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="86752-103">Ресурс DSC WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="86752-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="86752-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="86752-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="86752-105">Ресурс **WindowsOptionalFeatureSet** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="86752-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="86752-106">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс WindowsOptionalFeature](windowsOptionalFeatureResource.md) для каждого компонента, указанного в свойстве **Name** .</span><span class="sxs-lookup"><span data-stu-id="86752-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="86752-107">Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких дополнительных компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="86752-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="86752-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86752-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="86752-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="86752-109">Properties</span></span>

|<span data-ttu-id="86752-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="86752-110">Property</span></span> |<span data-ttu-id="86752-111">Описание</span><span class="sxs-lookup"><span data-stu-id="86752-111">Description</span></span> |
|---|---|
|<span data-ttu-id="86752-112">Имя</span><span class="sxs-lookup"><span data-stu-id="86752-112">Name</span></span> |<span data-ttu-id="86752-113">Указывает имена компонентов, которые необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="86752-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="86752-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="86752-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="86752-115">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонентов.</span><span class="sxs-lookup"><span data-stu-id="86752-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="86752-116">Если задано значение `$true`, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="86752-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="86752-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="86752-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="86752-118">Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентами, когда свойству **Ensure** присваивается значение **Absent** .</span><span class="sxs-lookup"><span data-stu-id="86752-118">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent** .</span></span> |
|<span data-ttu-id="86752-119">LogLevel</span><span class="sxs-lookup"><span data-stu-id="86752-119">LogLevel</span></span> |<span data-ttu-id="86752-120">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="86752-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="86752-121">Допустимые значения: **ErrorsOnly** , **ErrorsAndWarning** и **ErrorsAndWarningAndInformation** .</span><span class="sxs-lookup"><span data-stu-id="86752-121">The accepted values are: **ErrorsOnly** , **ErrorsAndWarning** , and **ErrorsAndWarningAndInformation** .</span></span> |
|<span data-ttu-id="86752-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="86752-122">LogPath</span></span> |<span data-ttu-id="86752-123">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="86752-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="86752-124">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="86752-124">Common properties</span></span>

|<span data-ttu-id="86752-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="86752-125">Property</span></span> |<span data-ttu-id="86752-126">Описание</span><span class="sxs-lookup"><span data-stu-id="86752-126">Description</span></span> |
|---|---|
|<span data-ttu-id="86752-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="86752-127">DependsOn</span></span> |<span data-ttu-id="86752-128">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="86752-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="86752-129">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="86752-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="86752-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="86752-130">Ensure</span></span> |<span data-ttu-id="86752-131">Указывает, включены ли компоненты.</span><span class="sxs-lookup"><span data-stu-id="86752-131">Specifies whether the features are enabled.</span></span> <span data-ttu-id="86752-132">Чтобы гарантировать, что компоненты включены, присвойте этому свойству значение **Enable** .</span><span class="sxs-lookup"><span data-stu-id="86752-132">To ensure that the features are enabled, set this property to **Enable** .</span></span> <span data-ttu-id="86752-133">Чтобы гарантировать, что компоненты отключены, присвойте этому свойству значение **Disable** .</span><span class="sxs-lookup"><span data-stu-id="86752-133">To ensure that the features are disabled, set the property to **Disable** .</span></span> <span data-ttu-id="86752-134">По умолчанию используется значение **Enable** .</span><span class="sxs-lookup"><span data-stu-id="86752-134">The default value is **Enable** .</span></span> |
|<span data-ttu-id="86752-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="86752-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="86752-136">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="86752-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="86752-137">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="86752-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="86752-138">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="86752-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
