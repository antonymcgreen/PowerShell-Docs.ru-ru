---
ms.date: 07/17/2020
ms.topic: reference
title: Ресурс nxService в DSC для Linux
description: Ресурс nxService в DSC для Linux
ms.openlocfilehash: 4eefe491c491c9245732def1cc85260f368ef9e1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648783"
---
# <a name="dsc-for-linux-nxservice-resource"></a><span data-ttu-id="da8ed-103">Ресурс nxService в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="da8ed-103">DSC for Linux nxService Resource</span></span>

<span data-ttu-id="da8ed-104">Ресурс **nxService** в настройке требуемого состояния PowerShell предоставляет механизм управления службами на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="da8ed-104">The **nxService** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="da8ed-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da8ed-105">Syntax</span></span>

```Syntax
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="da8ed-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="da8ed-106">Properties</span></span>

|<span data-ttu-id="da8ed-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="da8ed-107">Property</span></span> |<span data-ttu-id="da8ed-108">Description</span><span class="sxs-lookup"><span data-stu-id="da8ed-108">Description</span></span> |
|---|---|
|<span data-ttu-id="da8ed-109">Имя</span><span class="sxs-lookup"><span data-stu-id="da8ed-109">Name</span></span> |<span data-ttu-id="da8ed-110">Указывает имя службы или управляющей программы, которую нужно настроить.</span><span class="sxs-lookup"><span data-stu-id="da8ed-110">The name of the service/daemon to configure.</span></span> |
|<span data-ttu-id="da8ed-111">Контроллер</span><span class="sxs-lookup"><span data-stu-id="da8ed-111">Controller</span></span> |<span data-ttu-id="da8ed-112">Указывает тип контроллера для использования при настройке службы.</span><span class="sxs-lookup"><span data-stu-id="da8ed-112">The type of service controller to use when configuring the service.</span></span> |
|<span data-ttu-id="da8ed-113">Активировано</span><span class="sxs-lookup"><span data-stu-id="da8ed-113">Enabled</span></span> |<span data-ttu-id="da8ed-114">Указывает, запускается ли служба во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="da8ed-114">Indicates whether the service starts on boot.</span></span> |
|<span data-ttu-id="da8ed-115">Штат</span><span class="sxs-lookup"><span data-stu-id="da8ed-115">State</span></span> |<span data-ttu-id="da8ed-116">Указывает, запущена ли служба.</span><span class="sxs-lookup"><span data-stu-id="da8ed-116">Indicates whether the service is running.</span></span> <span data-ttu-id="da8ed-117">Установите для этого свойства значение **Stopped** , чтобы служба не выполнялась.</span><span class="sxs-lookup"><span data-stu-id="da8ed-117">Set this property to **Stopped** to ensure that the service is not running.</span></span> <span data-ttu-id="da8ed-118">Установите для этого свойства значение **Running** , чтобы служба выполнялась.</span><span class="sxs-lookup"><span data-stu-id="da8ed-118">Set it to **Running** to ensure that the service is running.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="da8ed-119">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="da8ed-119">Common properties</span></span>

|<span data-ttu-id="da8ed-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="da8ed-120">Property</span></span> |<span data-ttu-id="da8ed-121">Description</span><span class="sxs-lookup"><span data-stu-id="da8ed-121">Description</span></span> |
|---|---|
|<span data-ttu-id="da8ed-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="da8ed-122">DependsOn</span></span> |<span data-ttu-id="da8ed-123">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="da8ed-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="da8ed-124">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="da8ed-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="da8ed-125">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="da8ed-125">Additional Information</span></span>

<span data-ttu-id="da8ed-126">Ресурс **nxService** не создает определение или сценарий службы, если они не существуют.</span><span class="sxs-lookup"><span data-stu-id="da8ed-126">The **nxService** resource will not create a service definition or script for the service if it does not exist.</span></span> <span data-ttu-id="da8ed-127">Ресурс **nxFile** настройки требуемого состояния PowerShell можно использовать для управления существованием или содержанием сценария или файла определения службы.</span><span class="sxs-lookup"><span data-stu-id="da8ed-127">You can use the PowerShell Desired State Configuration **nxFile** Resource resource to manage the existence or contents of the service definition file or script.</span></span>

## <a name="example"></a><span data-ttu-id="da8ed-128">Пример</span><span class="sxs-lookup"><span data-stu-id="da8ed-128">Example</span></span>

<span data-ttu-id="da8ed-129">В следующем примере показана конфигурация службы httpd (для HTTP-сервера Apache), зарегистрированной с использованием контроллера службы **SystemD** .</span><span class="sxs-lookup"><span data-stu-id="da8ed-129">The following example shows configuration of the 'httpd' service (for Apache HTTP Server), registered with the **SystemD** service controller.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```
