---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: cc5d2d799c1292f68de5fb2360fcba220c2c010b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085302"
---
# <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="502bb-102">Get-ChildItem получает параметр -Depth</span><span class="sxs-lookup"><span data-stu-id="502bb-102">Get-ChildItem has -Depth parameter</span></span>
<span data-ttu-id="502bb-103">Теперь **Get-ChildItem** имеет параметр **Depth**, используемый вместе с **–Recurse** для ограничения рекурсии:</span><span class="sxs-lookup"><span data-stu-id="502bb-103">**Get-ChildItem** now has a **–Depth** parameter you use with **–Recurse** to limit the recursion:</span></span>

<span data-ttu-id="502bb-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span><span class="sxs-lookup"><span data-stu-id="502bb-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span></span>

<span data-ttu-id="502bb-105">Каталог: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="502bb-105">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="502bb-106">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="502bb-106">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="502bb-107">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="502bb-107">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="502bb-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="502bb-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="502bb-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="502bb-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span><span class="sxs-lookup"><span data-stu-id="502bb-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span></span>

<span data-ttu-id="502bb-112">Каталог: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="502bb-112">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="502bb-113">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="502bb-113">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="502bb-114">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="502bb-114">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="502bb-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="502bb-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="502bb-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="502bb-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="502bb-118">Каталог: C:\\Users\\slee\\Downloads\\Example\\Depth0</span><span class="sxs-lookup"><span data-stu-id="502bb-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span></span>

<span data-ttu-id="502bb-119">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="502bb-119">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="502bb-120">d----- 4/14/2015 5:33 PM Depth1</span><span class="sxs-lookup"><span data-stu-id="502bb-120">d----- 4/14/2015 5:33 PM Depth1</span></span>
