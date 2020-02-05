---
title: Создание файла справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 186a8ceecea47564503dc181a76cc314033b6d3f
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76996036"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="5304c-102">Как создать файл справки командлета</span><span class="sxs-lookup"><span data-stu-id="5304c-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="5304c-103">В этом разделе описывается создание допустимого XML-файла, содержащего содержимое разделов справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5304c-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="5304c-104">В этом разделе описывается, как присвоить имя файлу справки, как добавить соответствующие заголовки XML и как добавить узлы, которые будут содержать различные разделы содержимого справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="5304c-105">Для получения полного представления файла справки откройте один из файлов длл-Хелп. XML, расположенный в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5304c-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="5304c-106">Например, файл Microsoft. PowerShell. Commands. Management. длл-Хелп. XML содержит содержимое для некоторых командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5304c-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="5304c-107">Создание файла справки по командлету</span><span class="sxs-lookup"><span data-stu-id="5304c-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="5304c-108">Создайте текстовый файл и сохраните его с помощью кодировки UTF8.</span><span class="sxs-lookup"><span data-stu-id="5304c-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="5304c-109">Имя файла должно иметь следующий формат, чтобы Windows PowerShell могла обнаружить его как файл справки командлета.</span><span class="sxs-lookup"><span data-stu-id="5304c-109">The file name must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. <span data-ttu-id="5304c-110">Добавьте следующие XML-заголовки в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="5304c-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="5304c-111">Имейте в виду, что файл будет проверен на соответствие схеме языка моделирования (MAML) с несколькими агентами.</span><span class="sxs-lookup"><span data-stu-id="5304c-111">Be aware that the file will be validated against the Multi-Agent Modeling Language (MAML) schema.</span></span> <span data-ttu-id="5304c-112">В настоящее время Windows PowerShell не предоставляет никаких средств для проверки файла.</span><span class="sxs-lookup"><span data-stu-id="5304c-112">Currently, Windows PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. <span data-ttu-id="5304c-113">Добавьте узел команды в файл справки командлета для каждого командлета в сборке.</span><span class="sxs-lookup"><span data-stu-id="5304c-113">Add a Command node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="5304c-114">Каждый узел в узле команды относится к разным разделам справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-114">Each node within the Command node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="5304c-115">В следующей таблице перечислены элементы XML для каждого узла, за которыми следуют описания каждого узла.</span><span class="sxs-lookup"><span data-stu-id="5304c-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |<span data-ttu-id="5304c-116">Узел</span><span class="sxs-lookup"><span data-stu-id="5304c-116">Node</span></span>|<span data-ttu-id="5304c-117">Description</span><span class="sxs-lookup"><span data-stu-id="5304c-117">Description</span></span>|
   |----------|-----------------|
   |`<details>`|<span data-ttu-id="5304c-118">Добавляет содержимое для разделов "имя" и "КРАТКИй Обзор" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-119">Дополнительные сведения см. в разделе [Добавление имени командлета и кратких](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)сведений.</span><span class="sxs-lookup"><span data-stu-id="5304c-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:description>`|<span data-ttu-id="5304c-120">Добавляет содержимое для раздела описания в разделе справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="5304c-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-121">Дополнительные сведения см. в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>|
   |`<command:syntax>`|<span data-ttu-id="5304c-122">Добавляет содержимое для раздела СИНТАКСИСа раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-123">Дополнительные сведения см. в [разделе Добавление синтаксиса в раздел справки по командлетам](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:parameters>`|<span data-ttu-id="5304c-124">Добавляет содержимое для раздела "Параметры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-125">Дополнительные сведения см. в [разделе Добавление параметров в раздел справки по командлетам](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>|
   |`<command:inputTypes>`|<span data-ttu-id="5304c-126">Добавляет содержимое для раздела "ВХОДные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-127">Дополнительные сведения см. в [разделе Добавление типов входных данных в раздел справки по командлетам](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:returnValues>`|<span data-ttu-id="5304c-128">Добавляет содержимое для раздела "выходные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-129">Дополнительные сведения см. в [разделе Добавление возвращаемых значений в раздел справки по командлетам](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:alertset>`|<span data-ttu-id="5304c-130">Добавляет содержимое в раздел "Примечания" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-130">Adds content to the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-131">Дополнительные сведения см. в [разделе Добавление заметок в раздел справки по командлетам](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:examples>`|<span data-ttu-id="5304c-132">Добавляет содержимое для раздела "примеры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-133">Дополнительные сведения см. в [разделе Добавление примеров в раздел справки по командлетам](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:relatedLinks>`|<span data-ttu-id="5304c-134">Добавляет содержимое для раздела "связанные ссылки" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="5304c-135">Дополнительные сведения см. в [разделе Добавление связанных ссылок в раздел справки по командлетам](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="5304c-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>|

## <a name="example"></a><span data-ttu-id="5304c-136">Пример</span><span class="sxs-lookup"><span data-stu-id="5304c-136">Example</span></span>

 <span data-ttu-id="5304c-137">Ниже приведен пример узла команды, который содержит узлы для различных разделов справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5304c-137">Here is an example of a Command node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="https://schemas.microsoft.com/maml/2004/10"
  xmlns:command="https://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="https://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a><span data-ttu-id="5304c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="5304c-138">See Also</span></span>

 [<span data-ttu-id="5304c-139">Добавление имени командлета и кратких обзоров</span><span class="sxs-lookup"><span data-stu-id="5304c-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-140">Добавление подробного описания в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="5304c-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="5304c-141">Добавление синтаксиса в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="5304c-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-142">Добавление параметров в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="5304c-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="5304c-143">Добавление типов входных данных в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5304c-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-144">Добавление возвращаемых значений в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5304c-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-145">Добавление заметок в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5304c-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-146">Добавление примеров в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5304c-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-147">Добавление связанных ссылок в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="5304c-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="5304c-148">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5304c-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)