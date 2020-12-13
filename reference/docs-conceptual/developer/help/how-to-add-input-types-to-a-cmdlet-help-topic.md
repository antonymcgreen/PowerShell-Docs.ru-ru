---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить типы входных данных в раздел справки для командлета
description: Как добавить типы входных данных в раздел справки для командлета
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391108"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="d6c77-103">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="d6c77-103">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="d6c77-104">В этом разделе описывается добавление раздела **входных данных** в раздел справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6c77-104">This section describes how to add an **INPUTS** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="d6c77-105">В разделе **входных данных** перечислены классы .NET объектов, которые командлет принимает в качестве входных данных из конвейера: по значению или по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="d6c77-105">The **INPUTS** section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="d6c77-106">Количество классов, которые можно добавить в раздел **входных данных** , не ограничено.</span><span class="sxs-lookup"><span data-stu-id="d6c77-106">There is no limit to the number of classes that you can add to an **INPUTS** section.</span></span> <span data-ttu-id="d6c77-107">Входные типы заключаются в `<command:inputTypes>` узел с каждым классом, заключенным в `<command:inputType>` элемент.</span><span class="sxs-lookup"><span data-stu-id="d6c77-107">The input types are enclosed in a `<command:inputTypes>` node, with each class enclosed in a `<command:inputType>` element.</span></span>

<span data-ttu-id="d6c77-108">Схема включает в себя два `<maml:description>` элемента в каждом `<command:inputType>` элементе.</span><span class="sxs-lookup"><span data-stu-id="d6c77-108">The schema includes two `<maml:description>` elements in each `<command:inputType>` element.</span></span>
<span data-ttu-id="d6c77-109">Однако `Get-Help` командлет отображает только содержимое `<command:inputType>/<maml:description>` элемента.</span><span class="sxs-lookup"><span data-stu-id="d6c77-109">However, the `Get-Help` cmdlet displays only the content of the `<command:inputType>/<maml:description>` element.</span></span>

<span data-ttu-id="d6c77-110">Начиная с PowerShell 3,0, `Get-Help` командлет отображает содержимое `<maml:uri>` элемента.</span><span class="sxs-lookup"><span data-stu-id="d6c77-110">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="d6c77-111">Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="d6c77-111">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="d6c77-112">В следующем коде XML показан `<maml:inputTypes>` узел.</span><span class="sxs-lookup"><span data-stu-id="d6c77-112">The following XML shows the `<maml:inputTypes>` node.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

<span data-ttu-id="d6c77-113">В следующем коде XML показан пример использования `<maml:inputTypes>` узла для документирования типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="d6c77-113">The following XML shows an example of using the `<maml:inputTypes>` node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
