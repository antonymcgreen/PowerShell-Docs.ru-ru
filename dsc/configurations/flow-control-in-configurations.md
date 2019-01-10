---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Условные операторы и циклы в конфигурациях
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402315"
---
# <a name="conditional-statements-and-loops-in-configurations"></a><span data-ttu-id="51377-103">Условные операторы и циклы в конфигурациях</span><span class="sxs-lookup"><span data-stu-id="51377-103">Conditional statements and loops in Configurations</span></span>

<span data-ttu-id="51377-104">Можно сделать ваши [конфигураций](configurations.md) более динамичными, с помощью ключевых слов PowerShell управления потоком.</span><span class="sxs-lookup"><span data-stu-id="51377-104">You can make your [Configurations](configurations.md) more dynamic using PowerShell flow-control keywords.</span></span> <span data-ttu-id="51377-105">В этой статье мы покажем, как можно использовать условные операторы и циклы выполняются ваши настройки более динамичной.</span><span class="sxs-lookup"><span data-stu-id="51377-105">This article will show you how you can use conditional statements, and loops to make your Configurations more dynamic.</span></span> <span data-ttu-id="51377-106">Условное объединение и циклы с [параметры](add-parameters-to-a-configuration.md) и [данные конфигурации](configData.md) обеспечивает дополнительную гибкость и контроль при компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-106">Combining conditional and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your Configurations.</span></span>

<span data-ttu-id="51377-107">Так же, как функции или блок скрипта можно использовать любой язык PowerShell, в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-107">Just like a Function or a Script Block, you can use any PowerShell language within a Configuration.</span></span> <span data-ttu-id="51377-108">Инструкции, которые используются вычисляется только в том случае, при вызове конфигурации для компиляции MOF «-» файла.</span><span class="sxs-lookup"><span data-stu-id="51377-108">The statements you use will only be evaluated when you call your Configuration to compile a ".mof" file.</span></span> <span data-ttu-id="51377-109">В приведенных ниже примерах показано простых сценариев для демонстрации концепций.</span><span class="sxs-lookup"><span data-stu-id="51377-109">The examples below show simple scenarios to demonstrate concepts.</span></span> <span data-ttu-id="51377-110">Условные выражения — это циклы чаще всего используются с параметрами и данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-110">Conditionals are loops are more often used with parameters and Configuration Data.</span></span>

<span data-ttu-id="51377-111">В этом простом примере **службы** блоке ресурсов возвращает текущее состояние службы во время компиляции для создания файла «.mof», его текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="51377-111">In this simple example, the **Service** resource block retrieves the current state of a service at compile time to generate a ".mof" file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="51377-112">С помощью динамические блоки ресурсов сосредоточенной эффективность Intellisense.</span><span class="sxs-lookup"><span data-stu-id="51377-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="51377-113">Средство синтаксического анализа PowerShell не может определить, если значения, указанные являются допустимыми, пока не компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-113">The PowerShell parser cannot determine if the values specified are acceptable until the Configuration is compiled.</span></span>

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

<span data-ttu-id="51377-114">Кроме того, можно создать **службы** блокировка ресурсов для каждой службы на текущем компьютере, с помощью `foreach` цикла.</span><span class="sxs-lookup"><span data-stu-id="51377-114">Additionally, you could create a **Service** block resource for every service on the current machine, using a `foreach` loop.</span></span>

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

<span data-ttu-id="51377-115">Также только для создания конфигурации для компьютеров, которые находятся в сети, с помощью простого `if` инструкции.</span><span class="sxs-lookup"><span data-stu-id="51377-115">You could also only create configurations for machines that are online, by using a simple `if` statement.</span></span>

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
> <span data-ttu-id="51377-116">Динамический ресурс блоков в приведенной выше схеме примеры текущего компьютера.</span><span class="sxs-lookup"><span data-stu-id="51377-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="51377-117">В этом экземпляре, который может быть компьютер, вы создаете конфигурации, не конечный узел.</span><span class="sxs-lookup"><span data-stu-id="51377-117">In this instance, that would be the machine you are authoring the Configuration on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="51377-118">Сводка</span><span class="sxs-lookup"><span data-stu-id="51377-118">Summary</span></span>

<span data-ttu-id="51377-119">Таким образом можно использовать любой язык PowerShell, в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-119">In summary, you can use any PowerShell language within a Configuration.</span></span>

<span data-ttu-id="51377-120">Сюда входят, например:</span><span class="sxs-lookup"><span data-stu-id="51377-120">This includes things like:</span></span>

- <span data-ttu-id="51377-121">Пользовательские объекты</span><span class="sxs-lookup"><span data-stu-id="51377-121">Custom Objects</span></span>
- <span data-ttu-id="51377-122">Хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="51377-122">Hashtables</span></span>
- <span data-ttu-id="51377-123">Управление строками</span><span class="sxs-lookup"><span data-stu-id="51377-123">String manipulation</span></span>
- <span data-ttu-id="51377-124">Удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="51377-124">Remoting</span></span>
- <span data-ttu-id="51377-125">WMI и CIM</span><span class="sxs-lookup"><span data-stu-id="51377-125">WMI and CIM</span></span>
- <span data-ttu-id="51377-126">ActiveDirectory объектов</span><span class="sxs-lookup"><span data-stu-id="51377-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="51377-127">и другое…</span><span class="sxs-lookup"><span data-stu-id="51377-127">and more...</span></span>

<span data-ttu-id="51377-128">Любой код PowerShell, определенный в конфигурации будет вычисляться как время компиляции, но можно также поместить код в скрипт, содержащий конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="51377-128">Any PowerShell code defined in a Configuration will be evaluated a compile time, but you can also place code in the script containing your Configuration.</span></span> <span data-ttu-id="51377-129">Никакого кода за пределами блока конфигурации будет выполняться при импорте конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51377-129">Any code outside of the Configuration block will be executed when you import your Configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="51377-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="51377-130">See also</span></span>

- [<span data-ttu-id="51377-131">Добавление параметров в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="51377-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="51377-132">Разделение данных конфигурации из конфигураций</span><span class="sxs-lookup"><span data-stu-id="51377-132">Separate Configuration data from Configurations</span></span>](configData.md)
