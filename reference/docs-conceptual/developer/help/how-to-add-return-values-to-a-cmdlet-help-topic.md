---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить возвращаемые значения в раздел справки для командлета
description: Как добавить возвращаемые значения в раздел справки для командлета
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389748"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="265ab-103">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="265ab-103">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="265ab-104">В этом разделе описывается добавление раздела OUTPUTs в раздел справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="265ab-104">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="265ab-105">В разделе **Outputs** перечислены классы .NET объектов, которые командлет возвращает или передает по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="265ab-105">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="265ab-106">Количество классов, которые можно добавить в раздел **Outputs** , не ограничено.</span><span class="sxs-lookup"><span data-stu-id="265ab-106">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="265ab-107">Типы возвращаемых данных командлета заключаются в `<command:returnValues>` узел с каждым классом, заключенным в `<command:returnValue>` элемент.</span><span class="sxs-lookup"><span data-stu-id="265ab-107">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="265ab-108">Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы указать, что выходные данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="265ab-108">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="265ab-109">Например, вместо имени класса напишите **None** и укажите краткое объяснение.</span><span class="sxs-lookup"><span data-stu-id="265ab-109">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="265ab-110">Если командлет создает выходные условия, используйте этот узел для объяснения условий и описания условного вывода.</span><span class="sxs-lookup"><span data-stu-id="265ab-110">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="265ab-111">Схема включает в себя два `<maml:description>` элемента в каждом `<command:returnValue>` элементе.</span><span class="sxs-lookup"><span data-stu-id="265ab-111">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="265ab-112">Однако `Get-Help` командлет отображает только содержимое `<command:returnValue>/<maml:description>` элемента.</span><span class="sxs-lookup"><span data-stu-id="265ab-112">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="265ab-113">Начиная с PowerShell 3,0, `Get-Help` командлет отображает содержимое `<maml:uri>` элемента.</span><span class="sxs-lookup"><span data-stu-id="265ab-113">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="265ab-114">Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="265ab-114">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="265ab-115">В следующем коде XML показан `<maml:returnValues>` узел.</span><span class="sxs-lookup"><span data-stu-id="265ab-115">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="265ab-116">В следующем коде XML показан пример использования `<maml:returnValues>` узла для документирования типа выходных данных.</span><span class="sxs-lookup"><span data-stu-id="265ab-116">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
