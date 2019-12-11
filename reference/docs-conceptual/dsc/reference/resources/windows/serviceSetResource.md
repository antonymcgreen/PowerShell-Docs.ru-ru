---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC ServiceSet
ms.openlocfilehash: 97c25f46940d69ed6c696e2692e29131e9a997b0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953031"
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="18433-103">Ресурс DSC ServiceSet</span><span class="sxs-lookup"><span data-stu-id="18433-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="18433-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="18433-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="18433-105">Ресурс **ServiceSet** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="18433-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="18433-106">Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Service](serviceResource.md) для каждой службы, указанной в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="18433-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the **Name** property.</span></span>

<span data-ttu-id="18433-107">Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="18433-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="18433-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18433-108">Syntax</span></span>

```Syntax
ServiceSet [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="18433-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="18433-109">Properties</span></span>

|<span data-ttu-id="18433-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="18433-110">Property</span></span> |<span data-ttu-id="18433-111">Описание</span><span class="sxs-lookup"><span data-stu-id="18433-111">Description</span></span> |
|---|---|
|<span data-ttu-id="18433-112">Name</span><span class="sxs-lookup"><span data-stu-id="18433-112">Name</span></span> |<span data-ttu-id="18433-113">Указывает имена служб.</span><span class="sxs-lookup"><span data-stu-id="18433-113">Indicates the service names.</span></span> <span data-ttu-id="18433-114">Обратите внимание на то, что иногда они отличаются от отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="18433-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="18433-115">Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="18433-115">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="18433-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="18433-116">StartupType</span></span> |<span data-ttu-id="18433-117">Указывает тип запуска служб.</span><span class="sxs-lookup"><span data-stu-id="18433-117">Indicates the startup type for the services.</span></span> <span data-ttu-id="18433-118">Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**.</span><span class="sxs-lookup"><span data-stu-id="18433-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="18433-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="18433-119">BuiltInAccount</span></span> |<span data-ttu-id="18433-120">Указывает учетную запись, используемую службами для входа.</span><span class="sxs-lookup"><span data-stu-id="18433-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="18433-121">Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="18433-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="18433-122">State</span><span class="sxs-lookup"><span data-stu-id="18433-122">State</span></span> |<span data-ttu-id="18433-123">Указывает состояние, в котором должны находиться службы: **Stopped** или **Running**.</span><span class="sxs-lookup"><span data-stu-id="18433-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span> |
|<span data-ttu-id="18433-124">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="18433-124">Credential</span></span> |<span data-ttu-id="18433-125">Указывает учетные данные для учетной записи, от имени которой будет запускаться ресурс службы.</span><span class="sxs-lookup"><span data-stu-id="18433-125">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="18433-126">Это свойство нельзя использовать одновременно со свойством **BuiltinAccount**.</span><span class="sxs-lookup"><span data-stu-id="18433-126">This property and the **BuiltinAccount** property cannot be used together.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="18433-127">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="18433-127">Common properties</span></span>

|<span data-ttu-id="18433-128">Свойство</span><span class="sxs-lookup"><span data-stu-id="18433-128">Property</span></span> |<span data-ttu-id="18433-129">Описание</span><span class="sxs-lookup"><span data-stu-id="18433-129">Description</span></span> |
|---|---|
|<span data-ttu-id="18433-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="18433-130">DependsOn</span></span> |<span data-ttu-id="18433-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="18433-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="18433-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="18433-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="18433-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="18433-133">Ensure</span></span> |<span data-ttu-id="18433-134">Указывает, имеются ли службы в системе.</span><span class="sxs-lookup"><span data-stu-id="18433-134">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="18433-135">Если службы не должны существовать, присвойте этому свойству значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="18433-135">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="18433-136">Если целевые службы должны существовать, укажите значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="18433-136">Setting it to **Present** ensures that target services exist.</span></span> <span data-ttu-id="18433-137">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="18433-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="18433-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="18433-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="18433-139">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="18433-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="18433-140">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="18433-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="18433-141">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="18433-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="18433-142">Пример</span><span class="sxs-lookup"><span data-stu-id="18433-142">Example</span></span>

<span data-ttu-id="18433-143">Приведенная ниже конфигурация запускает службы "Windows Audio" и "Службы удаленных рабочих столов".</span><span class="sxs-lookup"><span data-stu-id="18433-143">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```