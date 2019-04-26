---
title: Поддержке справки в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: b76f45299d11dc10c8b16ed80f87c7f1fcc5ed65
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082147"
---
# <a name="supporting-online-help"></a><span data-ttu-id="5d247-102">Поддержка справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="5d247-102">Supporting Online Help</span></span>

<span data-ttu-id="5d247-103">Начиная с Windows PowerShell 3.0, существует два способа для поддержки `Get-Help` интерактивный инструмент для команд Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d247-103">Beginning in Windows PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for Windows PowerShell commands.</span></span> <span data-ttu-id="5d247-104">В этом разделе объясняется, как реализовать эту функцию для разные типы команд.</span><span class="sxs-lookup"><span data-stu-id="5d247-104">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="5d247-105">О справке</span><span class="sxs-lookup"><span data-stu-id="5d247-105">About Online Help</span></span>

<span data-ttu-id="5d247-106">Справка в Интернете всегда было важной частью работы Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d247-106">Online help has always been a vital part of Windows PowerShell.</span></span> <span data-ttu-id="5d247-107">Несмотря на то что `Get-Help` командлет отображает разделы справки в командной строке, многие пользователи предпочитают процесс чтения через Интернет, в том числе цветовое кодирование, гиперссылки и обмена идеями в содержимое сообщества и документы на основе вики-сайта.</span><span class="sxs-lookup"><span data-stu-id="5d247-107">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="5d247-108">Самое главное до появления обновляемую справку, Справка в Интернете указано самую последнюю версию файлов справки.</span><span class="sxs-lookup"><span data-stu-id="5d247-108">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="5d247-109">С появлением обновляемой справки в Windows PowerShell 3.0 Справка в Интернете по-прежнему играет важную роль.</span><span class="sxs-lookup"><span data-stu-id="5d247-109">With the advent of Updatable Help in Windows PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="5d247-110">Помимо использования элементов интерфейса пользователя гибкий справку в Интернете предоставляет справку для пользователей, не устанавливает или не может использовать обновляемую справку для загрузки разделов справки.</span><span class="sxs-lookup"><span data-stu-id="5d247-110">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="5d247-111">Как Get-Help-Online Works</span><span class="sxs-lookup"><span data-stu-id="5d247-111">How Get-Help -Online Works</span></span>

<span data-ttu-id="5d247-112">Чтобы помочь пользователям найти разделы справки для команд, `Get-Help` command имеет Online параметр, который открывает Интернет-версию раздела справки для команд в веб-браузере пользователя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5d247-112">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default Internet browser.</span></span>

<span data-ttu-id="5d247-113">Например, следующая команда открывает раздела справки в Интернете для `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="5d247-113">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="5d247-114">Для реализации `Get-Help` -Интернете, `Get-Help` командлет ищет для универсального кода ресурса (URI) для интерактивной версии раздела справки в следующих расположениях.</span><span class="sxs-lookup"><span data-stu-id="5d247-114">To implement `Get-Help` -Online, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="5d247-115">Первую ссылку в разделе "связанные ссылки" раздела справки для команды.</span><span class="sxs-lookup"><span data-stu-id="5d247-115">The first link in the Related Links section of the help topic for the command.</span></span> <span data-ttu-id="5d247-116">Раздел справки необходимо установить на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d247-116">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="5d247-117">Эта функция появилась в Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="5d247-117">This feature was introduced in Windows PowerShell 2.0.</span></span>

- <span data-ttu-id="5d247-118">Свойства HelpUri любую команду.</span><span class="sxs-lookup"><span data-stu-id="5d247-118">The HelpUri property of any command.</span></span> <span data-ttu-id="5d247-119">Свойства HelpUri доступен даже в том случае, если раздел справки для команды не установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d247-119">The HelpUri property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="5d247-120">Эта функция появилась в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5d247-120">This feature was introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="5d247-121">`Get-Help` выполняет поиск с URI в первой записи в разделе ссылки по теме перед получением значения свойства HelpUri.</span><span class="sxs-lookup"><span data-stu-id="5d247-121">`Get-Help` looks for a URI in the first entry in the Related Links section before getting the HelpUri property value.</span></span> <span data-ttu-id="5d247-122">Если значение свойства задан неверно, или был изменен, его можно переопределить, указав другое значение в первую связанную ссылку.</span><span class="sxs-lookup"><span data-stu-id="5d247-122">If the property value is incorrect or has changed, you can override it by entering a different value in the first Related Link.</span></span> <span data-ttu-id="5d247-123">Тем не менее в первую связанную ссылку работает только в том случае, если разделы справки, установленных на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d247-123">However, the first Related Link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="5d247-124">Добавление URI в первую связанную ссылку разделу справки</span><span class="sxs-lookup"><span data-stu-id="5d247-124">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="5d247-125">Можно поддерживать `Get-Help` -Online для любой команды, добавив является допустимым URI для первой записи в разделе "ссылки по теме" раздела справки на основе XML для команды.</span><span class="sxs-lookup"><span data-stu-id="5d247-125">You can support `Get-Help` -Online for any command by adding a valid URI to the first entry in the Related Links section of the XML-based help topic for the command.</span></span> <span data-ttu-id="5d247-126">Этот параметр допустим только в разделы справки на основе XML и работает только в том случае, если раздел справки установлена на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d247-126">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="5d247-127">При установке раздела справки, а URI заполняется, это значение имеет приоритет над **HelpUri** свойства команды.</span><span class="sxs-lookup"><span data-stu-id="5d247-127">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span> <span data-ttu-id="5d247-128">Сведения о формате XML разделы справки для команд, см. в разделе [Writing XML-Based разделы справки для команд](../help/writing-xml-based-help-topics-for-commands.md).</span><span class="sxs-lookup"><span data-stu-id="5d247-128">For information about XML-based help topics for commands, see [Writing XML-Based Help Topics for Commands](../help/writing-xml-based-help-topics-for-commands.md).</span></span>

<span data-ttu-id="5d247-129">Для поддержки этой возможности, URI должен присутствовать в `maml:uri` элемент под первым `maml:relatedLinks/maml:navigationLink` элемент в `maml:relatedLinks` элемент.</span><span class="sxs-lookup"><span data-stu-id="5d247-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="5d247-130">Следующий код XML показано правильное размещение URI.</span><span class="sxs-lookup"><span data-stu-id="5d247-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="5d247-131">«Интернет-версии:» текст в `maml:linkText` элемент является лучшим способом, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5d247-131">The "Online version:" text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>http://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="5d247-132">Добавление свойства HelpUri команды</span><span class="sxs-lookup"><span data-stu-id="5d247-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="5d247-133">В этом разделе показано, как добавить свойства HelpUri к командам различных типов.</span><span class="sxs-lookup"><span data-stu-id="5d247-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="5d247-134">Добавление свойства HelpUri в командлет</span><span class="sxs-lookup"><span data-stu-id="5d247-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="5d247-135">Для командлетов, написанных на C#, добавьте **HelpUri** атрибут в классе командлета.</span><span class="sxs-lookup"><span data-stu-id="5d247-135">For cmdlets written in C#, add a **HelpUri** attribute to the Cmdlet class.</span></span> <span data-ttu-id="5d247-136">Значение атрибута должно быть URI, который начинается с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="5d247-136">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="5d247-137">В следующем коде показано атрибут HelpUri `Get-History` класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d247-137">The following code shows the HelpUri attribute of the `Get-History` cmdlet class.</span></span>

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="5d247-138">Добавление свойства HelpUri в дополнительную функцию</span><span class="sxs-lookup"><span data-stu-id="5d247-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="5d247-139">Расширенные функции, добавьте **HelpUri** свойства **CmdletBinding** атрибута.</span><span class="sxs-lookup"><span data-stu-id="5d247-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="5d247-140">Значение свойства должно быть URI, который начинается с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="5d247-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="5d247-141">В следующем коде показано атрибута HelpUri функции New-календаря</span><span class="sxs-lookup"><span data-stu-id="5d247-141">The following code shows the HelpUri attribute of the New-Calendar function</span></span>

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="5d247-142">Добавление атрибута HelpUri команды CIM</span><span class="sxs-lookup"><span data-stu-id="5d247-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="5d247-143">Для команды CIM, добавьте **HelpUri** атрибут **CmdletMetadata** в файле CDXML.</span><span class="sxs-lookup"><span data-stu-id="5d247-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span> <span data-ttu-id="5d247-144">Значение атрибута должно быть URI, который начинается с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="5d247-144">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="5d247-145">В следующем коде показано атрибута HelpUri команды Start-Debug CIM</span><span class="sxs-lookup"><span data-stu-id="5d247-145">The following code shows the HelpUri attribute of the Start-Debug CIM command</span></span>

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="5d247-146">Добавление атрибута HelpUri рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="5d247-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="5d247-147">Для рабочих процессов, написанных на языке Windows PowerShell, добавьте **. ExternalHelp** comment-директива код рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5d247-147">For workflows that are written in the Windows PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="5d247-148">Значение директивы должен быть URI, который начинается с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="5d247-148">The value of the directive must be a URI that begins with "http" or "https".</span></span>

> [!NOTE]
> <span data-ttu-id="5d247-149">Свойства HelpUri не поддерживается для рабочих процессов на основе XAML в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d247-149">The HelpUri property is not supported for XAML-based workflows in Windows PowerShell.</span></span>

<span data-ttu-id="5d247-150">В следующем коде показан. Директива ExternalHelp в файл рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5d247-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```