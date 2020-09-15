---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsPackageCab
ms.openlocfilehash: 7205a454d100bb369fd6cf0c5ac419585c8bbe86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464151"
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="b00b1-103">Ресурс DSC WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="b00b1-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="b00b1-104">Область применения: Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="b00b1-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="b00b1-105">Ресурс **WindowsPackageCab** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов CAB-файлов Windows на целевом узле или их удаления.</span><span class="sxs-lookup"><span data-stu-id="b00b1-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="b00b1-106">На целевом узле должен быть установлен модуль DISM PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b00b1-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="b00b1-107">Дополнительные сведения см. в статье [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14) (Использование DISM в Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b00b1-107">For information, see [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span>

## <a name="syntax"></a><span data-ttu-id="b00b1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b00b1-108">Syntax</span></span>

```Syntax
{
    Name = [string]
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    Ensure = [string] { Absent | Present }
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="b00b1-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="b00b1-109">Properties</span></span>

|<span data-ttu-id="b00b1-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="b00b1-110">Property</span></span> |<span data-ttu-id="b00b1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b00b1-111">Description</span></span> |
|---|---|
|<span data-ttu-id="b00b1-112">Имя</span><span class="sxs-lookup"><span data-stu-id="b00b1-112">Name</span></span> |<span data-ttu-id="b00b1-113">Указывает имя пакета, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="b00b1-113">Indicates the name of the package for you want to ensure a specific state.</span></span> |
|<span data-ttu-id="b00b1-114">SourcePath</span><span class="sxs-lookup"><span data-stu-id="b00b1-114">SourcePath</span></span> |<span data-ttu-id="b00b1-115">Указывает путь к файлу пакета.</span><span class="sxs-lookup"><span data-stu-id="b00b1-115">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="b00b1-116">LogPath</span><span class="sxs-lookup"><span data-stu-id="b00b1-116">LogPath</span></span> |<span data-ttu-id="b00b1-117">Указывает полный путь к папке, где нужно сохранить файл журнала для установки или удаления пакета.</span><span class="sxs-lookup"><span data-stu-id="b00b1-117">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="b00b1-118">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="b00b1-118">Common properties</span></span>

|<span data-ttu-id="b00b1-119">Свойство</span><span class="sxs-lookup"><span data-stu-id="b00b1-119">Property</span></span> |<span data-ttu-id="b00b1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b00b1-120">Description</span></span> |
|---|---|
|<span data-ttu-id="b00b1-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="b00b1-121">DependsOn</span></span> |<span data-ttu-id="b00b1-122">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="b00b1-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="b00b1-123">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="b00b1-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="b00b1-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="b00b1-124">Ensure</span></span> |<span data-ttu-id="b00b1-125">Указывает, установлен ли пакет.</span><span class="sxs-lookup"><span data-stu-id="b00b1-125">Indicates if the package is installed.</span></span> <span data-ttu-id="b00b1-126">Если это свойство имеет значение **Absent**, пакет не устанавливается (а если он уже установлен, то удаляется).</span><span class="sxs-lookup"><span data-stu-id="b00b1-126">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="b00b1-127">Если это свойство имеет значение **Present**, пакет устанавливается.</span><span class="sxs-lookup"><span data-stu-id="b00b1-127">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="b00b1-128">Свойство **Ensure** является обязательным для ресурса **WindowsPackageCab**.</span><span class="sxs-lookup"><span data-stu-id="b00b1-128">**Ensure** is a required property on the **WindowsPackageCab** resource.</span></span> |
|<span data-ttu-id="b00b1-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b00b1-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="b00b1-130">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="b00b1-130">Sets the credential for running the entire resource as.</span></span> |

## <a name="example"></a><span data-ttu-id="b00b1-131">Пример</span><span class="sxs-lookup"><span data-stu-id="b00b1-131">Example</span></span>

<span data-ttu-id="b00b1-132">Ниже приведен пример конфигурации, которая принимает входные параметры и гарантирует, что CAB-файл, указанный в параметре `$Name`, установлен.</span><span class="sxs-lookup"><span data-stu-id="b00b1-132">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

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
