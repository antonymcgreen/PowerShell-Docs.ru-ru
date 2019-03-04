---
title: Как добавить примеры для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: 5e8d1df6b423bfd2cd6b0a64a8875dea9c3fb4ef
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857320"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="5b2cc-102">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="5b2cc-102">How to Add Examples to a Cmdlet Help Topic</span></span>

- [<span data-ttu-id="5b2cc-103">Что нужно знать о примерах справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5b2cc-103">Things to Know about Examples in Cmdlet Help</span></span>](#Things-to-Know-about-Examples-in-Cmdlet-Help)

- [<span data-ttu-id="5b2cc-104">Справка представлений, которые отображают примеры</span><span class="sxs-lookup"><span data-stu-id="5b2cc-104">Help Views that Display Examples</span></span>](#Help-Views-that-Display-Examples)

- [<span data-ttu-id="5b2cc-105">Добавление узла примеры</span><span class="sxs-lookup"><span data-stu-id="5b2cc-105">Adding an Examples Node</span></span>](#Adding-an-Examples-Node)

- [<span data-ttu-id="5b2cc-106">Добавление предшествующих символов</span><span class="sxs-lookup"><span data-stu-id="5b2cc-106">Adding Preceding Characters</span></span>](#Adding-Preceding-Characters)

- [<span data-ttu-id="5b2cc-107">Добавление команды</span><span class="sxs-lookup"><span data-stu-id="5b2cc-107">Adding the Command</span></span>](#Adding-the-Command)

- [<span data-ttu-id="5b2cc-108">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="5b2cc-108">Adding a Description</span></span>](#Adding-a-Description)

- [<span data-ttu-id="5b2cc-109">Добавление выходных данных примера</span><span class="sxs-lookup"><span data-stu-id="5b2cc-109">Adding Example Output</span></span>](#Adding-Example-Output)

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="5b2cc-110">Что нужно знать о примерах справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5b2cc-110">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="5b2cc-111">Список всех имен параметров в команде, даже в том случае, если имена параметров являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-111">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="5b2cc-112">Это позволяет пользователю легко интерпретировать команду.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-112">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="5b2cc-113">Избегайте псевдонимы и частичные имена параметров, несмотря на то, что они работают в Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-113">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="5b2cc-114">В описании примера объясните rational для создания команды.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-114">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="5b2cc-115">Объясните предложениями определенного параметры и значения, и как использовать переменные.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-115">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="5b2cc-116">Если команда использует выражения, их также подробно объясняется.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-116">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="5b2cc-117">Если команда использует свойства и методы объектов, особенно те свойства, которые не отображаются в представление по умолчанию, используйте приведенный пример, как возможность сообщить пользователю об объекте.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-117">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="5b2cc-118">Справка представлений, которые отображают примеры</span><span class="sxs-lookup"><span data-stu-id="5b2cc-118">Help Views that Display Examples</span></span>

<span data-ttu-id="5b2cc-119">Примеры приведены только в подробный и полного представления справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-119">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="5b2cc-120">Добавление узла примеры</span><span class="sxs-lookup"><span data-stu-id="5b2cc-120">Adding an Examples Node</span></span>

<span data-ttu-id="5b2cc-121">Следующий код XML показано, как добавить узел примерах, содержит один узел пример.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-121">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="5b2cc-122">Добавьте дополнительный пример узлы для каждого примеры, которые вы хотите включить в разделе.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-122">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="5b2cc-123">Добавление название примера</span><span class="sxs-lookup"><span data-stu-id="5b2cc-123">Adding an Example Title</span></span>

<span data-ttu-id="5b2cc-124">Следующий код XML показано, как добавить заголовок для примера.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-124">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="5b2cc-125">Заголовок, используемый для задания в примере, помимо других примеров.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-125">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="5b2cc-126">Windows PowerShell® использует стандартный заголовок, который включает несколько последовательном примере.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-126">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="5b2cc-127">Добавление предшествующих символов</span><span class="sxs-lookup"><span data-stu-id="5b2cc-127">Adding Preceding Characters</span></span>

<span data-ttu-id="5b2cc-128">Следующий код XML показано, как добавить символы, такие как командной строке Windows PowerShell, которые отображаются непосредственно перед пример команды (без пробелов промежуточных).</span><span class="sxs-lookup"><span data-stu-id="5b2cc-128">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="5b2cc-129">Windows PowerShell® используется в командной строке Windows PowerShell: C:\PS>.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-129">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a><span data-ttu-id="5b2cc-130">Добавление команды</span><span class="sxs-lookup"><span data-stu-id="5b2cc-130">Adding the Command</span></span>

<span data-ttu-id="5b2cc-131">Следующий код XML показано, как добавить команду фактическое примера.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-131">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="5b2cc-132">При добавлении команды, введите полное имя (не используйте псевдоним) командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-132">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="5b2cc-133">Кроме того можно используйте строчные буквы, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-133">Also, use lowercase characters whenever possible.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a><span data-ttu-id="5b2cc-134">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="5b2cc-134">Adding a Description</span></span>

<span data-ttu-id="5b2cc-135">Следующий код XML показано, как добавить описание для примера.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-135">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="5b2cc-136">Windows PowerShell® использует один набор \<MAML: para > теги для описания, даже если несколько \<MAML: para > теги можно использовать.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-136">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a><span data-ttu-id="5b2cc-137">Добавление выходных данных примера</span><span class="sxs-lookup"><span data-stu-id="5b2cc-137">Adding Example Output</span></span>

<span data-ttu-id="5b2cc-138">Следующий XML-код демонстрирует добавление выходных данных команды.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-138">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="5b2cc-139">Сведения о командах результатов является необязательным, но в некоторых случаях полезно демонстрации эффекта с помощью определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-139">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="5b2cc-140">Windows PowerShell® использует два набора пустым \<MAML: para > теги для разделения выходных данных команды из команды.</span><span class="sxs-lookup"><span data-stu-id="5b2cc-140">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```