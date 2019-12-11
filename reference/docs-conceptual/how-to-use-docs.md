---
ms.date: 10/20/2019
keywords: powershell,командлет
title: Использование документации по PowerShell
ms.openlocfilehash: 80f72bb89b3bb82ee7c4d16b8969395f02d7d4ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72676161"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="a43c2-103">Использование документации по PowerShell</span><span class="sxs-lookup"><span data-stu-id="a43c2-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="a43c2-104">Добро пожаловать в интерактивную документацию по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c2-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="a43c2-105">Этот сайт содержит справочник по командлетам для следующих версий PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a43c2-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="a43c2-106">PowerShell 7 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a43c2-106">PowerShell 7 (preview)</span></span>
- <span data-ttu-id="a43c2-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="a43c2-107">PowerShell 6</span></span>
- <span data-ttu-id="a43c2-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a43c2-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="a43c2-109">Поиск статей и выбор версии</span><span class="sxs-lookup"><span data-stu-id="a43c2-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="a43c2-110">Существует два способа поиска содержимого в документах. Самый простой способ — использовать поле фильтра в области выбора версии.</span><span class="sxs-lookup"><span data-stu-id="a43c2-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="a43c2-111">Просто введите слово, которое есть в заголовке статьи.</span><span class="sxs-lookup"><span data-stu-id="a43c2-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="a43c2-112">На странице отображается список соответствующих статей.</span><span class="sxs-lookup"><span data-stu-id="a43c2-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="a43c2-113">Можно также выбрать вариант поиска по всему сайту из этого списка.</span><span class="sxs-lookup"><span data-stu-id="a43c2-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="a43c2-114">По умолчанию на этом сайте отображается документация по последней выпущенной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c2-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="a43c2-115">Некоторые командлеты работают по-разному в различных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c2-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="a43c2-116">Убедитесь, что вы просматриваете документацию по используемой вами версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c2-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="a43c2-117">Используйте средство выбора версий в верхней части страницы, чтобы выбрать нужную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c2-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Средство выбора](images/how-to-use-docs/version-search.gif)

<span data-ttu-id="a43c2-119">Чтобы узнать используемую версию PowerShell, проверьте значение `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="a43c2-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="a43c2-120">В следующем примере показаны выходные данные для Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="a43c2-120">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```
