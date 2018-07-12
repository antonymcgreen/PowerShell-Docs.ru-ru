---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: fcf2adf67f36edb534df3e2a849459fb20e1c2de
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892369"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a><span data-ttu-id="5ca22-102">Извлечение и анализ структурированных объектов вне строки</span><span class="sxs-lookup"><span data-stu-id="5ca22-102">Extract and Parse Structured Objects out of String</span></span>

<span data-ttu-id="5ca22-103">Здесь также расширена функциональность командлета `ConvertFrom-String`:</span><span class="sxs-lookup"><span data-stu-id="5ca22-103">This also introduces some additional functionality for the `ConvertFrom-String` cmdlet:</span></span>

- <span data-ttu-id="5ca22-104">Удалено свойство текста экстента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ca22-104">Removes the extent text property by default.</span></span> <span data-ttu-id="5ca22-105">Теперь его можно включить с помощью параметра -IncludeExtent.</span><span class="sxs-lookup"><span data-stu-id="5ca22-105">You can include it with the -IncludeExtent parameter.</span></span>

- <span data-ttu-id="5ca22-106">Исправлены многие ошибки в алгоритмах обучения благодаря отзывам MVP и участников сообщества.</span><span class="sxs-lookup"><span data-stu-id="5ca22-106">Many learning algorithm bug fixes from MVP and community feedback.</span></span>

- <span data-ttu-id="5ca22-107">Новый параметр -UpdateTemplate для сохранения результатов алгоритма обучения в комментарий внутри файла шаблона.</span><span class="sxs-lookup"><span data-stu-id="5ca22-107">A new -UpdateTemplate parameter to save the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="5ca22-108">Это делает затраты на процесс обучения (являющийся самым медленным этапом) единовременными.</span><span class="sxs-lookup"><span data-stu-id="5ca22-108">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="5ca22-109">Выполнение Convert-String с шаблоном, содержащим закодированный обучающий алгоритм, теперь осуществляется практически мгновенно.</span><span class="sxs-lookup"><span data-stu-id="5ca22-109">Running Convert-String with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>

## <a name="extract-and-parse-structured-objects-out-of-string-content"></a><span data-ttu-id="5ca22-110">Извлечение и анализ структурированных объектов вне строки</span><span class="sxs-lookup"><span data-stu-id="5ca22-110">Extract and parse structured objects out of string content</span></span>

<span data-ttu-id="5ca22-111">При сотрудничестве с [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) был добавлен новый командлет `ConvertFrom-String`.</span><span class="sxs-lookup"><span data-stu-id="5ca22-111">In collaboration with [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F), a new `ConvertFrom-String` cmdlet has been added.</span></span>

<span data-ttu-id="5ca22-112">Он поддерживает два режима: базовый анализ с разделением и анализ с управлением автоматически создаваемым примером.</span><span class="sxs-lookup"><span data-stu-id="5ca22-112">This cmdlet supports two modes: basic delimited parsing, and auto generated example-driven parsing.</span></span>

<span data-ttu-id="5ca22-113">Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.</span><span class="sxs-lookup"><span data-stu-id="5ca22-113">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span> <span data-ttu-id="5ca22-114">Разделитель можно настроить:</span><span class="sxs-lookup"><span data-stu-id="5ca22-114">You can customize the delimiter:</span></span>

```powershell
"Hello World" | ConvertFrom-String | Format-Table -Auto
```

```output
P1     P2
--     --
Hello  World
```

<span data-ttu-id="5ca22-115">Командлет также поддерживает анализ с управлением автоматически создаваемым примером, основанные на исследованиях технологии [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) в [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F).</span><span class="sxs-lookup"><span data-stu-id="5ca22-115">The cmdlet also supports auto-generated example-driven parsing based on the [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) research work in [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F).</span></span>

<span data-ttu-id="5ca22-116">Для начала рассмотрим текстовую адресную книгу:</span><span class="sxs-lookup"><span data-stu-id="5ca22-116">To get started, consider a text-based address book:</span></span>

```
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
```

<span data-ttu-id="5ca22-117">Скопируйте несколько примеров в файл, который будет использоваться в качестве шаблона:</span><span class="sxs-lookup"><span data-stu-id="5ca22-117">Copy a few examples into a file, which you will use as your template:</span></span>

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA
```

<span data-ttu-id="5ca22-118">Заключите извлекаемые данные в фигурные скобки, при этом им присваивается имя.</span><span class="sxs-lookup"><span data-stu-id="5ca22-118">Put curly braces around data that you want to extract, giving it a name as you do so.</span></span> <span data-ttu-id="5ca22-119">Поскольку свойство **Name** (и другие связанные с ним свойства) могут встречаться несколько раз, используйте звездочку (\*), чтобы указать, что результат представлен несколькими записями (вместо извлечения множества свойств в одну запись):</span><span class="sxs-lookup"><span data-stu-id="5ca22-119">Because the **Name** property (and its associated other properties) can appear multiple times, use an asterisk (\*) to indicate that this results in multiple records (rather than extracting a bunch of properties into one record):</span></span>

```
    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}
```

<span data-ttu-id="5ca22-120">Используя этот набор примеров, `ConvertFrom-String` может автоматически извлекать выходные данные на основе объектов из входных файлов с аналогичной структурой.</span><span class="sxs-lookup"><span data-stu-id="5ca22-120">From this set of examples, `ConvertFrom-String` can now automatically extract object-based output from input files with similar structure.</span></span>

```powershell
Get-Content .\addresses.output.txt | ConvertFrom-String -TemplateFile .\addresses.template.txt | Format-Table -Auto
```

```output
ExtentText                     Name               City     State
----------                     ----               ----     -----
Ana Trujillo...                Ana Trujillo       Redmond  WA
Antonio Moreno...              Antonio Moreno     Renton   WA
Thomas Hardy...                Thomas Hardy       Seattle  WA
Christina Berglund...          Christina Berglund Redmond  WA
Hanna Moos...                  Hanna Moos         Puyallup WA
```

<span data-ttu-id="5ca22-121">В целях дополнительной обработки извлеченного текста свойство **ExtentText** может фиксировать необработанный текст, из которого извлекалась запись.</span><span class="sxs-lookup"><span data-stu-id="5ca22-121">To do additional data manipulation on extracted text, the **ExtentText** property captures the raw text from which the record was extracted.</span></span> <span data-ttu-id="5ca22-122">Чтобы дать отзыв об этой функции или предоставить содержимое, для которого у вас не получается составить примеры, отправьте сообщение электронной почты на адрес <psdmfb@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="5ca22-122">To provide feedback on this feature, or to share content for which you are having difficulty writing examples, please email <psdmfb@microsoft.com>.</span></span>