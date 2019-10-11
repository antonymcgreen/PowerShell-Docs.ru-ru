---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxScript в DSC для Linux
ms.openlocfilehash: a7f2114aba47bb581cdd19168e784b79dfc5b6ad
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953191"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="bec6c-103">Ресурс nxScript в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="bec6c-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="bec6c-104">Ресурс **nxScript** в DSC PowerShell предоставляет механизм управления сценариями Linux на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="bec6c-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="bec6c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bec6c-105">Syntax</span></span>

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="bec6c-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="bec6c-106">Properties</span></span>

|<span data-ttu-id="bec6c-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="bec6c-107">Property</span></span> |<span data-ttu-id="bec6c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bec6c-108">Description</span></span> |
|---|---|
|<span data-ttu-id="bec6c-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="bec6c-109">GetScript</span></span> |<span data-ttu-id="bec6c-110">Предоставляет скрипт для возврата сведений о текущем состоянии компьютера.</span><span class="sxs-lookup"><span data-stu-id="bec6c-110">Provides a script to return current status of the machine.</span></span> <span data-ttu-id="bec6c-111">Этот скрипт выполняется при вызове скрипта [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="bec6c-111">This script runs when you invoke the [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="bec6c-112">Сценарий должен начинаться со знака решетки, например `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="bec6c-112">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="bec6c-113">SetScript</span><span class="sxs-lookup"><span data-stu-id="bec6c-113">SetScript</span></span> |<span data-ttu-id="bec6c-114">Предоставляет скрипт, с помощью которого компьютер переходит в надлежащее состояние.</span><span class="sxs-lookup"><span data-stu-id="bec6c-114">Provides a script that puts the machine in the correct state.</span></span> <span data-ttu-id="bec6c-115">При вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) в первую очередь выполняется команда **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="bec6c-115">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, the **TestScript** runs first.</span></span> <span data-ttu-id="bec6c-116">Если блок **TestScript** возвращает код выхода, отличный от 0, запускается блок **SetScript**.</span><span class="sxs-lookup"><span data-stu-id="bec6c-116">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="bec6c-117">Если блок **TestScript** возвращает код выхода 0, **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bec6c-117">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="bec6c-118">Сценарий должен начинаться со знака решетки, например `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="bec6c-118">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="bec6c-119">TestScript</span><span class="sxs-lookup"><span data-stu-id="bec6c-119">TestScript</span></span> |<span data-ttu-id="bec6c-120">Предоставляет скрипт для оценки состояния узла.</span><span class="sxs-lookup"><span data-stu-id="bec6c-120">Provides a script that evaluates whether the node is currently in the correct state.</span></span> <span data-ttu-id="bec6c-121">Этот скрипт выполняется при вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="bec6c-121">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, this script runs.</span></span> <span data-ttu-id="bec6c-122">Если он возвращает код выхода, отличный от 0, выполняется команда **SetScript**.</span><span class="sxs-lookup"><span data-stu-id="bec6c-122">If it returns an exit code other than 0, the **SetScript** will run.</span></span> <span data-ttu-id="bec6c-123">Если он возвращает код выхода 0, команда **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bec6c-123">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="bec6c-124">Кроме того, **TestScript** выполняется при вызове скрипта [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="bec6c-124">The **TestScript** also runs when you invoke the [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="bec6c-125">Однако в этом случае **SetScript** не будет запущен, какое бы значение ни вернул блок **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="bec6c-125">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="bec6c-126">Блок **TestScript** должен содержать контент и возвращать код выхода 0, если фактическая конфигурация соответствует текущей настройке требуемого состояния, и другой код выхода, если они не совпадают.</span><span class="sxs-lookup"><span data-stu-id="bec6c-126">The **TestScript** must contain content and must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="bec6c-127">Текущей конфигурацией требуемого состояния является последняя конфигурация, активированная на узле, который использует DSC.</span><span class="sxs-lookup"><span data-stu-id="bec6c-127">The current desired state configuration is the last configuration enacted on the node that is using DSC.</span></span> <span data-ttu-id="bec6c-128">Сценарий должен начинаться со знака решетки, например `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="bec6c-128">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="bec6c-129">User</span><span class="sxs-lookup"><span data-stu-id="bec6c-129">User</span></span> |<span data-ttu-id="bec6c-130">Указывает, от имени какого пользователя выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="bec6c-130">The user to run the script as.</span></span> |
|<span data-ttu-id="bec6c-131">Группа</span><span class="sxs-lookup"><span data-stu-id="bec6c-131">Group</span></span> |<span data-ttu-id="bec6c-132">Указывает, от имени какой группы выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="bec6c-132">The group to run the script as.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="bec6c-133">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="bec6c-133">Common properties</span></span>

|<span data-ttu-id="bec6c-134">Свойство</span><span class="sxs-lookup"><span data-stu-id="bec6c-134">Property</span></span> |<span data-ttu-id="bec6c-135">Описание</span><span class="sxs-lookup"><span data-stu-id="bec6c-135">Description</span></span> |
|---|---|
|<span data-ttu-id="bec6c-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="bec6c-136">DependsOn</span></span> |<span data-ttu-id="bec6c-137">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="bec6c-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="bec6c-138">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="bec6c-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="example"></a><span data-ttu-id="bec6c-139">Пример</span><span class="sxs-lookup"><span data-stu-id="bec6c-139">Example</span></span>

<span data-ttu-id="bec6c-140">В следующем примере показано применение ресурса **nxScript** для дополнительного управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="bec6c-140">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
