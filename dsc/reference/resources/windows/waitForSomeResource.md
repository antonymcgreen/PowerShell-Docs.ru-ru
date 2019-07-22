---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: 2260f37002171154a6f2c3996b2af1bd9120039d
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726766"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="76722-103">Ресурс DSC WaitForSome</span><span class="sxs-lookup"><span data-stu-id="76722-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="76722-104">Область применения. Windows PowerShell 5.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="76722-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="76722-105">Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="76722-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="76722-106">Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="76722-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="76722-107">Ресурс **WaitForSome** использует удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="76722-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="76722-108">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="76722-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="76722-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76722-109">Syntax</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

## <a name="properties"></a><span data-ttu-id="76722-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="76722-110">Properties</span></span>

|  <span data-ttu-id="76722-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="76722-111">Property</span></span>  |  <span data-ttu-id="76722-112">Описание</span><span class="sxs-lookup"><span data-stu-id="76722-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="76722-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="76722-113">NodeCount</span></span>| <span data-ttu-id="76722-114">Минимальное количество узлов, которые должны быть в требуемом состоянии для успешного выполнения этого ресурса.</span><span class="sxs-lookup"><span data-stu-id="76722-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="76722-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="76722-115">NodeName</span></span>| <span data-ttu-id="76722-116">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="76722-116">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="76722-117">ResourceName</span><span class="sxs-lookup"><span data-stu-id="76722-117">ResourceName</span></span>| <span data-ttu-id="76722-118">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="76722-118">The resource name to depend on.</span></span> <span data-ttu-id="76722-119">Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".</span><span class="sxs-lookup"><span data-stu-id="76722-119">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="76722-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="76722-120">RetryIntervalSec</span></span>| <span data-ttu-id="76722-121">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="76722-121">The number of seconds before retrying.</span></span> <span data-ttu-id="76722-122">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="76722-122">Minimum is 1.</span></span>|
| <span data-ttu-id="76722-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="76722-123">RetryCount</span></span>| <span data-ttu-id="76722-124">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="76722-124">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="76722-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="76722-125">ThrottleLimit</span></span>| <span data-ttu-id="76722-126">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="76722-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="76722-127">Значение по умолчанию — New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="76722-127">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="76722-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="76722-128">DependsOn</span></span> | <span data-ttu-id="76722-129">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="76722-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="76722-130">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="76722-130">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="76722-131">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="76722-131">PsDscRunAsCredential</span></span> | <span data-ttu-id="76722-132">См. статью [Запуск DSC с учетными данными пользователя](https://docs.microsoft.com/powershell/dsc/runasuser).</span><span class="sxs-lookup"><span data-stu-id="76722-132">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |

## <a name="example"></a><span data-ttu-id="76722-133">Пример</span><span class="sxs-lookup"><span data-stu-id="76722-133">Example</span></span>

<span data-ttu-id="76722-134">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="76722-134">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
