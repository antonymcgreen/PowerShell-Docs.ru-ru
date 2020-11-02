---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс DSC WaitForAll
description: Ресурс DSC WaitForAll
ms.openlocfilehash: a477584cf97a56815bda9973cb2befc9b71d14d1
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143115"
---
# <a name="dsc-waitforall-resource"></a><span data-ttu-id="656b2-103">Ресурс DSC WaitForAll</span><span class="sxs-lookup"><span data-stu-id="656b2-103">DSC WaitForAll Resource</span></span>

> <span data-ttu-id="656b2-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="656b2-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="656b2-105">Ресурс настройки требуемого состояния **WaitForAll** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="656b2-105">The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

<span data-ttu-id="656b2-106">Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName** , находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName** .</span><span class="sxs-lookup"><span data-stu-id="656b2-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="656b2-107">Ресурс **WaitForAll** использует удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="656b2-107">**WaitForAll** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="656b2-108">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="656b2-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="syntax"></a><span data-ttu-id="656b2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="656b2-109">Syntax</span></span>

```Syntax
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="656b2-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="656b2-110">Properties</span></span>

|<span data-ttu-id="656b2-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="656b2-111">Property</span></span> |<span data-ttu-id="656b2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="656b2-112">Description</span></span> |
|---|---|
|<span data-ttu-id="656b2-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="656b2-113">ResourceName</span></span> |<span data-ttu-id="656b2-114">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="656b2-114">The resource name to depend on.</span></span> <span data-ttu-id="656b2-115">Если этот ресурс относится к другой конфигурации, то его имя следует отформатировать как `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="656b2-115">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="656b2-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="656b2-116">NodeName</span></span> |<span data-ttu-id="656b2-117">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="656b2-117">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="656b2-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="656b2-118">RetryIntervalSec</span></span> |<span data-ttu-id="656b2-119">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="656b2-119">The number of seconds before retrying.</span></span> <span data-ttu-id="656b2-120">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="656b2-120">Minimum is 1.</span></span> |
|<span data-ttu-id="656b2-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="656b2-121">RetryCount</span></span> |<span data-ttu-id="656b2-122">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="656b2-122">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="656b2-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="656b2-123">ThrottleLimit</span></span> |<span data-ttu-id="656b2-124">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="656b2-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="656b2-125">Значение по умолчанию — `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="656b2-125">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="656b2-126">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="656b2-126">Common properties</span></span>

|<span data-ttu-id="656b2-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="656b2-127">Property</span></span> |<span data-ttu-id="656b2-128">Описание</span><span class="sxs-lookup"><span data-stu-id="656b2-128">Description</span></span> |
|---|---|
|<span data-ttu-id="656b2-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="656b2-129">DependsOn</span></span> |<span data-ttu-id="656b2-130">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="656b2-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="656b2-131">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="656b2-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="656b2-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="656b2-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="656b2-133">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="656b2-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="656b2-134">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="656b2-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="656b2-135">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="656b2-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="656b2-136">Пример</span><span class="sxs-lookup"><span data-stu-id="656b2-136">Example</span></span>

<span data-ttu-id="656b2-137">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="656b2-137">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
