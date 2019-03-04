---
title: Добавление типов входных данных для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860810"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="130c2-102">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="130c2-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="130c2-103">В этом разделе описывается добавление раздел входных данных для раздела справки командлета Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="130c2-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="130c2-104">В разделе входных данных перечислены классы .NET объектов, командлет принимает в качестве входных данных из конвейера, по значению или по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="130c2-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="130c2-105">Нет ограничений на число классов, которые можно добавить раздел входных данных.</span><span class="sxs-lookup"><span data-stu-id="130c2-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="130c2-106">Типы входных данных заключаются в \<команда: inputTypes > узел, в которой каждый класс, заключенный в \<команда: inputType > элемента.</span><span class="sxs-lookup"><span data-stu-id="130c2-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="130c2-107">Эта схема включает два \<maml:description > элементов в каждом \<команда: inputType > элемента.</span><span class="sxs-lookup"><span data-stu-id="130c2-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="130c2-108">Тем не менее `Get-Help` командлет отображает только содержимое \<команда: inputType > /\<maml:description >) элемента.</span><span class="sxs-lookup"><span data-stu-id="130c2-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="130c2-109">Начиная с Windows PowerShell 3.0, `Get-Help` командлет отображает содержимое элемента \<MAML: URI > элемента.</span><span class="sxs-lookup"><span data-stu-id="130c2-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="130c2-110">Этот элемент позволяет направлять пользователей на разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="130c2-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="130c2-111">Следующий код XML показывает \<maml:inputTypes > узла.</span><span class="sxs-lookup"><span data-stu-id="130c2-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="130c2-112">Следующий код XML показывает пример использования \<maml:inputTypes > узел для документирования тип входных данных.</span><span class="sxs-lookup"><span data-stu-id="130c2-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```