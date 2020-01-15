---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 86f75be4a3d1c1760dd6269335431e8ab9fd8d09
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736902"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a><span data-ttu-id="984e3-103">Условные операторы и циклы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="984e3-103">Conditional statements and loops in a Configuration</span></span>

<span data-ttu-id="984e3-104">Вы можете сделать свою [конфигурацию](configurations.md) более динамичной с помощью ключевых слов управления потоком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="984e3-104">You can make your [Configuration](configurations.md) more dynamic by using PowerShell flow-control keywords.</span></span> <span data-ttu-id="984e3-105">В этой статье показано использование условных операторов и циклов для более динамичной `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="984e3-105">This article shows you how you can use conditional statements and loops to make your `Configuration` more dynamic.</span></span> <span data-ttu-id="984e3-106">Комбинирование условных операторов и циклов с [параметрами](add-parameters-to-a-configuration.md) и [данными конфигурации](configData.md) обеспечивает большую гибкость и контроль при компиляции `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="984e3-106">Combining conditional statements and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your `Configuration`.</span></span>

<span data-ttu-id="984e3-107">Вы можете использовать любую возможность языка PowerShell в `Configuration` так же, как функцию или блок скриптов.</span><span class="sxs-lookup"><span data-stu-id="984e3-107">Just like a function or a script block, you can use any PowerShell language feature within a `Configuration`.</span></span>
<span data-ttu-id="984e3-108">Используемые вами операторы будут оцениваться только при вызове `Configuration` для компиляции файла `.mof`.</span><span class="sxs-lookup"><span data-stu-id="984e3-108">The statements you use will only be evaluated when you call your `Configuration` to compile a `.mof` file.</span></span> <span data-ttu-id="984e3-109">В приведенных ниже примерах показаны сценарии для демонстрации концепций.</span><span class="sxs-lookup"><span data-stu-id="984e3-109">The examples below show scenarios to demonstrate concepts.</span></span> <span data-ttu-id="984e3-110">Условные операторы и циклы чаще всего используются с параметрами и данными конфигурации.</span><span class="sxs-lookup"><span data-stu-id="984e3-110">Conditional statements and loops are more often used with parameters and configuration Data.</span></span>

<span data-ttu-id="984e3-111">В этом примере блок ресурсов **Служба** извлекает текущее состояние службы во время компиляции, чтобы создать файл `.mof`, который сохраняет свое текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="984e3-111">In this  example, the **Service** resource block retrieves the current state of a service at compile time to generate a `.mof` file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="984e3-112">Использование динамических блоков ресурсов снизит эффективность Intellisense.</span><span class="sxs-lookup"><span data-stu-id="984e3-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="984e3-113">Анализатор PowerShell не может определить, являются ли указанные значения приемлемыми, пока `Configuration` не будет скомпилирована.</span><span class="sxs-lookup"><span data-stu-id="984e3-113">The PowerShell parser cannot determine if the values specified are acceptable until the `Configuration` is compiled.</span></span>

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

<span data-ttu-id="984e3-114">Кроме того, вы можете создать блок ресурса **Служба** для каждой службы на текущем компьютере, используя цикл `foreach`.</span><span class="sxs-lookup"><span data-stu-id="984e3-114">Additionally, you could create a **Service** resource block for every service on the current machine using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        foreach ($service in $(Get-Service))
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

<span data-ttu-id="984e3-115">Вы также можете создавать `Configuration` только для тех компьютеров, которые подключены к сети, используя оператор `if`.</span><span class="sxs-lookup"><span data-stu-id="984e3-115">You could also create a `Configuration` only for machines that are online by using an `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
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
> <span data-ttu-id="984e3-116">Блоки динамических ресурсов в приведенных выше примерах ссылаются на текущий компьютер.</span><span class="sxs-lookup"><span data-stu-id="984e3-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="984e3-117">В этом случае это будет компьютер, на котором вы создаете `Configuration`, а не целевой узел.</span><span class="sxs-lookup"><span data-stu-id="984e3-117">In this instance, that would be the machine you are authoring the `Configuration` on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="984e3-118">Сводка</span><span class="sxs-lookup"><span data-stu-id="984e3-118">Summary</span></span>

<span data-ttu-id="984e3-119">Таким образом в `Configuration` можно использовать любую возможность языка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="984e3-119">In summary, you can use any PowerShell language feature within a `Configuration`.</span></span>

<span data-ttu-id="984e3-120">Это включает в себя следующие вещи:</span><span class="sxs-lookup"><span data-stu-id="984e3-120">This includes things like:</span></span>

- <span data-ttu-id="984e3-121">пользовательские объекты;</span><span class="sxs-lookup"><span data-stu-id="984e3-121">Custom Objects</span></span>
- <span data-ttu-id="984e3-122">хэш-таблицы;</span><span class="sxs-lookup"><span data-stu-id="984e3-122">Hashtables</span></span>
- <span data-ttu-id="984e3-123">управление строками;</span><span class="sxs-lookup"><span data-stu-id="984e3-123">String manipulation</span></span>
- <span data-ttu-id="984e3-124">Удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="984e3-124">Remoting</span></span>
- <span data-ttu-id="984e3-125">инструментарий WMI и CIM;</span><span class="sxs-lookup"><span data-stu-id="984e3-125">WMI and CIM</span></span>
- <span data-ttu-id="984e3-126">объекты ActiveDirectory;</span><span class="sxs-lookup"><span data-stu-id="984e3-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="984e3-127">и другое…</span><span class="sxs-lookup"><span data-stu-id="984e3-127">and more...</span></span>

<span data-ttu-id="984e3-128">Любой код PowerShell, определенный в `Configuration`, оценивается во время компиляции, но вы также можете поместить код в скрипт, содержащий вашу `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="984e3-128">Any PowerShell code defined in a `Configuration` is evaluated at compile time, but you can also place code in the script containing your `Configuration`.</span></span> <span data-ttu-id="984e3-129">Любой код за пределами блока `Configuration` выполняется при импорте вашей `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="984e3-129">Any code outside of the `Configuration` block is executed when you import your `Configuration`.</span></span>

## <a name="see-also"></a><span data-ttu-id="984e3-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="984e3-130">See also</span></span>

- [<span data-ttu-id="984e3-131">Добавление параметров в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="984e3-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="984e3-132">Разделение данных конфигурации из конфигураций</span><span class="sxs-lookup"><span data-stu-id="984e3-132">Separate Configuration data from Configurations</span></span>](configData.md)
