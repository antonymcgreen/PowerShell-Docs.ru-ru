---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: 7312edcaeb47427bf4736f466a9ed41bd7c31f6a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954651"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="d77f5-103">Ресурс DSC WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="d77f5-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="d77f5-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="d77f5-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="d77f5-105">Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="d77f5-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="d77f5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d77f5-106">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Source = [string[]] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="d77f5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d77f5-107">Properties</span></span>

|<span data-ttu-id="d77f5-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="d77f5-108">Property</span></span> |<span data-ttu-id="d77f5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d77f5-109">Description</span></span> |
|---|---|
|<span data-ttu-id="d77f5-110">Name</span><span class="sxs-lookup"><span data-stu-id="d77f5-110">Name</span></span> |<span data-ttu-id="d77f5-111">Указывает имя компонента, который необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="d77f5-111">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="d77f5-112">Источник</span><span class="sxs-lookup"><span data-stu-id="d77f5-112">Source</span></span> |<span data-ttu-id="d77f5-113">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="d77f5-113">Not implemented.</span></span> |
|<span data-ttu-id="d77f5-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="d77f5-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="d77f5-115">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента.</span><span class="sxs-lookup"><span data-stu-id="d77f5-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="d77f5-116">Если задано значение `$true`, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="d77f5-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="d77f5-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="d77f5-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="d77f5-118">Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение **Absent**).</span><span class="sxs-lookup"><span data-stu-id="d77f5-118">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="d77f5-119">Уровень журнала</span><span class="sxs-lookup"><span data-stu-id="d77f5-119">LogLevel</span></span> |<span data-ttu-id="d77f5-120">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="d77f5-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="d77f5-121">Допустимые значения: **ErrorsOnly**, **ErrorsAndWarning** и **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="d77f5-121">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="d77f5-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="d77f5-122">LogPath</span></span> |<span data-ttu-id="d77f5-123">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="d77f5-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="d77f5-124">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="d77f5-124">Common properties</span></span>

|<span data-ttu-id="d77f5-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="d77f5-125">Property</span></span> |<span data-ttu-id="d77f5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="d77f5-126">Description</span></span> |
|---|---|
|<span data-ttu-id="d77f5-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="d77f5-127">DependsOn</span></span> |<span data-ttu-id="d77f5-128">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="d77f5-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="d77f5-129">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="d77f5-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="d77f5-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="d77f5-130">Ensure</span></span> |<span data-ttu-id="d77f5-131">Указывает, включен ли компонент.</span><span class="sxs-lookup"><span data-stu-id="d77f5-131">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="d77f5-132">Чтобы гарантировать, что эта функция включена, присвойте этому свойству значение _Enable_.</span><span class="sxs-lookup"><span data-stu-id="d77f5-132">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="d77f5-133">Чтобы гарантировать, что эта функция отключена, присвойте этому свойству значение _Disable_.</span><span class="sxs-lookup"><span data-stu-id="d77f5-133">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="d77f5-134">По умолчанию используется значение _Enable_.</span><span class="sxs-lookup"><span data-stu-id="d77f5-134">The default value is _Enable_.</span></span> |
|<span data-ttu-id="d77f5-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="d77f5-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="d77f5-136">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="d77f5-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="d77f5-137">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d77f5-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="d77f5-138">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="d77f5-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>