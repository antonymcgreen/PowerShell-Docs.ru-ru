---
ms.date: 08/28/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093256"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="c04b9-103">Ресурс DSC WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="c04b9-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="c04b9-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="c04b9-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="c04b9-105">Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="c04b9-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="c04b9-106">**WindowsOptionalFeature** работает только на клиентских компьютерах Windows, таких как Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c04b9-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

## <a name="syntax"></a><span data-ttu-id="c04b9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c04b9-107">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="c04b9-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="c04b9-108">Properties</span></span>

|<span data-ttu-id="c04b9-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="c04b9-109">Property</span></span> |<span data-ttu-id="c04b9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c04b9-110">Description</span></span> |
|---|---|
|<span data-ttu-id="c04b9-111">Имя</span><span class="sxs-lookup"><span data-stu-id="c04b9-111">Name</span></span> |<span data-ttu-id="c04b9-112">Указывает имя компонента, который необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="c04b9-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="c04b9-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="c04b9-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="c04b9-114">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента.</span><span class="sxs-lookup"><span data-stu-id="c04b9-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="c04b9-115">Если задано значение `$true`, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="c04b9-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="c04b9-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="c04b9-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="c04b9-117">Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение **Absent**).</span><span class="sxs-lookup"><span data-stu-id="c04b9-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="c04b9-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="c04b9-118">LogLevel</span></span> |<span data-ttu-id="c04b9-119">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="c04b9-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="c04b9-120">Допустимые значения: **ErrorsOnly**, **ErrorsAndWarning** и **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="c04b9-120">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="c04b9-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="c04b9-121">LogPath</span></span> |<span data-ttu-id="c04b9-122">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="c04b9-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="c04b9-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="c04b9-123">Common properties</span></span>

|<span data-ttu-id="c04b9-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="c04b9-124">Property</span></span> |<span data-ttu-id="c04b9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c04b9-125">Description</span></span> |
|---|---|
|<span data-ttu-id="c04b9-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="c04b9-126">DependsOn</span></span> |<span data-ttu-id="c04b9-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="c04b9-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="c04b9-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="c04b9-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="c04b9-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="c04b9-129">Ensure</span></span> |<span data-ttu-id="c04b9-130">Указывает, включена ли функция.</span><span class="sxs-lookup"><span data-stu-id="c04b9-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="c04b9-131">Чтобы гарантировать, что эта функция включена, присвойте этому свойству значение _Enable_.</span><span class="sxs-lookup"><span data-stu-id="c04b9-131">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="c04b9-132">Чтобы гарантировать, что эта функция отключена, присвойте этому свойству значение _Disable_.</span><span class="sxs-lookup"><span data-stu-id="c04b9-132">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="c04b9-133">По умолчанию используется значение _Enable_.</span><span class="sxs-lookup"><span data-stu-id="c04b9-133">The default value is _Enable_.</span></span> |
|<span data-ttu-id="c04b9-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c04b9-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="c04b9-135">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="c04b9-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="c04b9-136">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c04b9-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="c04b9-137">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="c04b9-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
