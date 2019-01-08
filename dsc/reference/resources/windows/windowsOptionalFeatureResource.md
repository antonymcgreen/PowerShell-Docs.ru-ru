---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: 390caefd2ad190afc651b22ed1beb5cf1d604527
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047668"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="263b6-103">Ресурс DSC WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="263b6-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="263b6-104">Область применения. Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="263b6-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="263b6-105">Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="263b6-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="263b6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="263b6-106">Syntax</span></span>

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Source = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a><span data-ttu-id="263b6-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="263b6-107">Properties</span></span>

|  <span data-ttu-id="263b6-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="263b6-108">Property</span></span>  |  <span data-ttu-id="263b6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="263b6-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="263b6-110">Name</span><span class="sxs-lookup"><span data-stu-id="263b6-110">Name</span></span>| <span data-ttu-id="263b6-111">Указывает имя компонента, который необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="263b6-111">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span>|
| <span data-ttu-id="263b6-112">Ensure</span><span class="sxs-lookup"><span data-stu-id="263b6-112">Ensure</span></span>| <span data-ttu-id="263b6-113">Указывает, включен ли компонент.</span><span class="sxs-lookup"><span data-stu-id="263b6-113">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="263b6-114">Чтобы включить компонент, установите для этого свойства значение "Включить", чтобы отключить — значение "Отключить".</span><span class="sxs-lookup"><span data-stu-id="263b6-114">To ensure that the feature is enabled, set this property to "Enable" To ensure that the feature is disabled, set the property to "Disable".</span></span>|
| <span data-ttu-id="263b6-115">Источник</span><span class="sxs-lookup"><span data-stu-id="263b6-115">Source</span></span>| <span data-ttu-id="263b6-116">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="263b6-116">Not implemented.</span></span>|
| <span data-ttu-id="263b6-117">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="263b6-117">NoWindowsUpdateCheck</span></span>| <span data-ttu-id="263b6-118">Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента.</span><span class="sxs-lookup"><span data-stu-id="263b6-118">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="263b6-119">Если задано значение $true, система DISM не обращается к Центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="263b6-119">If $true, DISM does not contact WU.</span></span>|
| <span data-ttu-id="263b6-120">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="263b6-120">RemoveFilesOnDisable</span></span>| <span data-ttu-id="263b6-121">Задайте значение **$true**, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение Absent).</span><span class="sxs-lookup"><span data-stu-id="263b6-121">Set to **$true** to remove all files associated with the feature when it is disabled (that is, when **Ensure** is set to "Absent").</span></span>|
| <span data-ttu-id="263b6-122">Уровень журнала</span><span class="sxs-lookup"><span data-stu-id="263b6-122">LogLevel</span></span>| <span data-ttu-id="263b6-123">Максимальный уровень результатов, показываемый в журналах.</span><span class="sxs-lookup"><span data-stu-id="263b6-123">The maximum output level shown in the logs.</span></span> <span data-ttu-id="263b6-124">Допустимыми являются значения: «ErrorsOnly» (записываются только ошибки), «ErrorsAndWarning» (ошибки и предупреждения записываются) и «ErrorsAndWarningAndInformation» (регистрируются ошибки, предупреждения и отладочной информации).</span><span class="sxs-lookup"><span data-stu-id="263b6-124">The accepted values are: "ErrorsOnly" (only errors are logged), "ErrorsAndWarning" (errors and warnings are logged), and "ErrorsAndWarningAndInformation" (errors, warnings, and debug information are logged).</span></span>|
| <span data-ttu-id="263b6-125">LogPath</span><span class="sxs-lookup"><span data-stu-id="263b6-125">LogPath</span></span>| <span data-ttu-id="263b6-126">Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.</span><span class="sxs-lookup"><span data-stu-id="263b6-126">The path to a log file where you want the resource provider to log the operation.</span></span>|
| <span data-ttu-id="263b6-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="263b6-127">DependsOn</span></span>| <span data-ttu-id="263b6-128">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="263b6-128">Specifies that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="263b6-129">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="263b6-129">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|