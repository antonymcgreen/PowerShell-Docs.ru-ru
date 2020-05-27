---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Environment в DSC
ms.openlocfilehash: 5670646b6e94019f436d85296deff4de8da920f6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560361"
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="e6ea7-103">Ресурс Environment в DSC</span><span class="sxs-lookup"><span data-stu-id="e6ea7-103">DSC Environment Resource</span></span>

> <span data-ttu-id="e6ea7-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e6ea7-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="e6ea7-105">Ресурс **Environment** в DSC Windows PowerShell предоставляет механизм управления системными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-105">The **Environment** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6ea7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6ea7-106">Syntax</span></span>

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e6ea7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e6ea7-107">Properties</span></span>

|<span data-ttu-id="e6ea7-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="e6ea7-108">Property</span></span> |<span data-ttu-id="e6ea7-109">Description</span><span class="sxs-lookup"><span data-stu-id="e6ea7-109">Description</span></span> |
|---|---|
|<span data-ttu-id="e6ea7-110">Имя</span><span class="sxs-lookup"><span data-stu-id="e6ea7-110">Name</span></span> |<span data-ttu-id="e6ea7-111">Указывает имя переменной среды, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e6ea7-112">путь</span><span class="sxs-lookup"><span data-stu-id="e6ea7-112">Path</span></span> |<span data-ttu-id="e6ea7-113">Определяет настраиваемую переменную среды.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-113">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="e6ea7-114">Для переменной `$true`Path**присвойте этому свойству значение**; для остальных переменных используйте значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-114">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="e6ea7-115">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-115">The default is `$false`.</span></span> <span data-ttu-id="e6ea7-116">Если настраивается переменная **Path**, к существующему значению прикрепляется значение свойства **Value**.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-116">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |
|<span data-ttu-id="e6ea7-117">Значение</span><span class="sxs-lookup"><span data-stu-id="e6ea7-117">Value</span></span> |<span data-ttu-id="e6ea7-118">Значение, которое нужно присвоить переменной среды.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-118">The value to assign to the environment variable.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e6ea7-119">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="e6ea7-119">Common properties</span></span>

|<span data-ttu-id="e6ea7-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="e6ea7-120">Property</span></span> |<span data-ttu-id="e6ea7-121">Description</span><span class="sxs-lookup"><span data-stu-id="e6ea7-121">Description</span></span> |
|---|---|
|<span data-ttu-id="e6ea7-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e6ea7-122">DependsOn</span></span> |<span data-ttu-id="e6ea7-123">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e6ea7-124">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e6ea7-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="e6ea7-125">Ensure</span></span> |<span data-ttu-id="e6ea7-126">Указывает, существует ли переменная.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-126">Indicates if a variable exists.</span></span> <span data-ttu-id="e6ea7-127">Присвойте этому свойству значение **Present**, чтобы создать переменную среды, если она отсутствует, или убедиться, что ее значение соответствует значению свойства **Value**, если переменная уже существует.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-127">Set this property to **Present** to create the environment variable if it does not exist or to ensure that its value matches what is provided through the **Value** property if the variable already exists.</span></span> <span data-ttu-id="e6ea7-128">Задайте значение **Absent**, чтобы удалить переменную, если она существует.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-128">Set it to **Absent** to delete the variable if it exists.</span></span> |
|<span data-ttu-id="e6ea7-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e6ea7-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="e6ea7-130">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-130">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e6ea7-131">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-131">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e6ea7-132">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="e6ea7-132">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e6ea7-133">Пример</span><span class="sxs-lookup"><span data-stu-id="e6ea7-133">Example</span></span>

<span data-ttu-id="e6ea7-134">В следующем примере проверяется, существует ли переменная TestEnvironmentVariable и имеет ли она значение _TestValue_.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-134">The following example ensures that TestEnvironmentVariable is present and it has the value _TestValue_.</span></span> <span data-ttu-id="e6ea7-135">Если переменная не существует, она создается.</span><span class="sxs-lookup"><span data-stu-id="e6ea7-135">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
