---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Environment в DSC
ms.openlocfilehash: d8519a66d457767dcbc0e08b01a69a9264997479
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464423"
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="e9471-103">Ресурс Environment в DSC</span><span class="sxs-lookup"><span data-stu-id="e9471-103">DSC Environment Resource</span></span>

> <span data-ttu-id="e9471-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e9471-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="e9471-105">Ресурс **Environment** в DSC Windows PowerShell предоставляет механизм управления системными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="e9471-105">The **Environment** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9471-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9471-106">Syntax</span></span>

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Target = [string] { Process | Machine } ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e9471-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e9471-107">Properties</span></span>

|<span data-ttu-id="e9471-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="e9471-108">Property</span></span> |<span data-ttu-id="e9471-109">Description</span><span class="sxs-lookup"><span data-stu-id="e9471-109">Description</span></span> |
|---|---|
|<span data-ttu-id="e9471-110">Имя</span><span class="sxs-lookup"><span data-stu-id="e9471-110">Name</span></span> |<span data-ttu-id="e9471-111">Указывает имя переменной среды, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="e9471-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e9471-112">путь</span><span class="sxs-lookup"><span data-stu-id="e9471-112">Path</span></span> |<span data-ttu-id="e9471-113">Определяет настраиваемую переменную среды.</span><span class="sxs-lookup"><span data-stu-id="e9471-113">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="e9471-114">Для переменной **Path** присвойте этому свойству значение `$true`; для остальных переменных используйте значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="e9471-114">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="e9471-115">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="e9471-115">The default is `$false`.</span></span> <span data-ttu-id="e9471-116">Если настраивается переменная **Path**, к существующему значению прикрепляется значение свойства **Value**.</span><span class="sxs-lookup"><span data-stu-id="e9471-116">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |
|<span data-ttu-id="e9471-117">целевого объекта</span><span class="sxs-lookup"><span data-stu-id="e9471-117">Target</span></span>| <span data-ttu-id="e9471-118">Указывает, откуда извлечь переменную: компьютер или процесс.</span><span class="sxs-lookup"><span data-stu-id="e9471-118">Indicates where to retrieve the variable: The machine or the process.</span></span> <span data-ttu-id="e9471-119">Если указаны оба значения, возвращается только значение с компьютера.</span><span class="sxs-lookup"><span data-stu-id="e9471-119">If both are indicated then only the value from the machine is returned.</span></span> <span data-ttu-id="e9471-120">По умолчанию выбраны оба источника, так как это значение по умолчанию для остальной части ресурса.</span><span class="sxs-lookup"><span data-stu-id="e9471-120">The default is both since that is the default for the rest of the resource.</span></span> |
|<span data-ttu-id="e9471-121">Значение</span><span class="sxs-lookup"><span data-stu-id="e9471-121">Value</span></span> |<span data-ttu-id="e9471-122">Значение, которое нужно присвоить переменной среды.</span><span class="sxs-lookup"><span data-stu-id="e9471-122">The value to assign to the environment variable.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e9471-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="e9471-123">Common properties</span></span>

|<span data-ttu-id="e9471-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="e9471-124">Property</span></span> |<span data-ttu-id="e9471-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e9471-125">Description</span></span> |
|---|---|
|<span data-ttu-id="e9471-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e9471-126">DependsOn</span></span> |<span data-ttu-id="e9471-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="e9471-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e9471-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e9471-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e9471-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="e9471-129">Ensure</span></span> |<span data-ttu-id="e9471-130">Указывает, существует ли переменная.</span><span class="sxs-lookup"><span data-stu-id="e9471-130">Indicates if a variable exists.</span></span> <span data-ttu-id="e9471-131">Присвойте этому свойству значение **Present**, чтобы создать переменную среды, если она отсутствует, или убедиться, что ее значение соответствует значению свойства **Value**, если переменная уже существует.</span><span class="sxs-lookup"><span data-stu-id="e9471-131">Set this property to **Present** to create the environment variable if it does not exist or to ensure that its value matches what is provided through the **Value** property if the variable already exists.</span></span> <span data-ttu-id="e9471-132">Задайте значение **Absent**, чтобы удалить переменную, если она существует.</span><span class="sxs-lookup"><span data-stu-id="e9471-132">Set it to **Absent** to delete the variable if it exists.</span></span> |
|<span data-ttu-id="e9471-133">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e9471-133">PsDscRunAsCredential</span></span> |<span data-ttu-id="e9471-134">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="e9471-134">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e9471-135">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e9471-135">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e9471-136">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="e9471-136">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e9471-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e9471-137">Example</span></span>

<span data-ttu-id="e9471-138">В следующем примере проверяется, существует ли переменная TestEnvironmentVariable и имеет ли она значение _TestValue_.</span><span class="sxs-lookup"><span data-stu-id="e9471-138">The following example ensures that TestEnvironmentVariable is present and it has the value _TestValue_.</span></span> <span data-ttu-id="e9471-139">Если переменная не существует, она создается.</span><span class="sxs-lookup"><span data-stu-id="e9471-139">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
