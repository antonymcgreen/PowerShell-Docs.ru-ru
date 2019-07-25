---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxScript в DSC для Linux
ms.openlocfilehash: 0ad0530f1de7b86ff48c4eb1f79870f6682894a1
ms.sourcegitcommit: 118eb294d5a84a772e6449d42a9d9324e18ef6b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2019
ms.locfileid: "68372161"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="307c7-103">Ресурс nxScript в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="307c7-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="307c7-104">Ресурс **nxScript** в DSC PowerShell предоставляет механизм управления сценариями Linux на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="307c7-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="307c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="307c7-105">Syntax</span></span>

```
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

## <a name="properties"></a><span data-ttu-id="307c7-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="307c7-106">Properties</span></span>

|  <span data-ttu-id="307c7-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="307c7-107">Property</span></span> |  <span data-ttu-id="307c7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="307c7-108">Description</span></span> |
|---|---|
| <span data-ttu-id="307c7-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="307c7-109">GetScript</span></span>| <span data-ttu-id="307c7-110">Предоставляет скрипт для возврата сведений о текущем состоянии компьютера.</span><span class="sxs-lookup"><span data-stu-id="307c7-110">Provides a script to return current status of the machine.</span></span>  <span data-ttu-id="307c7-111">Этот скрипт выполняется при вызове скрипта [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="307c7-111">This script runs when you invoke the [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="307c7-112">Сценарий должен начинаться со знака решетки, например #!/bin/bash.</span><span class="sxs-lookup"><span data-stu-id="307c7-112">The script must begin with a shebang, such as #!/bin/bash.</span></span>|
| <span data-ttu-id="307c7-113">SetScript</span><span class="sxs-lookup"><span data-stu-id="307c7-113">SetScript</span></span>| <span data-ttu-id="307c7-114">Предоставляет скрипт, с помощью которого компьютер переходит в надлежащее состояние.</span><span class="sxs-lookup"><span data-stu-id="307c7-114">Provides a script that puts the machine in the correct state.</span></span> <span data-ttu-id="307c7-115">При вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) в первую очередь выполняется команда **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="307c7-115">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, the **TestScript** runs first.</span></span> <span data-ttu-id="307c7-116">Если блок **TestScript** возвращает код выхода, отличный от 0, запускается блок **SetScript**.</span><span class="sxs-lookup"><span data-stu-id="307c7-116">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="307c7-117">Если блок **TestScript** возвращает код выхода 0, **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="307c7-117">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="307c7-118">Сценарий должен начинаться со знака решетки, например `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="307c7-118">The script must begin with a shebang, such as `#!/bin/bash`.</span></span>|
| <span data-ttu-id="307c7-119">TestScript</span><span class="sxs-lookup"><span data-stu-id="307c7-119">TestScript</span></span>| <span data-ttu-id="307c7-120">Предоставляет скрипт для оценки состояния узла.</span><span class="sxs-lookup"><span data-stu-id="307c7-120">Provides a script that evaluates whether the node is currently in the correct state.</span></span> <span data-ttu-id="307c7-121">Этот скрипт выполняется при вызове скрипта [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="307c7-121">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, this script runs.</span></span> <span data-ttu-id="307c7-122">Если он возвращает код выхода, отличный от 0, выполняется команда SetScript.</span><span class="sxs-lookup"><span data-stu-id="307c7-122">If it returns an exit code other than 0, the SetScript will run.</span></span> <span data-ttu-id="307c7-123">Если он возвращает код выхода 0, команда **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="307c7-123">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="307c7-124">Кроме того, **TestScript** выполняется при вызове скрипта [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer).</span><span class="sxs-lookup"><span data-stu-id="307c7-124">The **TestScript** also runs when you invoke the [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="307c7-125">Однако в этом случае **SetScript** не будет запущен, какое бы значение ни вернул блок **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="307c7-125">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="307c7-126">Блок **TestScript** должен содержать контент и возвращать код выхода 0, если фактическая конфигурация соответствует текущей настройке требуемого состояния, и другой код выхода, если они не совпадают.</span><span class="sxs-lookup"><span data-stu-id="307c7-126">The **TestScript** must contain content and must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="307c7-127">(Текущей настройкой требуемого состояния является последняя конфигурация, активированная на узле, который использует DSC.)</span><span class="sxs-lookup"><span data-stu-id="307c7-127">(The current desired state configuration is the last configuration enacted on the node that is using DSC).</span></span> <span data-ttu-id="307c7-128">Сценарий должен начинаться со знака решетки, например 1#!/bin/bash.1</span><span class="sxs-lookup"><span data-stu-id="307c7-128">The script must begin with a shebang, such as 1#!/bin/bash.1</span></span>|
| <span data-ttu-id="307c7-129">User</span><span class="sxs-lookup"><span data-stu-id="307c7-129">User</span></span>| <span data-ttu-id="307c7-130">Указывает, от имени какого пользователя выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="307c7-130">The user to run the script as.</span></span>|
| <span data-ttu-id="307c7-131">Группа</span><span class="sxs-lookup"><span data-stu-id="307c7-131">Group</span></span>| <span data-ttu-id="307c7-132">Указывает, от имени какой группы выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="307c7-132">The group to run the script as.</span></span>|
| <span data-ttu-id="307c7-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="307c7-133">DependsOn</span></span> | <span data-ttu-id="307c7-134">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="307c7-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="307c7-135">Например, если **идентификатор** первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="307c7-135">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="307c7-136">Пример</span><span class="sxs-lookup"><span data-stu-id="307c7-136">Example</span></span>

<span data-ttu-id="307c7-137">В следующем примере показано применение ресурса **nxScript** для дополнительного управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="307c7-137">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```
Import-DSCResource -Module nx

Node $node {
nxScript KeepDirEmpty{

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
