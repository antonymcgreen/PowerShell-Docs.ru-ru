---
ms.date: 01/06/2021
ms.topic: reference
title: Ресурс Service в DSC
description: Ресурс Service в DSC
ms.openlocfilehash: bb151e11475c6e67f1fcb2d73336ff2e34b749b8
ms.sourcegitcommit: afefb3636362857036648c2fe80215bc4e81f5ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "97957042"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="72db5-103">Ресурс Service в DSC</span><span class="sxs-lookup"><span data-stu-id="72db5-103">DSC Service Resource</span></span>

> <span data-ttu-id="72db5-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="72db5-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="72db5-105">Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="72db5-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="72db5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72db5-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="72db5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="72db5-107">Properties</span></span>

|<span data-ttu-id="72db5-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="72db5-108">Property</span></span> |<span data-ttu-id="72db5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="72db5-109">Description</span></span> |
|---|---|
|<span data-ttu-id="72db5-110">Имя</span><span class="sxs-lookup"><span data-stu-id="72db5-110">Name</span></span> |<span data-ttu-id="72db5-111">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="72db5-111">Indicates the service name.</span></span> <span data-ttu-id="72db5-112">Обратите внимание! Иногда оно отличается от отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="72db5-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="72db5-113">Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="72db5-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="72db5-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="72db5-114">BuiltInAccount</span></span> |<span data-ttu-id="72db5-115">Указывает учетную запись, используемую службой для входа.</span><span class="sxs-lookup"><span data-stu-id="72db5-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="72db5-116">Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="72db5-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="72db5-117">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="72db5-117">Credential</span></span> |<span data-ttu-id="72db5-118">Указывает учетные данные для учетной записи, от имени которой будет запускаться служба.</span><span class="sxs-lookup"><span data-stu-id="72db5-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="72db5-119">Это свойство нельзя использовать одновременно со свойством **BuiltinAccount**.</span><span class="sxs-lookup"><span data-stu-id="72db5-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="72db5-120">StartupType</span><span class="sxs-lookup"><span data-stu-id="72db5-120">StartupType</span></span> |<span data-ttu-id="72db5-121">Указывает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="72db5-121">Indicates the startup type for the service.</span></span> <span data-ttu-id="72db5-122">Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**.</span><span class="sxs-lookup"><span data-stu-id="72db5-122">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="72db5-123">Состояние</span><span class="sxs-lookup"><span data-stu-id="72db5-123">State</span></span> |<span data-ttu-id="72db5-124">Указывает состояние, в котором должна находиться служба.</span><span class="sxs-lookup"><span data-stu-id="72db5-124">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="72db5-125">Значения качества производительности: **Running** или **Stopped**.</span><span class="sxs-lookup"><span data-stu-id="72db5-125">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="72db5-126">Зависимости</span><span class="sxs-lookup"><span data-stu-id="72db5-126">Dependencies</span></span> | <span data-ttu-id="72db5-127">Массив имен зависимостей, которые должна иметь служба.</span><span class="sxs-lookup"><span data-stu-id="72db5-127">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="72db5-128">Описание</span><span class="sxs-lookup"><span data-stu-id="72db5-128">Description</span></span> |<span data-ttu-id="72db5-129">Указывает описание целевой службы.</span><span class="sxs-lookup"><span data-stu-id="72db5-129">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="72db5-130">DisplayName</span><span class="sxs-lookup"><span data-stu-id="72db5-130">DisplayName</span></span> |<span data-ttu-id="72db5-131">Указывает отображаемое имя целевой службы.</span><span class="sxs-lookup"><span data-stu-id="72db5-131">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="72db5-132">Путь</span><span class="sxs-lookup"><span data-stu-id="72db5-132">Path</span></span> |<span data-ttu-id="72db5-133">Указывает путь к двоичному файлу для новой службы.</span><span class="sxs-lookup"><span data-stu-id="72db5-133">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="72db5-134">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="72db5-134">Common properties</span></span>

|<span data-ttu-id="72db5-135">Свойство</span><span class="sxs-lookup"><span data-stu-id="72db5-135">Property</span></span> |<span data-ttu-id="72db5-136">Описание</span><span class="sxs-lookup"><span data-stu-id="72db5-136">Description</span></span> |
|---|---|
|<span data-ttu-id="72db5-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="72db5-137">DependsOn</span></span> |<span data-ttu-id="72db5-138">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="72db5-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="72db5-139">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="72db5-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="72db5-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="72db5-140">Ensure</span></span> |<span data-ttu-id="72db5-141">Указывает, имеется ли целевая служба в системе.</span><span class="sxs-lookup"><span data-stu-id="72db5-141">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="72db5-142">Если целевая служба не должна существовать, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="72db5-142">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="72db5-143">Если целевая служба должна существовать, укажите значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="72db5-143">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="72db5-144">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="72db5-144">The default value is **Present**.</span></span> |
|<span data-ttu-id="72db5-145">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="72db5-145">PsDscRunAsCredential</span></span> |<span data-ttu-id="72db5-146">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="72db5-146">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="72db5-147">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="72db5-147">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="72db5-148">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="72db5-148">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="72db5-149">Пример</span><span class="sxs-lookup"><span data-stu-id="72db5-149">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
