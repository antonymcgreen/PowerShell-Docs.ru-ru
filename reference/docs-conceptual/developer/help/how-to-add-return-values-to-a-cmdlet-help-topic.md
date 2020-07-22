---
title: Как добавить возвращаемые значения в раздел справки для командлета
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893362"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="f88f9-102">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="f88f9-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="f88f9-103">В этом разделе описывается добавление раздела OUTPUTs в раздел справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f88f9-103">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="f88f9-104">В разделе **Outputs** перечислены классы .NET объектов, которые командлет возвращает или передает по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f88f9-104">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="f88f9-105">Количество классов, которые можно добавить в раздел **Outputs** , не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f88f9-105">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="f88f9-106">Типы возвращаемых данных командлета заключаются в `<command:returnValues>` узел с каждым классом, заключенным в `<command:returnValue>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f88f9-106">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="f88f9-107">Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы указать, что выходные данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="f88f9-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="f88f9-108">Например, вместо имени класса напишите **None** и укажите краткое объяснение.</span><span class="sxs-lookup"><span data-stu-id="f88f9-108">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="f88f9-109">Если командлет создает выходные условия, используйте этот узел для объяснения условий и описания условного вывода.</span><span class="sxs-lookup"><span data-stu-id="f88f9-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="f88f9-110">Схема включает в себя два `<maml:description>` элемента в каждом `<command:returnValue>` элементе.</span><span class="sxs-lookup"><span data-stu-id="f88f9-110">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="f88f9-111">Однако `Get-Help` командлет отображает только содержимое `<command:returnValue>/<maml:description>` элемента.</span><span class="sxs-lookup"><span data-stu-id="f88f9-111">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="f88f9-112">Начиная с PowerShell 3,0, `Get-Help` командлет отображает содержимое `<maml:uri>` элемента.</span><span class="sxs-lookup"><span data-stu-id="f88f9-112">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="f88f9-113">Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="f88f9-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="f88f9-114">В следующем коде XML показан `<maml:returnValues>` узел.</span><span class="sxs-lookup"><span data-stu-id="f88f9-114">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="f88f9-115">В следующем коде XML показан пример использования `<maml:returnValues>` узла для документирования типа выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f88f9-115">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
