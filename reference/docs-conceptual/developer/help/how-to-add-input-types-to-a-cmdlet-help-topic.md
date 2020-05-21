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
ms.openlocfilehash: 58b908be3149376547b075320b021421351b881e
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557075"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="9f389-102">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="9f389-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="9f389-103">В этом разделе описано, как добавить раздел ВХОДных данных в раздел справки по командлету Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="9f389-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="9f389-104">В разделе ВХОДных данных перечислены классы .NET объектов, которые командлет принимает в качестве входных данных из конвейера: по значению или по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="9f389-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="9f389-105">Количество классов, которые можно добавить в раздел ВХОДных данных, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9f389-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="9f389-106">Входные типы заключаются в \< команду: инпуттипес> node с каждым классом, заключенным в \< команду: inputType> element.</span><span class="sxs-lookup"><span data-stu-id="9f389-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="9f389-107">Схема включает в себя два \< элемента MAML: description> в каждой \< команде: inputType> элемент.</span><span class="sxs-lookup"><span data-stu-id="9f389-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="9f389-108">Однако `Get-Help` командлет отображает только содержимое \< команды: inputType>/ \< maml: Description>).</span><span class="sxs-lookup"><span data-stu-id="9f389-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="9f389-109">Начиная с Windows PowerShell 3,0, `Get-Help` командлет отображает содержимое \< элемента MAML: URI>.</span><span class="sxs-lookup"><span data-stu-id="9f389-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="9f389-110">Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.</span><span class="sxs-lookup"><span data-stu-id="9f389-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="9f389-111">В следующем коде XML показан \< узел MAML: инпуттипес>.</span><span class="sxs-lookup"><span data-stu-id="9f389-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="9f389-112">В следующем коде XML показан пример использования \< узла MAML: инпуттипес> для документирования типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="9f389-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
