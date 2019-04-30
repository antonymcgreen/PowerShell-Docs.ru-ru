---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080141"
---
# <a name="conditional-statements-and-loops-in-configurations"></a><span data-ttu-id="b35ec-103">Условные операторы и циклы в конфигурациях</span><span class="sxs-lookup"><span data-stu-id="b35ec-103">Conditional statements and loops in Configurations</span></span>

<span data-ttu-id="b35ec-104">Вы можете сделать свои [конфигурации](configurations.md) более динамичными с помощью ключевых слов управления потоком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b35ec-104">You can make your [Configurations](configurations.md) more dynamic using PowerShell flow-control keywords.</span></span> <span data-ttu-id="b35ec-105">В этой статье показано использование условных операторов и циклов для более динамичной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b35ec-105">This article will show you how you can use conditional statements, and loops to make your Configurations more dynamic.</span></span> <span data-ttu-id="b35ec-106">Комбинирование условий и циклов с [параметрами](add-parameters-to-a-configuration.md) и [данными конфигурации](configData.md) обеспечивает большую гибкость и контроль при компиляции конфигураций.</span><span class="sxs-lookup"><span data-stu-id="b35ec-106">Combining conditional and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your Configurations.</span></span>

<span data-ttu-id="b35ec-107">Вы можете использовать любой язык PowerShell в конфигурации так же, как функцию или блок скриптов.</span><span class="sxs-lookup"><span data-stu-id="b35ec-107">Just like a Function or a Script Block, you can use any PowerShell language within a Configuration.</span></span> <span data-ttu-id="b35ec-108">Используемые вами операторы будут оцениваться только при вызове конфигурации для компиляции MOF-файла.</span><span class="sxs-lookup"><span data-stu-id="b35ec-108">The statements you use will only be evaluated when you call your Configuration to compile a ".mof" file.</span></span> <span data-ttu-id="b35ec-109">В приведенных ниже примерах показаны простые сценарии для демонстрации концепций.</span><span class="sxs-lookup"><span data-stu-id="b35ec-109">The examples below show simple scenarios to demonstrate concepts.</span></span> <span data-ttu-id="b35ec-110">Условия — это циклы, которые чаще всего используются с параметрами и данными конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b35ec-110">Conditionals are loops are more often used with parameters and Configuration Data.</span></span>

<span data-ttu-id="b35ec-111">В этом простом примере блок ресурсов **Служба** извлекает текущее состояние службы во время компиляции, чтобы создать MOF-файл, который сохраняет свое текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="b35ec-111">In this simple example, the **Service** resource block retrieves the current state of a service at compile time to generate a ".mof" file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="b35ec-112">Использование динамических блоков ресурсов снизит эффективность Intellisense.</span><span class="sxs-lookup"><span data-stu-id="b35ec-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="b35ec-113">Анализатор PowerShell не может определить, являются ли указанные значения приемлемыми, пока конфигурация не будет скомпилирована.</span><span class="sxs-lookup"><span data-stu-id="b35ec-113">The PowerShell parser cannot determine if the values specified are acceptable until the Configuration is compiled.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

<span data-ttu-id="b35ec-114">Кроме того, вы можете создать блок ресурса **Служба** для каждой службы на текущем компьютере, используя цикл `foreach`.</span><span class="sxs-lookup"><span data-stu-id="b35ec-114">Additionally, you could create a **Service** block resource for every service on the current machine, using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

<span data-ttu-id="b35ec-115">Вы также можете создавать конфигурации только для тех компьютеров, которые подключены к сети, используя простую инструкцию `if`.</span><span class="sxs-lookup"><span data-stu-id="b35ec-115">You could also only create configurations for machines that are online, by using a simple `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    Foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="b35ec-116">Блоки динамических ресурсов в приведенных выше примерах ссылаются на текущий компьютер.</span><span class="sxs-lookup"><span data-stu-id="b35ec-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="b35ec-117">В этом случае это будет компьютер, на котором вы создаете конфигурацию, а не целевой узел.</span><span class="sxs-lookup"><span data-stu-id="b35ec-117">In this instance, that would be the machine you are authoring the Configuration on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="b35ec-118">Сводка</span><span class="sxs-lookup"><span data-stu-id="b35ec-118">Summary</span></span>

<span data-ttu-id="b35ec-119">Таким образом в конфигурации можно использовать любой язык PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b35ec-119">In summary, you can use any PowerShell language within a Configuration.</span></span>

<span data-ttu-id="b35ec-120">Это включает в себя следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="b35ec-120">This includes things like:</span></span>

- <span data-ttu-id="b35ec-121">пользовательские объекты;</span><span class="sxs-lookup"><span data-stu-id="b35ec-121">Custom Objects</span></span>
- <span data-ttu-id="b35ec-122">хэш-таблицы;</span><span class="sxs-lookup"><span data-stu-id="b35ec-122">Hashtables</span></span>
- <span data-ttu-id="b35ec-123">управление строками;</span><span class="sxs-lookup"><span data-stu-id="b35ec-123">String manipulation</span></span>
- <span data-ttu-id="b35ec-124">Удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="b35ec-124">Remoting</span></span>
- <span data-ttu-id="b35ec-125">инструментарий WMI и CIM;</span><span class="sxs-lookup"><span data-stu-id="b35ec-125">WMI and CIM</span></span>
- <span data-ttu-id="b35ec-126">объекты ActiveDirectory;</span><span class="sxs-lookup"><span data-stu-id="b35ec-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="b35ec-127">и другое…</span><span class="sxs-lookup"><span data-stu-id="b35ec-127">and more...</span></span>

<span data-ttu-id="b35ec-128">Любой код PowerShell, определенный в конфигурации, будет оцениваться во время компиляции, но вы также можете поместить код в сценарий, содержащий вашу конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b35ec-128">Any PowerShell code defined in a Configuration will be evaluated a compile time, but you can also place code in the script containing your Configuration.</span></span> <span data-ttu-id="b35ec-129">Любой код за пределами блока конфигурации будет выполняться при импорте вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b35ec-129">Any code outside of the Configuration block will be executed when you import your Configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="b35ec-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="b35ec-130">See also</span></span>

- [<span data-ttu-id="b35ec-131">Добавление параметров в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="b35ec-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="b35ec-132">Разделение данных конфигурации из конфигураций</span><span class="sxs-lookup"><span data-stu-id="b35ec-132">Separate Configuration data from Configurations</span></span>](configData.md)
