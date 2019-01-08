---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsPackageCab
ms.openlocfilehash: 035944e7ca5c7469250c48a19b79f2f2d5d38e9a
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047587"
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="20152-103">Ресурс DSC WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="20152-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="20152-104">Область применения. Windows PowerShell 5.1 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="20152-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="20152-105">Ресурс **WindowsPackageCab** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов CAB-файлов Windows на целевом узле или их удаления.</span><span class="sxs-lookup"><span data-stu-id="20152-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="20152-106">На целевом узле должен быть установлен модуль DISM PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20152-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="20152-107">Дополнительные сведения см. в статье [Use DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14) (Использование DISM в Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="20152-107">For information, see [Use DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span>


## <a name="syntax"></a><span data-ttu-id="20152-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20152-108">Syntax</span></span>

```
{
    Name = [string]
    Ensure = [string] { Absent | Present }
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="20152-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="20152-109">Properties</span></span>

|  <span data-ttu-id="20152-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="20152-110">Property</span></span>  |  <span data-ttu-id="20152-111">Описание</span><span class="sxs-lookup"><span data-stu-id="20152-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="20152-112">Name</span><span class="sxs-lookup"><span data-stu-id="20152-112">Name</span></span>| <span data-ttu-id="20152-113">Указывает имя пакета, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="20152-113">Indicates the name of the package for you want to ensure a specific state.</span></span>|
| <span data-ttu-id="20152-114">Ensure</span><span class="sxs-lookup"><span data-stu-id="20152-114">Ensure</span></span>| <span data-ttu-id="20152-115">Указывает, установлен ли пакет.</span><span class="sxs-lookup"><span data-stu-id="20152-115">Indicates if the package is installed.</span></span> <span data-ttu-id="20152-116">Если это свойство имеет значение Absent, пакет не устанавливается (а если он уже установлен, то удаляется).</span><span class="sxs-lookup"><span data-stu-id="20152-116">Set this property to "Absent" to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="20152-117">Если это свойство имеет значение Present (по умолчанию), пакет устанавливается.</span><span class="sxs-lookup"><span data-stu-id="20152-117">Set it to "Present" (the default value) to ensure the package is installed.</span></span>|
| <span data-ttu-id="20152-118">путь</span><span class="sxs-lookup"><span data-stu-id="20152-118">Path</span></span>| <span data-ttu-id="20152-119">Указывает путь к файлу пакета.</span><span class="sxs-lookup"><span data-stu-id="20152-119">Indicates the path where the package resides.</span></span>|
| <span data-ttu-id="20152-120">LogPath</span><span class="sxs-lookup"><span data-stu-id="20152-120">LogPath</span></span>| <span data-ttu-id="20152-121">Указывает полный путь к папке, где нужно сохранить файл журнала для установки или удаления пакета.</span><span class="sxs-lookup"><span data-stu-id="20152-121">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span>|
| <span data-ttu-id="20152-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="20152-122">DependsOn</span></span> | <span data-ttu-id="20152-123">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="20152-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="20152-124">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".</span><span class="sxs-lookup"><span data-stu-id="20152-124">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|

## <a name="example"></a><span data-ttu-id="20152-125">Пример</span><span class="sxs-lookup"><span data-stu-id="20152-125">Example</span></span>

<span data-ttu-id="20152-126">Ниже приведен пример конфигурации, которая принимает входные параметры и гарантирует, что CAB-файл, указанный в параметре `$Name`, установлен.</span><span class="sxs-lookup"><span data-stu-id="20152-126">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```