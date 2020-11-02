---
ms.date: 08/28/2020
ms.topic: reference
title: Ресурс DSC WindowsOptionalFeature
description: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: 1c7e888ea49b0d1710cc22c975cb618999238f67
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143064"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="90253-103">Ресурс DSC WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="90253-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="90253-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="90253-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="90253-105">Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="90253-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="90253-106">**WindowsOptionalFeature** работает только на клиентских компьютерах Windows, таких как Windows 10.</span><span class="sxs-lookup"><span data-stu-id="90253-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="90253-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90253-107">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="90253-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="90253-108">Properties</span></span>

|<span data-ttu-id="90253-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="90253-109">Property</span></span> |<span data-ttu-id="90253-110">Описание</span><span class="sxs-lookup"><span data-stu-id="90253-110">Description</span></span> |
|---|---|
|<span data-ttu-id="90253-111">Имя</span><span class="sxs-lookup"><span data-stu-id="90253-111">Name</span></span> |<span data-ttu-id="90253-112">Указывает имя компонента, который необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="90253-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="90253-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="90253-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="90253-114">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента.</span><span class="sxs-lookup"><span data-stu-id="90253-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="90253-115">Если задано значение `$true`, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="90253-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="90253-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="90253-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="90253-117">Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение **Absent** ).</span><span class="sxs-lookup"><span data-stu-id="90253-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent** .</span></span> |
|<span data-ttu-id="90253-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="90253-118">LogLevel</span></span> |<span data-ttu-id="90253-119">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="90253-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="90253-120">Допустимые значения: **ErrorsOnly** , **ErrorsAndWarning** и **ErrorsAndWarningAndInformation** .</span><span class="sxs-lookup"><span data-stu-id="90253-120">The accepted values are: **ErrorsOnly** , **ErrorsAndWarning** , and **ErrorsAndWarningAndInformation** .</span></span> |
|<span data-ttu-id="90253-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="90253-121">LogPath</span></span> |<span data-ttu-id="90253-122">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="90253-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="90253-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="90253-123">Common properties</span></span>

|<span data-ttu-id="90253-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="90253-124">Property</span></span> |<span data-ttu-id="90253-125">Описание</span><span class="sxs-lookup"><span data-stu-id="90253-125">Description</span></span> |
|---|---|
|<span data-ttu-id="90253-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="90253-126">DependsOn</span></span> |<span data-ttu-id="90253-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="90253-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="90253-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="90253-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="90253-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="90253-129">Ensure</span></span> |<span data-ttu-id="90253-130">Указывает, включена ли функция.</span><span class="sxs-lookup"><span data-stu-id="90253-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="90253-131">Чтобы гарантировать, что эта функция включена, присвойте этому свойству значение _Enable_ .</span><span class="sxs-lookup"><span data-stu-id="90253-131">To ensure that the feature is enabled, set this property to _Enable_ .</span></span> <span data-ttu-id="90253-132">Чтобы гарантировать, что эта функция отключена, присвойте этому свойству значение _Disable_ .</span><span class="sxs-lookup"><span data-stu-id="90253-132">To ensure that the feature is disabled, set the property to _Disable_ .</span></span> <span data-ttu-id="90253-133">По умолчанию используется значение _Enable_ .</span><span class="sxs-lookup"><span data-stu-id="90253-133">The default value is _Enable_ .</span></span> |
|<span data-ttu-id="90253-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="90253-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="90253-135">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="90253-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="90253-136">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="90253-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="90253-137">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="90253-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
