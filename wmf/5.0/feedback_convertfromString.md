---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: e4588e8c69efb965cd33c273ad09a8bef8e9bf16
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a><span data-ttu-id="01133-102">Извлечение и анализ структурированных объектов вне строки</span><span class="sxs-lookup"><span data-stu-id="01133-102">Extract and Parse Structured Objects out of String</span></span>
<span data-ttu-id="01133-103">Здесь также расширена функциональность командлета ConvertFrom-String:</span><span class="sxs-lookup"><span data-stu-id="01133-103">This also introduces some additional functionality for the ConvertFrom-String cmdlet:</span></span>

-   <span data-ttu-id="01133-104">Удалено свойство текста экстента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="01133-104">Removes the extent text property by default.</span></span> <span data-ttu-id="01133-105">Теперь его можно включить с помощью параметра -IncludeExtent.</span><span class="sxs-lookup"><span data-stu-id="01133-105">You can include it with the -IncludeExtent parameter.</span></span>

-   <span data-ttu-id="01133-106">Исправлены многие ошибки в алгоритмах обучения благодаря отзывам MVP и участников сообщества.</span><span class="sxs-lookup"><span data-stu-id="01133-106">Many learning algorithm bug fixes from MVP and community feedback.</span></span>

-   <span data-ttu-id="01133-107">Новый параметр -UpdateTemplate для сохранения результатов алгоритма обучения в комментарий внутри файла шаблона.</span><span class="sxs-lookup"><span data-stu-id="01133-107">A new -UpdateTemplate parameter to save the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="01133-108">Это делает затраты на процесс обучения (являющийся самым медленным этапом) единовременными.</span><span class="sxs-lookup"><span data-stu-id="01133-108">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="01133-109">Выполнение Convert-String с шаблоном, содержащим закодированный обучающий алгоритм, теперь осуществляется практически мгновенно.</span><span class="sxs-lookup"><span data-stu-id="01133-109">Running Convert-String with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>


<a name="extract-and-parse-structured-objects-out-of-string-content"></a><span data-ttu-id="01133-110">Извлечение и анализ структурированных объектов вне строки</span><span class="sxs-lookup"><span data-stu-id="01133-110">Extract and parse structured objects out of string content</span></span>
----------------------------------------------------------

<span data-ttu-id="01133-111">При сотрудничестве с [Microsoft Research](http://research.microsoft.com/) был добавлен новый командлет **ConvertFrom-String**.</span><span class="sxs-lookup"><span data-stu-id="01133-111">In collaboration with [Microsoft Research](http://research.microsoft.com/), a new **ConvertFrom-String** cmdlet has been added.</span></span>

<span data-ttu-id="01133-112">Он поддерживает два режима: базовый анализ с разделением и анализ с управлением автоматически создаваемым примером.</span><span class="sxs-lookup"><span data-stu-id="01133-112">This cmdlet supports two modes: basic delimited parsing, and auto generated example-driven parsing.</span></span>

<span data-ttu-id="01133-113">Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.</span><span class="sxs-lookup"><span data-stu-id="01133-113">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span> <span data-ttu-id="01133-114">Разделитель можно настроить:</span><span class="sxs-lookup"><span data-stu-id="01133-114">You can customize the delimiter:</span></span>

> <span data-ttu-id="01133-115">1 \[C:\\temp\].&gt;&gt; "Hello World" | ConvertFrom-String | Format-Table -Auto</span><span class="sxs-lookup"><span data-stu-id="01133-115">1 \[C:\\temp\] &gt;&gt; "Hello World" | ConvertFrom-String | Format-Table -Auto</span></span>

<span data-ttu-id="01133-116">P1    P2</span><span class="sxs-lookup"><span data-stu-id="01133-116">P1    P2</span></span>
--    --

<span data-ttu-id="01133-117">Командлет также поддерживает анализ с управлением автоматически создаваемым примером, основанные на исследованиях технологии [FlashExtract](http://research.microsoft.com/en-us/um/people/sumitg/flashextract.html) в [Microsoft Research](http://research.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="01133-117">The cmdlet also supports auto-generated example-driven parsing based on the [FlashExtract](http://research.microsoft.com/en-us/um/people/sumitg/flashextract.html) research work in [Microsoft Research](http://research.microsoft.com).</span></span>

<span data-ttu-id="01133-118">Для начала рассмотрим текстовую адресную книгу:</span><span class="sxs-lookup"><span data-stu-id="01133-118">To get started, consider a text-based address book:</span></span>

    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA

    Thomas Hardy

    Seattle, WA

    Christina Berglund

    Redmond, WA

    Hanna Moos

    Puyallup, WA

<span data-ttu-id="01133-119">Скопируйте несколько примеров в файл, который будет использоваться в качестве шаблона:</span><span class="sxs-lookup"><span data-stu-id="01133-119">Copy a few examples into a file, which you will use as your template:</span></span>

    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA



<span data-ttu-id="01133-120">Заключите извлекаемые данные в фигурные скобки, при этом им присваивается имя.</span><span class="sxs-lookup"><span data-stu-id="01133-120">Put curly braces around data that you want to extract, giving it a name as you do so.</span></span> <span data-ttu-id="01133-121">Поскольку свойство **Name** (и другие связанные с ним свойства) могут встречаться несколько раз, используйте звездочку (\*), чтобы указать, что результат представлен несколькими записями (вместо извлечения множества свойств в одну запись):</span><span class="sxs-lookup"><span data-stu-id="01133-121">Because the **Name** property (and its associated other properties) can appear multiple times, use an asterisk (\*) to indicate that this results in multiple records (rather than extracting a bunch of properties into one record):</span></span>

    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}

<span data-ttu-id="01133-122">Используя этот набор примеров, **ConvertFrom-String** может автоматически извлекать выходные данные на основе объектов из входных файлов с аналогичной структурой.</span><span class="sxs-lookup"><span data-stu-id="01133-122">From this set of examples, **ConvertFrom-String** can now automatically extract object-based output from input files with similar structure.</span></span>

> <span data-ttu-id="01133-123">2 \[C:\\temp\]</span><span class="sxs-lookup"><span data-stu-id="01133-123">2 \[C:\\temp\]</span></span>
>
> <span data-ttu-id="01133-124">&gt;&gt; Get-Content .\\addresses.output.txt | ConvertFrom-String -TemplateFile .\\addresses.template.txt | &gt;&gt;&gt; Format-Table -Auto</span><span class="sxs-lookup"><span data-stu-id="01133-124">&gt;&gt; Get-Content .\\addresses.output.txt | ConvertFrom-String -TemplateFile .\\addresses.template.txt | &gt;&gt;&gt; Format-Table -Auto</span></span>
>
> <span data-ttu-id="01133-125">ExtentText                     Name               City     State</span><span class="sxs-lookup"><span data-stu-id="01133-125">ExtentText                     Name               City     State</span></span>
> ----------                     ----               ----     -----
> <span data-ttu-id="01133-126">Ana Trujillo...                Ana Trujillo       Redmond  WA Antonio Moreno...              Antonio Moreno     Renton   WA Thomas Hardy...                Thomas Hardy       Seattle  WA Christina Berglund...          Christina Berglund Redmond  WA Hanna Moos...                  Hanna Moos         Puyallup WA</span><span class="sxs-lookup"><span data-stu-id="01133-126">Ana Trujillo...                Ana Trujillo       Redmond  WA Antonio Moreno...              Antonio Moreno     Renton   WA Thomas Hardy...                Thomas Hardy       Seattle  WA Christina Berglund...          Christina Berglund Redmond  WA Hanna Moos...                  Hanna Moos         Puyallup WA</span></span>

<span data-ttu-id="01133-127">В целях дополнительной обработки извлеченного текста свойство **ExtentText** может фиксировать необработанный текст, из которого извлекалась запись.</span><span class="sxs-lookup"><span data-stu-id="01133-127">To do additional data manipulation on extracted text, the **ExtentText** property captures the raw text from which the record was extracted.</span></span> <span data-ttu-id="01133-128">Чтобы дать отзыв об этой функции или предоставить содержимое, для которого у вас не получается составить примеры, отправьте сообщение электронной почты на адрес <psdmfb@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="01133-128">To provide feedback on this feature, or to share content for which you are having difficulty writing examples, please email <psdmfb@microsoft.com>.</span></span>
