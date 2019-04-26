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
ms.openlocfilehash: 08e05939f8aee42f2cd502a3da7a528d8460dec1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083252"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="18d67-102">Как создать файл справки командлета</span><span class="sxs-lookup"><span data-stu-id="18d67-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="18d67-103">В этом разделе описывается, как создать допустимый XML-файл, содержащий содержимое для разделы справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d67-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="18d67-104">В этом разделе рассматриваются принципы присвоения имен в файле справки, как добавить соответствующие заголовки XML и процесс добавления узлов, которые будут содержать разные разделы справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="18d67-105">Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d67-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="18d67-106">Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18d67-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="18d67-107">Создание файла справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="18d67-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="18d67-108">Создайте текстовый файл и сохраните его с использованием кодировки UTF8.</span><span class="sxs-lookup"><span data-stu-id="18d67-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="18d67-109">Имя файла должно иметь следующий формат, Windows PowerShell позволяет распознавать его как файл справки для командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-109">The file name must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. <span data-ttu-id="18d67-110">Добавьте следующие заголовки XML в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="18d67-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="18d67-111">Имейте в виду, что файл будет проверена на соответствие схеме языка моделирования нескольких агентов (MAML).</span><span class="sxs-lookup"><span data-stu-id="18d67-111">Be aware that the file will be validated against the Multi-Agent Modeling Language (MAML) schema.</span></span> <span data-ttu-id="18d67-112">В настоящее время Windows PowerShell не поддерживает любые средства для проверки файла.</span><span class="sxs-lookup"><span data-stu-id="18d67-112">Currently, Windows PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. <span data-ttu-id="18d67-113">Добавьте узел команд к файлу справки, командлет для каждого командлета в сборке.</span><span class="sxs-lookup"><span data-stu-id="18d67-113">Add a Command node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="18d67-114">Каждый узел в узле команду относится к различным разделам раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-114">Each node within the Command node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="18d67-115">Ниже перечислены XML-элемент для каждого узла, следуют описания каждого узла.</span><span class="sxs-lookup"><span data-stu-id="18d67-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |<span data-ttu-id="18d67-116">Узел</span><span class="sxs-lookup"><span data-stu-id="18d67-116">Node</span></span>|<span data-ttu-id="18d67-117">Описание</span><span class="sxs-lookup"><span data-stu-id="18d67-117">Description</span></span>|
   |----------|-----------------|
   |`<details>`|<span data-ttu-id="18d67-118">Добавляет содержимое для ИМЕНИ и краткий обзор разделов раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-119">Дополнительные сведения см. в разделе [как добавить имя командлета и краткий обзор](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:description>`|<span data-ttu-id="18d67-120">Добавляет содержимое раздела описание раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-121">Дополнительные сведения см. в разделе [Добавление подробное описание для раздела справки командлета](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>|
   |`<command:syntax>`|<span data-ttu-id="18d67-122">Добавляет содержимое в разделе "СИНТАКСИС" раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-123">Дополнительные сведения см. в разделе [как добавить синтаксис для раздела справки командлета](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:parameters>`|<span data-ttu-id="18d67-124">Добавляет содержимое раздела параметров раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-125">Дополнительные сведения см. в разделе [как добавление параметров для раздела справки командлета](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>|
   |`<command:inputTypes>`|<span data-ttu-id="18d67-126">Добавляет содержимое раздела справки командлета раздела входных данных.</span><span class="sxs-lookup"><span data-stu-id="18d67-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-127">Дополнительные сведения см. в разделе [как добавление типов входных данных для раздела справки командлета](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:returnValues>`|<span data-ttu-id="18d67-128">Добавляет содержимое для раздела справки командлета разделе выходных данных.</span><span class="sxs-lookup"><span data-stu-id="18d67-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-129">Дополнительные сведения см. в разделе [как добавить возвращаемые значения для раздела справки командлета](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:alertset>`|<span data-ttu-id="18d67-130">Добавляет содержимое в раздел "Примечания" раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-130">Adds content to the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-131">Дополнительные сведения см. в разделе [Добавление заметки для раздела справки командлета](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:examples>`|<span data-ttu-id="18d67-132">Добавляет содержимое для раздела "ПРИМЕРЫ" раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-133">Дополнительные сведения см. в разделе [как добавить примеры для раздела справки командлета](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:relatedLinks>`|<span data-ttu-id="18d67-134">Добавляет содержимое раздела ссылки по ТЕМЕ раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="18d67-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="18d67-135">Дополнительные сведения см. в разделе [как добавить ссылки по теме для раздела справки командлета](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="18d67-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>|

## <a name="example"></a><span data-ttu-id="18d67-136">Пример</span><span class="sxs-lookup"><span data-stu-id="18d67-136">Example</span></span>

 <span data-ttu-id="18d67-137">Ниже приведен пример команды узла, который включает в себя узлы для раздела справки командлета на различные разделы.</span><span class="sxs-lookup"><span data-stu-id="18d67-137">Here is an example of a Command node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
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

## <a name="see-also"></a><span data-ttu-id="18d67-138">См. также</span><span class="sxs-lookup"><span data-stu-id="18d67-138">See Also</span></span>

 [<span data-ttu-id="18d67-139">Как добавить имя командлета и краткий обзор</span><span class="sxs-lookup"><span data-stu-id="18d67-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-140">Как добавить подробное описание раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="18d67-141">Как добавить синтаксис для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-142">Как добавить параметры для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="18d67-143">Добавление типов входных данных для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-144">Как добавить возвращаемые значения для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-145">Добавление заметки для раздела справки командлета</span><span class="sxs-lookup"><span data-stu-id="18d67-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-146">Как добавить примеры для раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-147">Добавление ссылки по теме раздела справки по командлету</span><span class="sxs-lookup"><span data-stu-id="18d67-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="18d67-148">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18d67-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)