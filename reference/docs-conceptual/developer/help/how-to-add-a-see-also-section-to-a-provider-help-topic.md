---
title: Добавление раздела "см. также" в раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367843"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="7d7ca-102">Как добавить раздел "См. также" в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="7d7ca-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="7d7ca-103">В этом разделе объясняется, как заполнить раздел " **см. также** " в разделе справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="7d7ca-104">Раздел **см. также** содержит список разделов, связанных с поставщиком, или может помочь пользователю лучше понять и использовать поставщик.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="7d7ca-105">Список разделов может включать справку по командлетам, справку поставщика и концептуальные разделы справки в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="7d7ca-106">Он также может включать ссылки на книги, документы и статьи в Интернете, включая интерактивную версию текущего раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="7d7ca-107">При ссылке на разделы в Интернете укажите универсальный код ресурса (URI) или условие поиска в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="7d7ca-108">Командлет `Get-Help` не выполняет связывание или перенаправление к любому из разделов в списке.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="7d7ca-109">Кроме того, параметр `Online` командлета `Get-Help` не работает с справкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="7d7ca-110">Раздел см. также создается из элемента `RelatedLinks` и содержащихся в нем тегов.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-110">The See Also section is created from the `RelatedLinks` element and the tags that it contains.</span></span> <span data-ttu-id="7d7ca-111">В следующем коде XML показано, как добавить теги.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="7d7ca-112">Добавление разделов «см. также»</span><span class="sxs-lookup"><span data-stu-id="7d7ca-112">To Add "SEE ALSO" Topics</span></span>

1. <span data-ttu-id="7d7ca-113">В файле *AssemblyName*. длл-Хелп. XML в элементе `providerHelp` добавьте элемент `RelatedLinks`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-113">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="7d7ca-114">Элемент `RelatedLinks` должен быть последним элементом в элементе `providerHelp`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="7d7ca-115">В каждом разделе справки по поставщику допускается только один элемент `RelatedLinks`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="7d7ca-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="7d7ca-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. <span data-ttu-id="7d7ca-117">Для каждого раздела в разделе " **см. также** " в элементе `RelatedLinks` добавьте элемент `navigationLink`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="7d7ca-118">Затем в каждом элементе `navigationLink` добавьте один элемент `linkText` и один элемент `uri`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="7d7ca-119">Если элемент `uri` не используется, его можно добавить как пустой элемент (\<uri/>).</span><span class="sxs-lookup"><span data-stu-id="7d7ca-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="7d7ca-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="7d7ca-120">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> </linkText>
                <uri> </uri>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

3. <span data-ttu-id="7d7ca-121">Введите имя раздела между тегами `linkText`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="7d7ca-122">Если вы предоставляете универсальный код ресурса (URI), введите его между тегами `uri`.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="7d7ca-123">Чтобы указать Интернет-версию текущего раздела справки поставщика, между тегами `linkText` введите "Online Version:" вместо имени раздела.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="7d7ca-124">Как правило, ссылка "Оперативная версия:" является первой темой в списке "см. также".</span><span class="sxs-lookup"><span data-stu-id="7d7ca-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="7d7ca-125">В следующем примере показано три раздела см. также:</span><span class="sxs-lookup"><span data-stu-id="7d7ca-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="7d7ca-126">Первый раздел относится к интерактивной версии текущего раздела.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="7d7ca-127">Второй — раздел справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="7d7ca-128">Третья статья относится к другому разделу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7d7ca-128">The third refers to another online topic.</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> Online version: </linkText>
                <uri>http://www.fabrikam.com/help/myFunction.htm</uri>
            </navigationLink>
            <navigationLink>
                <linkText> about_functions </linkText>
                <uri/>
            </navigationLink>
            <navigationLink>
                <linkText> Windows PowerShell Getting Started Guide </linkText>
                <uri>http://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```