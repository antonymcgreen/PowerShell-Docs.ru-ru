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
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855116"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="61907-102">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="61907-102">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="61907-103">Что нужно знать о примерах справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="61907-103">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="61907-104">Список всех имен параметров в команде, даже в том случае, если имена параметров являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="61907-104">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="61907-105">Это позволяет пользователю легко интерпретировать команду.</span><span class="sxs-lookup"><span data-stu-id="61907-105">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="61907-106">Избегайте псевдонимы и частичные имена параметров, несмотря на то, что они работают в Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="61907-106">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="61907-107">В описании примера объясните rational для создания команды.</span><span class="sxs-lookup"><span data-stu-id="61907-107">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="61907-108">Объясните предложениями определенного параметры и значения, и как использовать переменные.</span><span class="sxs-lookup"><span data-stu-id="61907-108">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="61907-109">Если команда использует выражения, их также подробно объясняется.</span><span class="sxs-lookup"><span data-stu-id="61907-109">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="61907-110">Если команда использует свойства и методы объектов, особенно те свойства, которые не отображаются в представление по умолчанию, используйте приведенный пример, как возможность сообщить пользователю об объекте.</span><span class="sxs-lookup"><span data-stu-id="61907-110">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="61907-111">Справка представлений, которые отображают примеры</span><span class="sxs-lookup"><span data-stu-id="61907-111">Help Views that Display Examples</span></span>

<span data-ttu-id="61907-112">Примеры приведены только в подробный и полного представления справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="61907-112">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="61907-113">Добавление узла примеры</span><span class="sxs-lookup"><span data-stu-id="61907-113">Adding an Examples Node</span></span>

<span data-ttu-id="61907-114">Следующий код XML показано, как добавить узел примерах, содержит один узел пример.</span><span class="sxs-lookup"><span data-stu-id="61907-114">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="61907-115">Добавьте дополнительный пример узлы для каждого примеры, которые вы хотите включить в разделе.</span><span class="sxs-lookup"><span data-stu-id="61907-115">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="61907-116">Добавление название примера</span><span class="sxs-lookup"><span data-stu-id="61907-116">Adding an Example Title</span></span>

<span data-ttu-id="61907-117">Следующий код XML показано, как добавить заголовок для примера.</span><span class="sxs-lookup"><span data-stu-id="61907-117">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="61907-118">Заголовок, используемый для задания в примере, помимо других примеров.</span><span class="sxs-lookup"><span data-stu-id="61907-118">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="61907-119">Windows PowerShell® использует стандартный заголовок, который включает несколько последовательном примере.</span><span class="sxs-lookup"><span data-stu-id="61907-119">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="61907-120">Добавление предшествующих символов</span><span class="sxs-lookup"><span data-stu-id="61907-120">Adding Preceding Characters</span></span>

<span data-ttu-id="61907-121">Следующий код XML показано, как добавить символы, такие как командной строке Windows PowerShell, которые отображаются непосредственно перед пример команды (без пробелов промежуточных).</span><span class="sxs-lookup"><span data-stu-id="61907-121">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="61907-122">Windows PowerShell® используется в командной строке Windows PowerShell: C:\PS>.</span><span class="sxs-lookup"><span data-stu-id="61907-122">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

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

## <a name="adding-the-command"></a><span data-ttu-id="61907-123">Добавление команды</span><span class="sxs-lookup"><span data-stu-id="61907-123">Adding the Command</span></span>

<span data-ttu-id="61907-124">Следующий код XML показано, как добавить команду фактическое примера.</span><span class="sxs-lookup"><span data-stu-id="61907-124">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="61907-125">При добавлении команды, введите полное имя (не используйте псевдоним) командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="61907-125">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="61907-126">Кроме того можно используйте строчные буквы, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="61907-126">Also, use lowercase characters whenever possible.</span></span>

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

## <a name="adding-a-description"></a><span data-ttu-id="61907-127">Добавление описания</span><span class="sxs-lookup"><span data-stu-id="61907-127">Adding a Description</span></span>

<span data-ttu-id="61907-128">Следующий код XML показано, как добавить описание для примера.</span><span class="sxs-lookup"><span data-stu-id="61907-128">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="61907-129">Windows PowerShell® использует один набор \<MAML: para > теги для описания, даже если несколько \<MAML: para > теги можно использовать.</span><span class="sxs-lookup"><span data-stu-id="61907-129">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

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

## <a name="adding-example-output"></a><span data-ttu-id="61907-130">Добавление выходных данных примера</span><span class="sxs-lookup"><span data-stu-id="61907-130">Adding Example Output</span></span>

<span data-ttu-id="61907-131">Следующий XML-код демонстрирует добавление выходных данных команды.</span><span class="sxs-lookup"><span data-stu-id="61907-131">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="61907-132">Сведения о командах результатов является необязательным, но в некоторых случаях полезно демонстрации эффекта с помощью определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="61907-132">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="61907-133">Windows PowerShell® использует два набора пустым \<MAML: para > теги для разделения выходных данных команды из команды.</span><span class="sxs-lookup"><span data-stu-id="61907-133">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

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