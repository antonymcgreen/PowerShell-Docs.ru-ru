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
ms.openlocfilehash: 652e095bcce606e47cb97658f79eaca34033b239
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86953307"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="2a5a2-102">Как создать файл справки командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="2a5a2-103">В этом разделе описывается создание допустимого XML-файла, содержащего содержимое разделов справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="2a5a2-104">В этом разделе описывается, как присвоить имя файлу справки, как добавить соответствующие заголовки XML и как добавить узлы, которые будут содержать различные разделы содержимого справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="2a5a2-105">Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-105">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="2a5a2-106">Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-106">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="2a5a2-107">Создание файла справки по командлету</span><span class="sxs-lookup"><span data-stu-id="2a5a2-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="2a5a2-108">Создайте текстовый файл и сохраните его с помощью кодировки UTF8.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="2a5a2-109">Имя файла должно иметь следующий формат, чтобы Windows PowerShell могла обнаружить его как файл справки командлета.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-109">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="2a5a2-110">Добавьте следующие XML-заголовки в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="2a5a2-111">Имейте в виду, что файл будет проверен в соответствии со схемой языка разметки Microsoft Assistance (MAML).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-111">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="2a5a2-112">В настоящее время PowerShell не предоставляет никаких средств для проверки файла.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-112">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="2a5a2-113">Добавьте узел **команды** в файл справки командлета для каждого командлета в сборке.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-113">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="2a5a2-114">Каждый узел в узле **команды** относится к разным разделам справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-114">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="2a5a2-115">В следующей таблице перечислены элементы XML для каждого узла, за которыми следуют описания каждого узла.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="2a5a2-116">Узел</span><span class="sxs-lookup"><span data-stu-id="2a5a2-116">Node</span></span>           |                                                                                                     <span data-ttu-id="2a5a2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2a5a2-117">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="2a5a2-118">Добавляет содержимое для разделов "имя" и "КРАТКИй Обзор" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-119">Дополнительные сведения см. в разделе [Добавление имени командлета и кратких](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)сведений.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="2a5a2-120">Добавляет содержимое для раздела описания в разделе справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-121">Дополнительные сведения см. в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="2a5a2-122">Добавляет содержимое для раздела СИНТАКСИСа раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-123">Дополнительные сведения см. в [разделе Добавление синтаксиса в раздел справки по командлетам](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="2a5a2-124">Добавляет содержимое для раздела "Параметры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-125">Дополнительные сведения см. в [разделе Добавление параметров в раздел справки по командлетам](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="2a5a2-126">Добавляет содержимое для раздела "ВХОДные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-127">Дополнительные сведения см. в [разделе Добавление типов входных данных в раздел справки по командлетам](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="2a5a2-128">Добавляет содержимое для раздела "выходные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-129">Дополнительные сведения см. в [разделе Добавление возвращаемых значений в раздел справки по командлетам](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="2a5a2-130">Добавляет содержимое для раздела "Примечания" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-130">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-131">Дополнительные сведения см. в [разделе Добавление заметок в раздел справки по командлетам](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="2a5a2-132">Добавляет содержимое для раздела "примеры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-133">Дополнительные сведения см. в [разделе Добавление примеров в раздел справки по командлетам](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="2a5a2-134">Добавляет содержимое для раздела "связанные ссылки" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="2a5a2-135">Дополнительные сведения см. в [разделе Добавление связанных ссылок в раздел справки по командлетам](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="2a5a2-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="2a5a2-136">Пример</span><span class="sxs-lookup"><span data-stu-id="2a5a2-136">Example</span></span>

 <span data-ttu-id="2a5a2-137">Ниже приведен пример узла **команды** , который содержит узлы для различных разделов справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="2a5a2-137">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2a5a2-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a5a2-138">See Also</span></span>

 [<span data-ttu-id="2a5a2-139">Добавление имени командлета и кратких обзоров</span><span class="sxs-lookup"><span data-stu-id="2a5a2-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-140">Добавление подробного описания в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="2a5a2-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="2a5a2-141">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-142">Добавление параметров в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="2a5a2-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="2a5a2-143">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-144">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-145">Добавление заметок в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="2a5a2-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-146">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-147">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2a5a2-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="2a5a2-148">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a5a2-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
