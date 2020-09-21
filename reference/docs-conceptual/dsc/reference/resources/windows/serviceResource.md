---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Service в DSC
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463590"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="6e00a-103">Ресурс Service в DSC</span><span class="sxs-lookup"><span data-stu-id="6e00a-103">DSC Service Resource</span></span>

> <span data-ttu-id="6e00a-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="6e00a-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="6e00a-105">Ресурс **Service** в DSC Windows PowerShell предоставляет механизм управления службами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="6e00a-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e00a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e00a-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a><span data-ttu-id="6e00a-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6e00a-107">Properties</span></span>

|<span data-ttu-id="6e00a-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="6e00a-108">Property</span></span> |<span data-ttu-id="6e00a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6e00a-109">Description</span></span> |
|---|---|
|<span data-ttu-id="6e00a-110">Имя</span><span class="sxs-lookup"><span data-stu-id="6e00a-110">Name</span></span> |<span data-ttu-id="6e00a-111">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="6e00a-111">Indicates the service name.</span></span> <span data-ttu-id="6e00a-112">Обратите внимание! Иногда оно отличается от отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="6e00a-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="6e00a-113">Список служб и их текущее состояние можно получить с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="6e00a-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="6e00a-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="6e00a-114">BuiltInAccount</span></span> |<span data-ttu-id="6e00a-115">Указывает учетную запись, используемую службой для входа.</span><span class="sxs-lookup"><span data-stu-id="6e00a-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="6e00a-116">Допустимые значения этого свойства: **LocalService**, **LocalSystem** и **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="6e00a-117">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="6e00a-117">Credential</span></span> |<span data-ttu-id="6e00a-118">Указывает учетные данные для учетной записи, от имени которой будет запускаться служба.</span><span class="sxs-lookup"><span data-stu-id="6e00a-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="6e00a-119">Это свойство нельзя использовать одновременно со свойством **BuiltinAccount**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="6e00a-120">StartupTimeout</span><span class="sxs-lookup"><span data-stu-id="6e00a-120">StartupTimeout</span></span> | <span data-ttu-id="6e00a-121">Время ожидания выполнения службы в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="6e00a-121">The time to wait for the service to be running in milliseconds.</span></span>|
|<span data-ttu-id="6e00a-122">StartupType</span><span class="sxs-lookup"><span data-stu-id="6e00a-122">StartupType</span></span> |<span data-ttu-id="6e00a-123">Указывает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="6e00a-123">Indicates the startup type for the service.</span></span> <span data-ttu-id="6e00a-124">Допустимые значения этого свойства: **Automatic**, **Disabled** и **Manual**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-124">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="6e00a-125">Состояние</span><span class="sxs-lookup"><span data-stu-id="6e00a-125">State</span></span> |<span data-ttu-id="6e00a-126">Указывает состояние, в котором должна находиться служба.</span><span class="sxs-lookup"><span data-stu-id="6e00a-126">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="6e00a-127">Значения качества производительности: **Running** или **Stopped**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-127">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="6e00a-128">TerminateTimeout</span><span class="sxs-lookup"><span data-stu-id="6e00a-128">TerminateTimeout</span></span> |<span data-ttu-id="6e00a-129">Время ожидания остановки службы в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="6e00a-129">The time to wait for the service to be stopped in milliseconds.</span></span>|
|<span data-ttu-id="6e00a-130">Зависимости</span><span class="sxs-lookup"><span data-stu-id="6e00a-130">Dependencies</span></span> | <span data-ttu-id="6e00a-131">Массив имен зависимостей, которые должна иметь служба.</span><span class="sxs-lookup"><span data-stu-id="6e00a-131">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="6e00a-132">Описание</span><span class="sxs-lookup"><span data-stu-id="6e00a-132">Description</span></span> |<span data-ttu-id="6e00a-133">Указывает описание целевой службы.</span><span class="sxs-lookup"><span data-stu-id="6e00a-133">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="6e00a-134">DesktopInteract</span><span class="sxs-lookup"><span data-stu-id="6e00a-134">DesktopInteract</span></span> | <span data-ttu-id="6e00a-135">Указывает, должна ли служба взаимодействовать с окном на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="6e00a-135">Indicates whether or not the service should be able to communicate with a window on the desktop.</span></span> <span data-ttu-id="6e00a-136">Для служб, не работающих в качестве LocalSystem, должно быть задано значение false.</span><span class="sxs-lookup"><span data-stu-id="6e00a-136">Must be false for services not running as LocalSystem.</span></span>|
|<span data-ttu-id="6e00a-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6e00a-137">DisplayName</span></span> |<span data-ttu-id="6e00a-138">Указывает отображаемое имя целевой службы.</span><span class="sxs-lookup"><span data-stu-id="6e00a-138">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="6e00a-139">Путь</span><span class="sxs-lookup"><span data-stu-id="6e00a-139">Path</span></span> |<span data-ttu-id="6e00a-140">Указывает путь к двоичному файлу для новой службы.</span><span class="sxs-lookup"><span data-stu-id="6e00a-140">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="6e00a-141">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="6e00a-141">Common properties</span></span>

|<span data-ttu-id="6e00a-142">Свойство</span><span class="sxs-lookup"><span data-stu-id="6e00a-142">Property</span></span> |<span data-ttu-id="6e00a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="6e00a-143">Description</span></span> |
|---|---|
|<span data-ttu-id="6e00a-144">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6e00a-144">DependsOn</span></span> |<span data-ttu-id="6e00a-145">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="6e00a-145">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6e00a-146">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="6e00a-146">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="6e00a-147">Ensure</span><span class="sxs-lookup"><span data-stu-id="6e00a-147">Ensure</span></span> |<span data-ttu-id="6e00a-148">Указывает, имеется ли целевая служба в системе.</span><span class="sxs-lookup"><span data-stu-id="6e00a-148">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="6e00a-149">Если целевая служба не должна существовать, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-149">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="6e00a-150">Если целевая служба должна существовать, укажите значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-150">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="6e00a-151">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="6e00a-151">The default value is **Present**.</span></span> |
|<span data-ttu-id="6e00a-152">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="6e00a-152">PsDscRunAsCredential</span></span> |<span data-ttu-id="6e00a-153">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="6e00a-153">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="6e00a-154">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="6e00a-154">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="6e00a-155">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="6e00a-155">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="6e00a-156">Пример</span><span class="sxs-lookup"><span data-stu-id="6e00a-156">Example</span></span>

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
