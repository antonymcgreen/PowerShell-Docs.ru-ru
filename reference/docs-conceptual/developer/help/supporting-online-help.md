---
title: Поддержка справки в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: de25b099e61f82891daff87c4c73bb8cad9111a4
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811403"
---
# <a name="supporting-online-help"></a><span data-ttu-id="9a5c3-102">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="9a5c3-102">Supporting Online Help</span></span>

<span data-ttu-id="9a5c3-103">Начиная с Windows PowerShell 3,0, существует два способа поддержки `Get-Help` функции Online для команд Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-103">Beginning in Windows PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for Windows PowerShell commands.</span></span> <span data-ttu-id="9a5c3-104">В этом разделе объясняется, как реализовать эту функцию для различных типов команд.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-104">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="9a5c3-105">Справка в Интернете</span><span class="sxs-lookup"><span data-stu-id="9a5c3-105">About Online Help</span></span>

<span data-ttu-id="9a5c3-106">Интерактивная справка всегда была важной частью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-106">Online help has always been a vital part of Windows PowerShell.</span></span> <span data-ttu-id="9a5c3-107">Хотя `Get-Help` командлет отображает разделы справки в командной строке, многие пользователи предпочитают работать в Интернете, включая выделение цветом, гиперссылки и общие идеи в содержимом сообщества и на вики-документах.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-107">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="9a5c3-108">Самое важное, прежде чем поступать с обновляемой справкой, Справка в Интернете предоставляла самые последние версии файлов справки.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-108">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="9a5c3-109">С появлением обновляемой справки в Windows PowerShell 3,0 интерактивная справка по-прежнему играет важную роль.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-109">With the advent of Updatable Help in Windows PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="9a5c3-110">В дополнение к гибкому интерфейсу пользователя Справка в Интернете предоставляет пользователям, которые не могут использовать обновляемую справку для загрузки разделов справки.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-110">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="9a5c3-111">Как Get-Help-Online работает</span><span class="sxs-lookup"><span data-stu-id="9a5c3-111">How Get-Help -Online Works</span></span>

<span data-ttu-id="9a5c3-112">Чтобы помочь пользователям найти разделы справки в Интернете для команд, у `Get-Help` команды есть параметр в сети, который открывает интерактивную версию раздела справки для команды в браузере по умолчанию пользователя в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-112">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default Internet browser.</span></span>

<span data-ttu-id="9a5c3-113">Например, следующая команда открывает раздел справки в Интернете для `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-113">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="9a5c3-114">Чтобы реализовать `Get-Help` -Online, `Get-Help` командлет ищет универсальный код ресурса (URI) для раздела справки по интерактивной версии в следующих расположениях.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-114">To implement `Get-Help` -Online, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="9a5c3-115">Первая ссылка в разделе "связанные ссылки" раздела справки для команды.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-115">The first link in the Related Links section of the help topic for the command.</span></span> <span data-ttu-id="9a5c3-116">Раздел справки должен быть установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-116">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="9a5c3-117">Эта функция появилась в Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-117">This feature was introduced in Windows PowerShell 2.0.</span></span>

- <span data-ttu-id="9a5c3-118">Свойство HelpUri любой команды.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-118">The HelpUri property of any command.</span></span> <span data-ttu-id="9a5c3-119">Свойство HelpUri доступно, даже если раздел справки для команды не установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-119">The HelpUri property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="9a5c3-120">Эта функция появилась в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-120">This feature was introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="9a5c3-121">`Get-Help`ищет URI в первой записи в разделе связанных ссылок перед получением значения свойства HelpUri.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-121">`Get-Help` looks for a URI in the first entry in the Related Links section before getting the HelpUri property value.</span></span> <span data-ttu-id="9a5c3-122">Если значение свойства неверно или изменилось, его можно переопределить, введя другое значение в первой связанной ссылке.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-122">If the property value is incorrect or has changed, you can override it by entering a different value in the first Related Link.</span></span> <span data-ttu-id="9a5c3-123">Однако первая связанная ссылка работает только в том случае, если разделы справки установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-123">However, the first Related Link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="9a5c3-124">Добавление URI в первую связанную ссылку раздела справки по команде</span><span class="sxs-lookup"><span data-stu-id="9a5c3-124">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="9a5c3-125">Для `Get-Help` любой команды можно использовать режим "в сети", добавив допустимый URI в первую запись в разделе "связанные ссылки" раздела справки на основе XML для команды.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-125">You can support `Get-Help` -Online for any command by adding a valid URI to the first entry in the Related Links section of the XML-based help topic for the command.</span></span> <span data-ttu-id="9a5c3-126">Этот параметр допустим только в разделах справки на основе XML и работает только при установке раздела справки на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-126">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="9a5c3-127">Если раздел справки установлен и URI заполнен, это значение имеет приоритет над свойством **HelpUri** команды.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-127">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="9a5c3-128">Для поддержки этой функции URI должен присутствовать в элементе, `maml:uri` расположенном под первым `maml:relatedLinks/maml:navigationLink` элементом в `maml:relatedLinks` элементе.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-128">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="9a5c3-129">В следующем XML-коде показано правильное размещение URI.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-129">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="9a5c3-130">Рекомендуется использовать текст "онлайн Version:" в `maml:linkText` элементе, но он не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-130">The "Online version:" text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="9a5c3-131">Добавление свойства HelpUri в команду</span><span class="sxs-lookup"><span data-stu-id="9a5c3-131">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="9a5c3-132">В этом разделе показано, как добавить свойство HelpUri в команды различных типов.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-132">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="9a5c3-133">Добавление свойства HelpUri в командлет</span><span class="sxs-lookup"><span data-stu-id="9a5c3-133">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="9a5c3-134">Для командлетов, написанных на языке C#, добавьте атрибут **HelpUri** в класс командлета.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-134">For cmdlets written in C#, add a **HelpUri** attribute to the Cmdlet class.</span></span> <span data-ttu-id="9a5c3-135">Значение атрибута должно быть URI, начинающимся с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9a5c3-135">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="9a5c3-136">В следующем коде показан атрибут HelpUri `Get-History` класса командлета.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-136">The following code shows the HelpUri attribute of the `Get-History` cmdlet class.</span></span>

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="9a5c3-137">Добавление свойства HelpUri в расширенную функцию</span><span class="sxs-lookup"><span data-stu-id="9a5c3-137">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="9a5c3-138">Для расширенных функций добавьте свойство **HelpUri** в атрибут **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="9a5c3-138">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="9a5c3-139">Значение свойства должно быть URI, начинающимся с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9a5c3-139">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="9a5c3-140">В следующем коде показан атрибут HelpUri функции New-Calendar.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-140">The following code shows the HelpUri attribute of the New-Calendar function</span></span>

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="9a5c3-141">Добавление атрибута HelpUri в команду CIM</span><span class="sxs-lookup"><span data-stu-id="9a5c3-141">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="9a5c3-142">Для команд CIM добавьте атрибут **HelpUri** в элемент **КМДЛЕТМЕТАДАТА** в файле CDXML.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-142">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span> <span data-ttu-id="9a5c3-143">Значение атрибута должно быть URI, начинающимся с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9a5c3-143">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="9a5c3-144">В следующем коде показан атрибут HelpUri команды CIM Start-Debug.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-144">The following code shows the HelpUri attribute of the Start-Debug CIM command</span></span>

```
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="9a5c3-145">Добавление атрибута HelpUri в рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="9a5c3-145">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="9a5c3-146">Для рабочих процессов, написанных на языке Windows PowerShell, добавьте \*\*. \*\*Директива комментария екстерналхелп к коду рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-146">For workflows that are written in the Windows PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="9a5c3-147">Значение директивы должно быть универсальным кодом ресурса (URI), начинающимся с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9a5c3-147">The value of the directive must be a URI that begins with "http" or "https".</span></span>

> [!NOTE]
> <span data-ttu-id="9a5c3-148">Свойство HelpUri не поддерживается для рабочих процессов на основе XAML в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-148">The HelpUri property is not supported for XAML-based workflows in Windows PowerShell.</span></span>

<span data-ttu-id="9a5c3-149">В следующем коде показан объект. Директива Екстерналхелп в файле рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9a5c3-149">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
