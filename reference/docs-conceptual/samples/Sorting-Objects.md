---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сортировка объектов
description: Командлет Sort-Object позволяет сортировать коллекцию объектов по одному или нескольким свойствам.
ms.openlocfilehash: 836207adfc566003e9714e45920d9b4e24a677e9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501020"
---
# <a name="sorting-objects"></a><span data-ttu-id="4abee-104">Сортировка объектов</span><span class="sxs-lookup"><span data-stu-id="4abee-104">Sorting Objects</span></span>

<span data-ttu-id="4abee-105">С помощью командлета `Sort-Object` можно упорядочить отображаемые данные для упрощения их проверки.</span><span class="sxs-lookup"><span data-stu-id="4abee-105">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="4abee-106">`Sort-Object` принимает имя одного или нескольких свойств, по значениям которых выполняется сортировка, и возвращает данные, отсортированные по значениям этих свойств.</span><span class="sxs-lookup"><span data-stu-id="4abee-106">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="4abee-107">Базовая сортировка</span><span class="sxs-lookup"><span data-stu-id="4abee-107">Basic sorting</span></span>

<span data-ttu-id="4abee-108">Рассмотрите проблему перечисления подкаталогов и файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4abee-108">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="4abee-109">Если требуется отсортировать по **LastWriteTime** (времени последней записи), а затем по **Name** имени, это можно сделать, введя следующие команды.</span><span class="sxs-lookup"><span data-stu-id="4abee-109">If we want to sort by **LastWriteTime** and then by **Name** , we can do it by typing:</span></span>

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

<span data-ttu-id="4abee-110">Можно также отсортировать объекты в обратном порядке, указав параметр-переключатель **Descending** (по убыванию).</span><span class="sxs-lookup"><span data-stu-id="4abee-110">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

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

## <a name="using-hash-tables"></a><span data-ttu-id="4abee-111">Использование хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="4abee-111">Using hash tables</span></span>

<span data-ttu-id="4abee-112">Используя хэш-таблицы в массиве, можно сортировать разные свойства в разном порядке.</span><span class="sxs-lookup"><span data-stu-id="4abee-112">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="4abee-113">Каждая хэш-таблица использует ключ **Expression** для указания имени свойства в виде строки и ключ **Ascending** (по возрастанию) или **Descending** (по убыванию) для указания порядка сортировки по `$true` или `$false`.</span><span class="sxs-lookup"><span data-stu-id="4abee-113">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="4abee-114">Ключ **Expression** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="4abee-114">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="4abee-115">Ключи **Ascending** или **Descending** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="4abee-115">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="4abee-116">В следующем примере объекты сортируются в порядке убывания по **LastWriteTime** и в порядке возрастания по **Name** .</span><span class="sxs-lookup"><span data-stu-id="4abee-116">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

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

<span data-ttu-id="4abee-117">Вы также можете установить блок скрипта для ключа **Expression** .</span><span class="sxs-lookup"><span data-stu-id="4abee-117">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="4abee-118">При выполнении командлета `Sort-Object` выполняется блок сценария, а его результат используется для сортировки.</span><span class="sxs-lookup"><span data-stu-id="4abee-118">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="4abee-119">В следующем примере объекты сортируются в порядке убывания в промежутке времени между **CreationTime** (временем создания файла) ​​и **LastWriteTime** (временем последней записи).</span><span class="sxs-lookup"><span data-stu-id="4abee-119">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

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

## <a name="tips"></a><span data-ttu-id="4abee-120">Советы</span><span class="sxs-lookup"><span data-stu-id="4abee-120">Tips</span></span>

<span data-ttu-id="4abee-121">Вы можете опустить имя параметра **Свойство** следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4abee-121">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="4abee-122">Кроме того, вы можете ссылаться на `Sort-Object` по его встроенному псевдониму `sort`.</span><span class="sxs-lookup"><span data-stu-id="4abee-122">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="4abee-123">Ключи в хэш-таблицах для сортировки можно сократить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4abee-123">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="4abee-124">В этом примере **e** расшифровывается **выражение** , **d** расшифровывается **по убыванию** и **a** обозначает **по возрастанию** .</span><span class="sxs-lookup"><span data-stu-id="4abee-124">In this example, the **e** stands for **Expression** , the **d** stands for **Descending** , and the **a** stands for **Ascending** .</span></span>

<span data-ttu-id="4abee-125">Чтобы улучшить читабельность, хэш-таблицы можно поместить в отдельную переменную.</span><span class="sxs-lookup"><span data-stu-id="4abee-125">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
