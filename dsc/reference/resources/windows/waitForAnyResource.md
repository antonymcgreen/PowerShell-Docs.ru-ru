---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForAny
ms.openlocfilehash: d15acb3fb34d571eca56ed496eaa9a04b2551ff0
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726854"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="d44e1-103">Ресурс DSC WaitForAny</span><span class="sxs-lookup"><span data-stu-id="d44e1-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="d44e1-104">Область применения. Windows PowerShell 5.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d44e1-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="d44e1-105">Ресурс настройки требуемого состояния **WaitForAny** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="d44e1-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="d44e1-106">Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="d44e1-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="d44e1-107">Ресурс **WaitForAny** использует удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="d44e1-107">**WaitForAny** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="d44e1-108">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="d44e1-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="d44e1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d44e1-109">Syntax</span></span>

```
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="d44e1-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="d44e1-110">Properties</span></span>

|  <span data-ttu-id="d44e1-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="d44e1-111">Property</span></span>  |  <span data-ttu-id="d44e1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d44e1-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="d44e1-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="d44e1-113">ResourceName</span></span>| <span data-ttu-id="d44e1-114">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="d44e1-114">The resource name to depend on.</span></span> <span data-ttu-id="d44e1-115">Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".</span><span class="sxs-lookup"><span data-stu-id="d44e1-115">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="d44e1-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="d44e1-116">NodeName</span></span>| <span data-ttu-id="d44e1-117">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="d44e1-117">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="d44e1-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="d44e1-118">RetryIntervalSec</span></span>| <span data-ttu-id="d44e1-119">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="d44e1-119">The number of seconds before retrying.</span></span> <span data-ttu-id="d44e1-120">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="d44e1-120">Minimum is 1.</span></span>|
| <span data-ttu-id="d44e1-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="d44e1-121">RetryCount</span></span>| <span data-ttu-id="d44e1-122">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="d44e1-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="d44e1-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d44e1-123">ThrottleLimit</span></span>| <span data-ttu-id="d44e1-124">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d44e1-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="d44e1-125">Значение по умолчанию — New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="d44e1-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="d44e1-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="d44e1-126">DependsOn</span></span> | <span data-ttu-id="d44e1-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="d44e1-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="d44e1-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="d44e1-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="d44e1-129">Пример</span><span class="sxs-lookup"><span data-stu-id="d44e1-129">Example</span></span>

<span data-ttu-id="d44e1-130">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="d44e1-130">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
