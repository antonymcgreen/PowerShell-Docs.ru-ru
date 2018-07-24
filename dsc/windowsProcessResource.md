---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsProcess в DSC
ms.openlocfilehash: 3c4e6d8377c3dcbf4f1db87a603d5483b8caafb8
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093741"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="dbdc9-103">Ресурс WindowsProcess в DSC</span><span class="sxs-lookup"><span data-stu-id="dbdc9-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="dbdc9-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="dbdc9-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="dbdc9-105">Ресурс **WindowsProcess** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="dbdc9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbdc9-106">Syntax</span></span>

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ DependsOn = [string[]] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="dbdc9-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="dbdc9-107">Properties</span></span>

|  <span data-ttu-id="dbdc9-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="dbdc9-108">Property</span></span>  |  <span data-ttu-id="dbdc9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dbdc9-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="dbdc9-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="dbdc9-110">Arguments</span></span>| <span data-ttu-id="dbdc9-111">Указывает строку аргументов, которая будет передана процессу "как есть".</span><span class="sxs-lookup"><span data-stu-id="dbdc9-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="dbdc9-112">Если необходимо передать несколько аргументов, поместите их все в эту строку.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-112">If you need to pass several arguments, put them all in this string.</span></span>|
| <span data-ttu-id="dbdc9-113">путь</span><span class="sxs-lookup"><span data-stu-id="dbdc9-113">Path</span></span>| <span data-ttu-id="dbdc9-114">Путь к исполняемому файлу процесса.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-114">The path to the process executable.</span></span> <span data-ttu-id="dbdc9-115">Если это имя исполняемого файла (а не полный путь к нему), ресурс DSC будет искать переменную среды **Path** (`$env:Path`), чтобы найти исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment **Path** variable (`$env:Path`) to find the executable file.</span></span> <span data-ttu-id="dbdc9-116">Если значение этого свойства — полный путь, ресурс DSC не будет использовать переменную среды **Path** для поиска файла и вызовет ошибку в случае отсутствия пути.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-116">If the value of this property is a fully qualified path, DSC will not use the **Path** environment variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="dbdc9-117">Относительные пути не допускаются.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-117">Relative paths are not allowed.</span></span>|
| <span data-ttu-id="dbdc9-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="dbdc9-118">Credential</span></span>| <span data-ttu-id="dbdc9-119">Указывает учетные данные для запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-119">Indicates the credentials for starting the process.</span></span>|
| <span data-ttu-id="dbdc9-120">Ensure</span><span class="sxs-lookup"><span data-stu-id="dbdc9-120">Ensure</span></span>| <span data-ttu-id="dbdc9-121">Указывает, существует ли процесс.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-121">Indicates if the process exists.</span></span> <span data-ttu-id="dbdc9-122">Если процесс существует, укажите для этого свойства значение Present.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-122">Set this property to "Present" to ensure that the process exists.</span></span> <span data-ttu-id="dbdc9-123">В противном случае укажите значение Absent.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-123">Otherwise, set it to "Absent".</span></span> <span data-ttu-id="dbdc9-124">Значение по умолчанию — Present.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-124">The default is "Present".</span></span>|
| <span data-ttu-id="dbdc9-125">DependsOn</span><span class="sxs-lookup"><span data-stu-id="dbdc9-125">DependsOn</span></span> | <span data-ttu-id="dbdc9-126">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-126">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="dbdc9-127">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: 'DependsOn = "[ResourceType]ResourceName"''.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-127">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\` .</span></span>|
| <span data-ttu-id="dbdc9-128">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="dbdc9-128">StandardErrorPath</span></span>| <span data-ttu-id="dbdc9-129">Указывает путь к каталогу для записи стандартных ошибок.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-129">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="dbdc9-130">Все существующие файлы в этом каталоге будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-130">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="dbdc9-131">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="dbdc9-131">StandardInputPath</span></span>| <span data-ttu-id="dbdc9-132">Указывает расположение стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-132">Indicates the standard input location.</span></span>|
| <span data-ttu-id="dbdc9-133">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="dbdc9-133">StandardOutputPath</span></span>| <span data-ttu-id="dbdc9-134">Указывает расположение стандартного вывода.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-134">Indicates the location to write the standard output.</span></span> <span data-ttu-id="dbdc9-135">Все существующие файлы в этом каталоге будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-135">Any existing file there will be overwritten.</span></span>|
| <span data-ttu-id="dbdc9-136">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="dbdc9-136">WorkingDirectory</span></span>| <span data-ttu-id="dbdc9-137">Указывает расположение, которое будет использоваться в качестве текущего рабочего каталога для процесса.</span><span class="sxs-lookup"><span data-stu-id="dbdc9-137">Indicates the location that will be used as the current working directory for the process.</span></span>|