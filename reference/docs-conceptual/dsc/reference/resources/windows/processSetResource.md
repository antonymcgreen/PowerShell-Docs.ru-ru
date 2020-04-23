---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC ProcessSet
ms.openlocfilehash: 72925d3a9516f5c0040427773a3b1d66034667bb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953131"
---
# <a name="dsc-processset-resource"></a><span data-ttu-id="05529-103">Ресурс DSC ProcessSet</span><span class="sxs-lookup"><span data-stu-id="05529-103">DSC ProcessSet Resource</span></span>

> <span data-ttu-id="05529-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="05529-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="05529-105">Ресурс **ProcessSet** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="05529-105">The **ProcessSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="05529-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05529-106">Syntax</span></span>

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="05529-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="05529-107">Properties</span></span>

|<span data-ttu-id="05529-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="05529-108">Property</span></span> |<span data-ttu-id="05529-109">Описание</span><span class="sxs-lookup"><span data-stu-id="05529-109">Description</span></span> |
|---|---|
|<span data-ttu-id="05529-110">путь</span><span class="sxs-lookup"><span data-stu-id="05529-110">Path</span></span> |<span data-ttu-id="05529-111">Путь к исполняемому файлу процесса.</span><span class="sxs-lookup"><span data-stu-id="05529-111">The path to the process executable.</span></span> <span data-ttu-id="05529-112">Если это имена исполняемых файлов (а не полные пути к ним), ресурс DSC будет искать переменную среды `$env:Path`, чтобы найти файлы.</span><span class="sxs-lookup"><span data-stu-id="05529-112">If these are the names of the executable files (not fully qualified paths), the DSC resource will search the environment `$env:Path` variable to find the files.</span></span> <span data-ttu-id="05529-113">Если значения этого свойства — полные пути, ресурс DSC не будет использовать переменную среды `$env:Path` для поиска файлов и вызовет ошибку в случае отсутствия путей.</span><span class="sxs-lookup"><span data-stu-id="05529-113">If the values of this property are fully qualified paths, DSC will not use the `$env:Path` environment variable to find the files, and will throw an error if any of the paths do not exist.</span></span> <span data-ttu-id="05529-114">Относительные пути не допускаются.</span><span class="sxs-lookup"><span data-stu-id="05529-114">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="05529-115">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="05529-115">Credential</span></span> |<span data-ttu-id="05529-116">Указывает учетные данные для запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="05529-116">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="05529-117">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="05529-117">StandardErrorPath</span></span> |<span data-ttu-id="05529-118">Путь, по которому процессы записывают стандартную ошибку.</span><span class="sxs-lookup"><span data-stu-id="05529-118">The path to which the processes write standard error.</span></span> <span data-ttu-id="05529-119">Все существующие файлы в этом каталоге будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="05529-119">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="05529-120">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="05529-120">StandardInputPath</span></span> |<span data-ttu-id="05529-121">Поток, из которого процесс получает стандартные входные данные.</span><span class="sxs-lookup"><span data-stu-id="05529-121">The stream from which the process receives standard input.</span></span> |
|<span data-ttu-id="05529-122">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="05529-122">StandardOutputPath</span></span> |<span data-ttu-id="05529-123">Путь, по которому процессы записывают стандартные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="05529-123">The path of the file to which the processes write standard output.</span></span> <span data-ttu-id="05529-124">Все существующие файлы в этом каталоге будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="05529-124">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="05529-125">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="05529-125">WorkingDirectory</span></span> |<span data-ttu-id="05529-126">Расположение, которое используется в качестве текущего рабочего каталога для процессов.</span><span class="sxs-lookup"><span data-stu-id="05529-126">The location used as the current working directory for the processes.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="05529-127">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="05529-127">Common properties</span></span>

|<span data-ttu-id="05529-128">Свойство</span><span class="sxs-lookup"><span data-stu-id="05529-128">Property</span></span> |<span data-ttu-id="05529-129">Описание</span><span class="sxs-lookup"><span data-stu-id="05529-129">Description</span></span> |
|---|---|
|<span data-ttu-id="05529-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="05529-130">DependsOn</span></span> |<span data-ttu-id="05529-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="05529-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="05529-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="05529-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="05529-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="05529-133">Ensure</span></span> |<span data-ttu-id="05529-134">Указывает, существуют ли процессы.</span><span class="sxs-lookup"><span data-stu-id="05529-134">Specifies whether the processes exists.</span></span> <span data-ttu-id="05529-135">Чтобы гарантировать, что процесс существует, укажите для этого свойства значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="05529-135">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="05529-136">В противном случае укажите значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="05529-136">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="05529-137">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="05529-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="05529-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="05529-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="05529-139">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="05529-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="05529-140">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="05529-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="05529-141">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="05529-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>