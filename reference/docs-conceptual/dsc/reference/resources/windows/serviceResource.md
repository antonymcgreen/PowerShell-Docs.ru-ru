---
ms.date: 09/20/2019
ms.topic: reference
title: Ресурс Service в DSC
description: Ресурс Service в DSC
ms.openlocfilehash: 24121688bc46dcef70e3751d243d140fb7fcc7c9
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142630"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="d85c0-103">Ресурс Service в DSC</span><span class="sxs-lookup"><span data-stu-id="d85c0-103">DSC Service Resource</span></span>

> <span data-ttu-id="d85c0-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="d85c0-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="d85c0-105">Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="d85c0-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="d85c0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d85c0-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="d85c0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d85c0-107">Properties</span></span>

|<span data-ttu-id="d85c0-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="d85c0-108">Property</span></span> |<span data-ttu-id="d85c0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d85c0-109">Description</span></span> |
|---|---|
|<span data-ttu-id="d85c0-110">Имя</span><span class="sxs-lookup"><span data-stu-id="d85c0-110">Name</span></span> |<span data-ttu-id="d85c0-111">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="d85c0-111">Indicates the service name.</span></span> <span data-ttu-id="d85c0-112">Обратите внимание! Иногда оно отличается от отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="d85c0-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="d85c0-113">Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="d85c0-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="d85c0-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="d85c0-114">BuiltInAccount</span></span> |<span data-ttu-id="d85c0-115">Указывает учетную запись, используемую службой для входа.</span><span class="sxs-lookup"><span data-stu-id="d85c0-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="d85c0-116">Допустимые значения этого свойства: **LocalService** , **LocalSystem** и **NetworkService** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-116">The values that are allowed for this property are: **LocalService** , **LocalSystem** , and **NetworkService** .</span></span> |
|<span data-ttu-id="d85c0-117">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="d85c0-117">Credential</span></span> |<span data-ttu-id="d85c0-118">Указывает учетные данные для учетной записи, от имени которой будет запускаться служба.</span><span class="sxs-lookup"><span data-stu-id="d85c0-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="d85c0-119">Это свойство нельзя использовать одновременно со свойством **BuiltinAccount** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="d85c0-120">StartupType</span><span class="sxs-lookup"><span data-stu-id="d85c0-120">StartupType</span></span> |<span data-ttu-id="d85c0-121">Указывает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="d85c0-121">Indicates the startup type for the service.</span></span> <span data-ttu-id="d85c0-122">Допустимые значения этого свойства: **Automatic** , **Disabled** и **Manual** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-122">The values that are allowed for this property are: **Automatic** , **Disabled** , and **Manual** .</span></span> |
|<span data-ttu-id="d85c0-123">Состояние</span><span class="sxs-lookup"><span data-stu-id="d85c0-123">State</span></span> |<span data-ttu-id="d85c0-124">Указывает состояние, в котором должна находиться служба.</span><span class="sxs-lookup"><span data-stu-id="d85c0-124">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="d85c0-125">Значения качества производительности: **Running** или **Stopped** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-125">The values are: **Running** or **Stopped** .</span></span> |
|<span data-ttu-id="d85c0-126">Зависимости</span><span class="sxs-lookup"><span data-stu-id="d85c0-126">Dependencies</span></span> | <span data-ttu-id="d85c0-127">Массив имен зависимостей, которые должна иметь служба.</span><span class="sxs-lookup"><span data-stu-id="d85c0-127">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="d85c0-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d85c0-128">Description</span></span> |<span data-ttu-id="d85c0-129">Указывает описание целевой службы.</span><span class="sxs-lookup"><span data-stu-id="d85c0-129">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="d85c0-130">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d85c0-130">DisplayName</span></span> |<span data-ttu-id="d85c0-131">Указывает отображаемое имя целевой службы.</span><span class="sxs-lookup"><span data-stu-id="d85c0-131">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="d85c0-132">Путь</span><span class="sxs-lookup"><span data-stu-id="d85c0-132">Path</span></span> |<span data-ttu-id="d85c0-133">Указывает путь к двоичному файлу для новой службы.</span><span class="sxs-lookup"><span data-stu-id="d85c0-133">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="d85c0-134">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="d85c0-134">Common properties</span></span>

|<span data-ttu-id="d85c0-135">Свойство</span><span class="sxs-lookup"><span data-stu-id="d85c0-135">Property</span></span> |<span data-ttu-id="d85c0-136">Описание</span><span class="sxs-lookup"><span data-stu-id="d85c0-136">Description</span></span> |
|---|---|
|<span data-ttu-id="d85c0-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="d85c0-137">DependsOn</span></span> |<span data-ttu-id="d85c0-138">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="d85c0-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="d85c0-139">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="d85c0-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="d85c0-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="d85c0-140">Ensure</span></span> |<span data-ttu-id="d85c0-141">Указывает, имеется ли целевая служба в системе.</span><span class="sxs-lookup"><span data-stu-id="d85c0-141">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="d85c0-142">Если целевая служба не должна существовать, укажите для этого свойства значение **Absent** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-142">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="d85c0-143">Если целевая служба должна существовать, укажите значение **Present** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-143">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="d85c0-144">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="d85c0-144">The default value is **Present** .</span></span> |
|<span data-ttu-id="d85c0-145">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="d85c0-145">PsDscRunAsCredential</span></span> |<span data-ttu-id="d85c0-146">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="d85c0-146">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="d85c0-147">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d85c0-147">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="d85c0-148">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="d85c0-148">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="d85c0-149">Пример</span><span class="sxs-lookup"><span data-stu-id="d85c0-149">Example</span></span>

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
