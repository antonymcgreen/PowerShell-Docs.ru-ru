---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сортировка объектов
ms.openlocfilehash: ed78e7e333f3468781c9cd96df2194fbdfebe753
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030769"
---
# <a name="sorting-objects"></a><span data-ttu-id="c1748-103">Сортировка объектов</span><span class="sxs-lookup"><span data-stu-id="c1748-103">Sorting Objects</span></span>

<span data-ttu-id="c1748-104">С помощью командлета `Sort-Object` можно упорядочить отображаемые данные для упрощения их проверки.</span><span class="sxs-lookup"><span data-stu-id="c1748-104">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c1748-105">`Sort-Object` принимает имя одного или нескольких свойств, по значениям которых выполняется сортировка, и возвращает данные, отсортированные по значениям этих свойств.</span><span class="sxs-lookup"><span data-stu-id="c1748-105">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="c1748-106">Базовая сортировка</span><span class="sxs-lookup"><span data-stu-id="c1748-106">Basic sorting</span></span>

<span data-ttu-id="c1748-107">Рассмотрите проблему перечисления подкаталогов и файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c1748-107">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="c1748-108">Если требуется отсортировать по **LastWriteTime** (времени последней записи), а затем по **Name** имени, это можно сделать, введя следующие команды.</span><span class="sxs-lookup"><span data-stu-id="c1748-108">If we want to sort by **LastWriteTime** and then by **Name**, we can do it by typing:</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

<span data-ttu-id="c1748-109">Можно также отсортировать объекты в обратном порядке, указав параметр-переключатель **Descending** (по убыванию).</span><span class="sxs-lookup"><span data-stu-id="c1748-109">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a><span data-ttu-id="c1748-110">Использование хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="c1748-110">Using hash tables</span></span>

<span data-ttu-id="c1748-111">Используя хэш-таблицы в массиве, можно сортировать разные свойства в разном порядке.</span><span class="sxs-lookup"><span data-stu-id="c1748-111">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="c1748-112">Каждая хэш-таблица использует ключ **Expression** для указания имени свойства в виде строки и ключ **Ascending** (по возрастанию) или **Descending** (по убыванию) для указания порядка сортировки по `$true` или `$false`.</span><span class="sxs-lookup"><span data-stu-id="c1748-112">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="c1748-113">Ключ **Expression** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c1748-113">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="c1748-114">Ключи **Ascending** или **Descending** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="c1748-114">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="c1748-115">В следующем примере объекты сортируются в порядке убывания по  **LastWriteTime** и в порядке возрастания по **Name**.</span><span class="sxs-lookup"><span data-stu-id="c1748-115">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

<span data-ttu-id="c1748-116">Вы также можете установить блок скрипта для ключа **Expression**.</span><span class="sxs-lookup"><span data-stu-id="c1748-116">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="c1748-117">При выполнении командлета `Sort-Object` выполняется блок сценария, а его результат используется для сортировки.</span><span class="sxs-lookup"><span data-stu-id="c1748-117">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="c1748-118">В следующем примере объекты сортируются в порядке убывания в промежутке времени между **CreationTime** (временем создания файла) ​​и **LastWriteTime** (временем последней записи).</span><span class="sxs-lookup"><span data-stu-id="c1748-118">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime**.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a><span data-ttu-id="c1748-119">Советы</span><span class="sxs-lookup"><span data-stu-id="c1748-119">Tips</span></span>

<span data-ttu-id="c1748-120">Вы можете опустить имя параметра **Свойство** следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c1748-120">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="c1748-121">Кроме того, вы можете ссылаться на `Sort-Object` по его встроенному псевдониму `sort`.</span><span class="sxs-lookup"><span data-stu-id="c1748-121">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="c1748-122">Ключи в хэш-таблицах для сортировки можно сократить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c1748-122">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="c1748-123">В этом примере **e** расшифровывается **выражение**, **d** расшифровывается **по убыванию**и **a** обозначает **по возрастанию**.</span><span class="sxs-lookup"><span data-stu-id="c1748-123">In this example, the **e** stands for **Expression**, the **d** stands for **Descending**, and the **a** stands for **Ascending**.</span></span>

<span data-ttu-id="c1748-124">Чтобы улучшить читабельность, хэш-таблицы можно поместить в отдельную переменную.</span><span class="sxs-lookup"><span data-stu-id="c1748-124">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
