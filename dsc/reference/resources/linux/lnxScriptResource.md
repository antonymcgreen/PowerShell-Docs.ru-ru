---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxScript в DSC для Linux
ms.openlocfilehash: 339968512ab1c16c4c3785a3a19b00c3fbbf9ea1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077829"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="3565d-103">Ресурс nxScript в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="3565d-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="3565d-104">Ресурс **nxScript** в DSC PowerShell предоставляет механизм управления сценариями Linux на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="3565d-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="3565d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3565d-105">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="3565d-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="3565d-106">Properties</span></span>

|  <span data-ttu-id="3565d-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="3565d-107">Property</span></span> |  <span data-ttu-id="3565d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3565d-108">Description</span></span> |
|---|---|
| <span data-ttu-id="3565d-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="3565d-109">GetScript</span></span>| <span data-ttu-id="3565d-110">Предоставляет сценарий, который выполняется при вызове командлета [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx).</span><span class="sxs-lookup"><span data-stu-id="3565d-110">Provides a script that runs when you invoke the [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet.</span></span> <span data-ttu-id="3565d-111">Сценарий должен начинаться со знака решетки, например #!/bin/bash.</span><span class="sxs-lookup"><span data-stu-id="3565d-111">The script must begin with a shebang, such as #!/bin/bash.</span></span>|
| <span data-ttu-id="3565d-112">SetScript</span><span class="sxs-lookup"><span data-stu-id="3565d-112">SetScript</span></span>| <span data-ttu-id="3565d-113">Предоставляет сценарий.</span><span class="sxs-lookup"><span data-stu-id="3565d-113">Provides a script.</span></span> <span data-ttu-id="3565d-114">При вызове командлета [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) в первую очередь выполняется команда **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="3565d-114">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, the **TestScript** runs first.</span></span> <span data-ttu-id="3565d-115">Если блок **TestScript** возвращает код выхода, отличный от 0, запускается блок **SetScript**.</span><span class="sxs-lookup"><span data-stu-id="3565d-115">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="3565d-116">Если блок **TestScript** возвращает код выхода 0, **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3565d-116">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="3565d-117">Сценарий должен начинаться со знака решетки, например `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="3565d-117">The script must begin with a shebang, such as `#!/bin/bash`.</span></span>|
| <span data-ttu-id="3565d-118">TestScript</span><span class="sxs-lookup"><span data-stu-id="3565d-118">TestScript</span></span>| <span data-ttu-id="3565d-119">Предоставляет сценарий.</span><span class="sxs-lookup"><span data-stu-id="3565d-119">Provides a script.</span></span> <span data-ttu-id="3565d-120">При вызове командлета [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) выполняется этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="3565d-120">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, this script runs.</span></span> <span data-ttu-id="3565d-121">Если он возвращает код выхода, отличный от 0, выполняется команда SetScript.</span><span class="sxs-lookup"><span data-stu-id="3565d-121">If it returns an exit code other than 0, the SetScript will run.</span></span> <span data-ttu-id="3565d-122">Если он возвращает код выхода 0, команда **SetScript** не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3565d-122">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="3565d-123">Кроме того, **TestScript** выполняется при вызове командлета [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx).</span><span class="sxs-lookup"><span data-stu-id="3565d-123">The **TestScript** also runs when you invoke the [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) cmdlet.</span></span> <span data-ttu-id="3565d-124">Однако в этом случае **SetScript** не будет запущен, какое бы значение ни вернул блок **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="3565d-124">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="3565d-125">Блок **TestScript** должен возвращать код выхода 0, если фактическая конфигурация соответствует текущей настройке требуемого состояния, и другой код выхода, если они не совпадают.</span><span class="sxs-lookup"><span data-stu-id="3565d-125">The **TestScript** must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="3565d-126">(Текущей настройкой требуемого состояния является последняя конфигурация, активированная на узле, который использует DSC.)</span><span class="sxs-lookup"><span data-stu-id="3565d-126">(The current desired state configuration is the last configuration enacted on the node that is using DSC).</span></span> <span data-ttu-id="3565d-127">Сценарий должен начинаться со знака решетки, например 1#!/bin/bash.1</span><span class="sxs-lookup"><span data-stu-id="3565d-127">The script must begin with a shebang, such as 1#!/bin/bash.1</span></span>|
| <span data-ttu-id="3565d-128">User</span><span class="sxs-lookup"><span data-stu-id="3565d-128">User</span></span>| <span data-ttu-id="3565d-129">Указывает, от имени какого пользователя выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="3565d-129">The user to run the script as.</span></span>|
| <span data-ttu-id="3565d-130">Группа</span><span class="sxs-lookup"><span data-stu-id="3565d-130">Group</span></span>| <span data-ttu-id="3565d-131">Указывает, от имени какой группы выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="3565d-131">The group to run the script as.</span></span>|
| <span data-ttu-id="3565d-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="3565d-132">DependsOn</span></span> | <span data-ttu-id="3565d-133">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="3565d-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="3565d-134">Например, если **идентификатор** первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="3565d-134">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="3565d-135">Пример</span><span class="sxs-lookup"><span data-stu-id="3565d-135">Example</span></span>

<span data-ttu-id="3565d-136">В следующем примере показано применение ресурса **nxScript** для дополнительного управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3565d-136">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

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