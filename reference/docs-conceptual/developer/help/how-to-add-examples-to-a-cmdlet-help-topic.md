---
title: Добавление примеров в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368113"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="cc07f-102">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="cc07f-102">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="cc07f-103">Что нужно узнать о примерах в справке по командлетам</span><span class="sxs-lookup"><span data-stu-id="cc07f-103">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="cc07f-104">Список всех имен параметров в команде, даже если имена параметров являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="cc07f-104">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="cc07f-105">Это позволяет пользователю легко интерпретировать команду.</span><span class="sxs-lookup"><span data-stu-id="cc07f-105">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="cc07f-106">Не рекомендуется использовать псевдонимы и имена частичных параметров, даже если они работают в Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="cc07f-106">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="cc07f-107">В описании примера объясните рациональное построение команды.</span><span class="sxs-lookup"><span data-stu-id="cc07f-107">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="cc07f-108">Объясните, почему вы выбрали определенные параметры и значения и как использовать переменные.</span><span class="sxs-lookup"><span data-stu-id="cc07f-108">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="cc07f-109">Если команда использует выражения, объясните их подробно.</span><span class="sxs-lookup"><span data-stu-id="cc07f-109">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="cc07f-110">Если команда использует свойства и методы объектов, особенно свойства, которые не отображаются в отображении по умолчанию, используйте пример как возможность, чтобы сообщить пользователю об объекте.</span><span class="sxs-lookup"><span data-stu-id="cc07f-110">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="cc07f-111">Представления справки, в которых отображаются примеры</span><span class="sxs-lookup"><span data-stu-id="cc07f-111">Help Views that Display Examples</span></span>

<span data-ttu-id="cc07f-112">Примеры отображаются только в подробных и полных представлениях справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="cc07f-112">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="cc07f-113">Добавление узла примеров</span><span class="sxs-lookup"><span data-stu-id="cc07f-113">Adding an Examples Node</span></span>

<span data-ttu-id="cc07f-114">В следующем коде XML показано, как добавить узел примеров, содержащий один узел примера.</span><span class="sxs-lookup"><span data-stu-id="cc07f-114">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="cc07f-115">Добавьте дополнительные примеры узлов для каждого из примеров, которые необходимо включить в раздел.</span><span class="sxs-lookup"><span data-stu-id="cc07f-115">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="cc07f-116">Добавление примера заголовка</span><span class="sxs-lookup"><span data-stu-id="cc07f-116">Adding an Example Title</span></span>

<span data-ttu-id="cc07f-117">В следующем коде XML показано, как добавить заголовок для примера.</span><span class="sxs-lookup"><span data-stu-id="cc07f-117">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="cc07f-118">Заголовок используется для задания примера отдельно от других примеров.</span><span class="sxs-lookup"><span data-stu-id="cc07f-118">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="cc07f-119">® Windows PowerShell использует стандартный заголовок, который содержит последовательный пример.</span><span class="sxs-lookup"><span data-stu-id="cc07f-119">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="cc07f-120">Добавление предшествующих символов</span><span class="sxs-lookup"><span data-stu-id="cc07f-120">Adding Preceding Characters</span></span>

<span data-ttu-id="cc07f-121">В следующем коде XML показано, как добавить символы, такие как Командная строка Windows PowerShell, которые отображаются непосредственно перед командой example (без каких-либо промежуточных пробелов).</span><span class="sxs-lookup"><span data-stu-id="cc07f-121">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="cc07f-122">® Windows PowerShell использует командную строку Windows PowerShell: К:\ПС >.</span><span class="sxs-lookup"><span data-stu-id="cc07f-122">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

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

## <a name="adding-the-command"></a><span data-ttu-id="cc07f-123">Добавление команды</span><span class="sxs-lookup"><span data-stu-id="cc07f-123">Adding the Command</span></span>

<span data-ttu-id="cc07f-124">В следующем коде XML показано, как добавить фактическую команду в примере.</span><span class="sxs-lookup"><span data-stu-id="cc07f-124">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="cc07f-125">При добавлении команды введите полное имя (не используйте псевдоним) командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="cc07f-125">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="cc07f-126">Кроме того, при возможности используйте символы нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="cc07f-126">Also, use lowercase characters whenever possible.</span></span>

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

## <a name="adding-a-description"></a><span data-ttu-id="cc07f-127">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="cc07f-127">Adding a Description</span></span>

<span data-ttu-id="cc07f-128">В следующем коде XML показано, как добавить описание для примера.</span><span class="sxs-lookup"><span data-stu-id="cc07f-128">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="cc07f-129">® Windows PowerShell использует один набор тегов \<maml: para > для описания, хотя можно использовать несколько тегов \<maml: para >.</span><span class="sxs-lookup"><span data-stu-id="cc07f-129">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

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

## <a name="adding-example-output"></a><span data-ttu-id="cc07f-130">Добавление выходных данных примера</span><span class="sxs-lookup"><span data-stu-id="cc07f-130">Adding Example Output</span></span>

<span data-ttu-id="cc07f-131">В следующем коде XML показано, как добавить выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="cc07f-131">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="cc07f-132">Сведения о результатах команды являются необязательными, но в некоторых случаях полезно продемонстрировать результат использования определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="cc07f-132">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="cc07f-133">® Windows PowerShell использует два набора пустых тегов \<maml: para >, чтобы отделить выходные данные команды от команды.</span><span class="sxs-lookup"><span data-stu-id="cc07f-133">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

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