---
title: Как добавить см. также раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858350"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="35de3-102">Как добавить раздел "См. также" в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="35de3-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="35de3-103">В этом разделе объясняется, как для заполнения **см. также** раздела справки на поставщика.</span><span class="sxs-lookup"><span data-stu-id="35de3-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="35de3-104">**См. также** раздел состоит из списка разделов, которые относятся к поставщику или может помочь пользователю лучше понять и использовать поставщик.</span><span class="sxs-lookup"><span data-stu-id="35de3-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="35de3-105">Список разделов может включать справку по командлетам, справку по поставщикам и концептуальные («about») разделы справки в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35de3-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="35de3-106">Он также могут включать ссылки на книги, документ и разделы, включая версию текущего поставщика раздела справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="35de3-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="35de3-107">При ссылке на разделы, укажите URI или условие поиска в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="35de3-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="35de3-108">`Get-Help` Командлет не связать или перенаправлять любой из разделов в списке.</span><span class="sxs-lookup"><span data-stu-id="35de3-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="35de3-109">Кроме того `Online` параметр `Get-Help` командлет не работает с помощью поставщика.</span><span class="sxs-lookup"><span data-stu-id="35de3-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="35de3-110">В разделе см. в разделе также создается на основе `RelatedLinks` элемента и теги, которые она содержит.</span><span class="sxs-lookup"><span data-stu-id="35de3-110">The See Also section is created from the `RelatedLinks` element and the tags that it contains.</span></span> <span data-ttu-id="35de3-111">Следующий код XML показано, как добавлять теги.</span><span class="sxs-lookup"><span data-stu-id="35de3-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="35de3-112">Чтобы добавить разделы «См.»</span><span class="sxs-lookup"><span data-stu-id="35de3-112">To Add "SEE ALSO" Topics</span></span>

1. <span data-ttu-id="35de3-113">В *AssemblyName*.dll help.xml файл в `providerHelp` элемента, добавьте `RelatedLinks` элемент.</span><span class="sxs-lookup"><span data-stu-id="35de3-113">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="35de3-114">`RelatedLinks` Элемент должен быть последним элементом в `providerHelp` элемент.</span><span class="sxs-lookup"><span data-stu-id="35de3-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="35de3-115">Только один `RelatedLinks` элемент допустим в каждый раздел справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="35de3-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="35de3-116">Например:</span><span class="sxs-lookup"><span data-stu-id="35de3-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. <span data-ttu-id="35de3-117">Для каждого раздела в **см. также** в разделе `RelatedLinks` элемента, добавьте `navigationLink` элемент.</span><span class="sxs-lookup"><span data-stu-id="35de3-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="35de3-118">Затем, внутри каждого `navigationLink` элемента, добавьте один `linkText` элемент и один `uri` элемент.</span><span class="sxs-lookup"><span data-stu-id="35de3-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="35de3-119">Если вы не используете `uri` элемент, его можно добавить пустой элемент (\<uri / >).</span><span class="sxs-lookup"><span data-stu-id="35de3-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="35de3-120">Например:</span><span class="sxs-lookup"><span data-stu-id="35de3-120">For example:</span></span>

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

3. <span data-ttu-id="35de3-121">Введите имя раздела между `linkText` теги.</span><span class="sxs-lookup"><span data-stu-id="35de3-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="35de3-122">Если вы предоставляете URI, введите его между `uri` теги.</span><span class="sxs-lookup"><span data-stu-id="35de3-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="35de3-123">Чтобы указать Интернет-версию текущего раздела справки поставщика, между `linkText` теги, типа «Интернет-версии:» вместо имени раздела.</span><span class="sxs-lookup"><span data-stu-id="35de3-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="35de3-124">Как правило «версия в Интернете: «ссылка находится в первом разделе Список разделов также см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="35de3-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="35de3-125">Следующий пример включены три см. также разделы.</span><span class="sxs-lookup"><span data-stu-id="35de3-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="35de3-126">Первый ссылаться на Интернет-версию текущего раздела.</span><span class="sxs-lookup"><span data-stu-id="35de3-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="35de3-127">Второе — для раздела справки командлета Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35de3-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="35de3-128">Третий ссылается на другой раздел справки.</span><span class="sxs-lookup"><span data-stu-id="35de3-128">The third refers to another online topic.</span></span>

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