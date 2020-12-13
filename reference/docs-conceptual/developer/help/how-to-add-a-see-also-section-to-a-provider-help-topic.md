---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить раздел "См. также" в раздел справки для поставщика
description: Как добавить раздел "См. также" в раздел справки для поставщика
ms.openlocfilehash: df0b14ba84e04baf404081944ef62ef6745d74b2
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667663"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="01ddf-103">Как добавить раздел "См. также" в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="01ddf-103">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="01ddf-104">В этом разделе объясняется, как заполнить раздел " **см. также** " в разделе справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="01ddf-104">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="01ddf-105">Раздел **см. также** содержит список разделов, связанных с поставщиком, или может помочь пользователю лучше понять и использовать поставщик.</span><span class="sxs-lookup"><span data-stu-id="01ddf-105">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="01ddf-106">Список разделов может включать справку по командлетам, справку поставщика и концептуальные разделы справки в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01ddf-106">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="01ddf-107">Он также может включать ссылки на книги, документы и статьи в Интернете, включая интерактивную версию текущего раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="01ddf-107">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="01ddf-108">При ссылке на разделы в Интернете укажите универсальный код ресурса (URI) или условие поиска в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="01ddf-108">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="01ddf-109">`Get-Help`Командлет не выполняет связывание или перенаправление к любому из разделов в списке.</span><span class="sxs-lookup"><span data-stu-id="01ddf-109">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="01ddf-110">Кроме того, `Online` параметр `Get-Help` командлета не работает со справкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="01ddf-110">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="01ddf-111">Раздел **см. также** создается на основе `RelatedLinks` элемента и содержащихся в нем тегов.</span><span class="sxs-lookup"><span data-stu-id="01ddf-111">The **See Also** section is created from the `RelatedLinks` element and the tags that it contains.</span></span>
<span data-ttu-id="01ddf-112">В следующем коде XML показано, как добавить теги.</span><span class="sxs-lookup"><span data-stu-id="01ddf-112">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="01ddf-113">Для добавления см. также разделы</span><span class="sxs-lookup"><span data-stu-id="01ddf-113">To Add SEE ALSO Topics</span></span>

1. <span data-ttu-id="01ddf-114">В `<AssemblyName>.dll-help.xml` файле в `providerHelp` элементе добавьте `RelatedLinks` элемент.</span><span class="sxs-lookup"><span data-stu-id="01ddf-114">In the `<AssemblyName>.dll-help.xml` file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="01ddf-115">`RelatedLinks`Элемент должен быть последним элементом в `providerHelp` элементе.</span><span class="sxs-lookup"><span data-stu-id="01ddf-115">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="01ddf-116">`RelatedLinks`В каждом разделе справки по поставщику допускается только один элемент.</span><span class="sxs-lookup"><span data-stu-id="01ddf-116">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="01ddf-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="01ddf-117">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

1. <span data-ttu-id="01ddf-118">Для каждого раздела в разделе " **см. также** " в `RelatedLinks` элементе добавьте `navigationLink` элемент.</span><span class="sxs-lookup"><span data-stu-id="01ddf-118">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="01ddf-119">Затем в каждом `navigationLink` элементе добавьте один `linkText` элемент и один `uri` элемент.</span><span class="sxs-lookup"><span data-stu-id="01ddf-119">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="01ddf-120">Если элемент не используется `uri` , его можно добавить как пустой элемент ( \<uri/> ).</span><span class="sxs-lookup"><span data-stu-id="01ddf-120">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="01ddf-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="01ddf-121">For example:</span></span>

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

1. <span data-ttu-id="01ddf-122">Введите имя раздела между `linkText` тегами.</span><span class="sxs-lookup"><span data-stu-id="01ddf-122">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="01ddf-123">Если вы предоставляете универсальный код ресурса (URI), введите его между `uri` тегами.</span><span class="sxs-lookup"><span data-stu-id="01ddf-123">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="01ddf-124">Чтобы указать Интернет-версию текущего раздела справки поставщика, между `linkText` тегами введите "Оперативная версия:", а не имя раздела.</span><span class="sxs-lookup"><span data-stu-id="01ddf-124">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="01ddf-125">Как правило, ссылка "Оперативная версия:" является первой темой в списке "см. также".</span><span class="sxs-lookup"><span data-stu-id="01ddf-125">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="01ddf-126">В следующем примере показано три раздела см. также:</span><span class="sxs-lookup"><span data-stu-id="01ddf-126">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="01ddf-127">Первый раздел относится к интерактивной версии текущего раздела.</span><span class="sxs-lookup"><span data-stu-id="01ddf-127">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="01ddf-128">Второй — раздел справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01ddf-128">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="01ddf-129">Третья статья относится к другому разделу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="01ddf-129">The third refers to another online topic.</span></span>

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
                <uri>https://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```
