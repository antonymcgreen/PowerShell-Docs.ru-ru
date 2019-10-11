---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForAny
ms.openlocfilehash: 61fee456d2652e08ed9bdbe64457627ff5b2e145
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953001"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="97add-103">Ресурс DSC WaitForAny</span><span class="sxs-lookup"><span data-stu-id="97add-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="97add-104">Область применения: Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="97add-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="97add-105">Ресурс настройки требуемого состояния **WaitForAny** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="97add-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="97add-106">Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="97add-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="97add-107">Ресурс **WaitForAny** использует удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="97add-107">**WaitForAny** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="97add-108">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="97add-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="97add-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97add-109">Syntax</span></span>

```Syntax
WaitForAny [string] #ResourceName
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

## <a name="properties"></a><span data-ttu-id="97add-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="97add-110">Properties</span></span>

|<span data-ttu-id="97add-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="97add-111">Property</span></span> |<span data-ttu-id="97add-112">Описание</span><span class="sxs-lookup"><span data-stu-id="97add-112">Description</span></span> |
|---|---|
|<span data-ttu-id="97add-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="97add-113">ResourceName</span></span> |<span data-ttu-id="97add-114">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="97add-114">The resource name to depend on.</span></span> <span data-ttu-id="97add-115">Если этот ресурс относится к другой конфигурации, то его имя следует отформатировать как `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="97add-115">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="97add-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="97add-116">NodeName</span></span> |<span data-ttu-id="97add-117">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="97add-117">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="97add-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="97add-118">RetryIntervalSec</span></span> |<span data-ttu-id="97add-119">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="97add-119">The number of seconds before retrying.</span></span> <span data-ttu-id="97add-120">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="97add-120">Minimum is 1.</span></span> |
|<span data-ttu-id="97add-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="97add-121">RetryCount</span></span> |<span data-ttu-id="97add-122">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="97add-122">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="97add-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="97add-123">ThrottleLimit</span></span> |<span data-ttu-id="97add-124">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="97add-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="97add-125">Значение по умолчанию — `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="97add-125">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="97add-126">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="97add-126">Common properties</span></span>

|<span data-ttu-id="97add-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="97add-127">Property</span></span> |<span data-ttu-id="97add-128">Описание</span><span class="sxs-lookup"><span data-stu-id="97add-128">Description</span></span> |
|---|---|
|<span data-ttu-id="97add-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="97add-129">DependsOn</span></span> |<span data-ttu-id="97add-130">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="97add-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="97add-131">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="97add-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="97add-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="97add-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="97add-133">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="97add-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="97add-134">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="97add-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="97add-135">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="97add-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="97add-136">Пример</span><span class="sxs-lookup"><span data-stu-id="97add-136">Example</span></span>

<span data-ttu-id="97add-137">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="97add-137">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>