---
title: Добавление возвращаемого значения для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859440"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="962cc-102">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="962cc-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="962cc-103">В этом разделе описывается добавление раздел OUTPUTS для раздела справки командлета Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="962cc-103">This section describes how to add an OUTPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="962cc-104">В разделе выходных данных перечислены классы .NET объектов, которые возвращает командлет, или передает по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="962cc-104">The OUTPUTS section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="962cc-105">Нет ограничений на число классов, которые можно добавить в раздел выходных данных.</span><span class="sxs-lookup"><span data-stu-id="962cc-105">There is no limit to the number of classes that you can add to the OUTPUTS section.</span></span> <span data-ttu-id="962cc-106">Типы возвращаемого значения командлета заключаются в \<команда: returnValues > узел, в которой каждый класс, заключенный в \<команда: returnValue > элемента.</span><span class="sxs-lookup"><span data-stu-id="962cc-106">The return types of a cmdlet are enclosed in a \<command:returnValues> node, with each class enclosed in a \<command:returnValue> element.</span></span>

<span data-ttu-id="962cc-107">Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы о том, что выходные данные.</span><span class="sxs-lookup"><span data-stu-id="962cc-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="962cc-108">Например вместо имени класса, написать «None» и Дайте краткое описание.</span><span class="sxs-lookup"><span data-stu-id="962cc-108">For example, in place of the class name, write "None" and provide a brief explanation.</span></span> <span data-ttu-id="962cc-109">Если командлет создает выходные данные по условию, используйте этот узел, чтобы объяснить условия и описание условным выводом.</span><span class="sxs-lookup"><span data-stu-id="962cc-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="962cc-110">Эта схема включает два \<maml:description > элементов в каждом \<команда: returnValue > элемента.</span><span class="sxs-lookup"><span data-stu-id="962cc-110">The schema includes two \<maml:description> elements in each \<command:returnValue> element.</span></span> <span data-ttu-id="962cc-111">Тем не менее `Get-Help` командлет отображает только содержимое \<команда: returnValue > /\<maml:description > элемента.</span><span class="sxs-lookup"><span data-stu-id="962cc-111">However, the `Get-Help` cmdlet displays only the content of the \<command:returnValue>/\<maml:description> element.</span></span>

<span data-ttu-id="962cc-112">Начиная с Windows PowerShell 3.0, `Get-Help` командлет отображает содержимое элемента \<MAML: URI > элемента.</span><span class="sxs-lookup"><span data-stu-id="962cc-112">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="962cc-113">Этот элемент позволяет направлять пользователей на разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="962cc-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="962cc-114">Следующий код XML показывает \<maml:returnValues > узла.</span><span class="sxs-lookup"><span data-stu-id="962cc-114">The following XML shows the \<maml:returnValues> node.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

<span data-ttu-id="962cc-115">Следующий код XML показывает пример использования \<maml:returnValues > узел для документирования тип выходных данных.</span><span class="sxs-lookup"><span data-stu-id="962cc-115">The following XML shows an example of using the \<maml:returnValues> node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```



