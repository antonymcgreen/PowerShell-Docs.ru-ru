---
title: Добавление типов входных данных в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361243"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="509c2-102">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="509c2-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="509c2-103">В этом разделе описано, как добавить раздел ВХОДных данных в раздел справки по командлету Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="509c2-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="509c2-104">В разделе ВХОДных данных перечислены классы .NET объектов, которые командлет принимает в качестве входных данных из конвейера: по значению или по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="509c2-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="509c2-105">Количество классов, которые можно добавить в раздел ВХОДных данных, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="509c2-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="509c2-106">Входные типы заключаются в \<команду: Инпуттипес > Node, где каждый класс заключен в \<команду: inputType > элемент.</span><span class="sxs-lookup"><span data-stu-id="509c2-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="509c2-107">Схема включает в себя два \<MAML: Description > элементов в каждой команде \<: inputType > элемент.</span><span class="sxs-lookup"><span data-stu-id="509c2-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="509c2-108">Однако командлет `Get-Help` отображает только содержимое команды \<: inputType >/\<MAML: Description >).</span><span class="sxs-lookup"><span data-stu-id="509c2-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="509c2-109">Начиная с Windows PowerShell 3,0, командлет `Get-Help` отображает содержимое элемента > \<MAML: URI.</span><span class="sxs-lookup"><span data-stu-id="509c2-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="509c2-110">Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="509c2-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="509c2-111">В следующем коде XML показан узел \<MAML: Инпуттипес >.</span><span class="sxs-lookup"><span data-stu-id="509c2-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="509c2-112">В следующем коде XML показан пример использования узла \<MAML: Инпуттипес > для документирования типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="509c2-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

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