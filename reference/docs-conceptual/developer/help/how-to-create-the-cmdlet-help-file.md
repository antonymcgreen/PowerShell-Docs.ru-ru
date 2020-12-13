---
ms.date: 09/13/2016
ms.topic: reference
title: Как создать файл справки командлета
description: Как создать файл справки командлета
ms.openlocfilehash: 40259c8f9496b10380805a78f3711aed6f1bf2e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659084"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="36d23-103">Как создать файл справки командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-103">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="36d23-104">В этом разделе описывается создание допустимого XML-файла, содержащего содержимое разделов справки по командлетам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36d23-104">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="36d23-105">В этом разделе описывается, как присвоить имя файлу справки, как добавить соответствующие заголовки XML и как добавить узлы, которые будут содержать различные разделы содержимого справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-105">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="36d23-106">Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36d23-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="36d23-107">Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36d23-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="36d23-108">Создание файла справки по командлету</span><span class="sxs-lookup"><span data-stu-id="36d23-108">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="36d23-109">Создайте текстовый файл и сохраните его с помощью кодировки UTF8.</span><span class="sxs-lookup"><span data-stu-id="36d23-109">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="36d23-110">Имя файла должно иметь следующий формат, чтобы Windows PowerShell могла обнаружить его как файл справки командлета.</span><span class="sxs-lookup"><span data-stu-id="36d23-110">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="36d23-111">Добавьте следующие XML-заголовки в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="36d23-111">Add the following XML headers to the text file.</span></span> <span data-ttu-id="36d23-112">Имейте в виду, что файл будет проверен в соответствии со схемой языка разметки Microsoft Assistance (MAML).</span><span class="sxs-lookup"><span data-stu-id="36d23-112">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="36d23-113">В настоящее время PowerShell не предоставляет никаких средств для проверки файла.</span><span class="sxs-lookup"><span data-stu-id="36d23-113">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="36d23-114">Добавьте узел **команды** в файл справки командлета для каждого командлета в сборке.</span><span class="sxs-lookup"><span data-stu-id="36d23-114">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="36d23-115">Каждый узел в узле **команды** относится к разным разделам справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-115">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="36d23-116">В следующей таблице перечислены элементы XML для каждого узла, за которыми следуют описания каждого узла.</span><span class="sxs-lookup"><span data-stu-id="36d23-116">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="36d23-117">Узел</span><span class="sxs-lookup"><span data-stu-id="36d23-117">Node</span></span>           |                                                                                                     <span data-ttu-id="36d23-118">Описание</span><span class="sxs-lookup"><span data-stu-id="36d23-118">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="36d23-119">Добавляет содержимое для разделов "имя" и "КРАТКИй Обзор" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-119">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-120">Дополнительные сведения см. в разделе [Добавление имени командлета и кратких](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)сведений.</span><span class="sxs-lookup"><span data-stu-id="36d23-120">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="36d23-121">Добавляет содержимое для раздела описания в разделе справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="36d23-121">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-122">Дополнительные сведения см. в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-122">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="36d23-123">Добавляет содержимое для раздела СИНТАКСИСа раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-123">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-124">Дополнительные сведения см. в [разделе Добавление синтаксиса в раздел справки по командлетам](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-124">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="36d23-125">Добавляет содержимое для раздела "Параметры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-125">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-126">Дополнительные сведения см. в [разделе Добавление параметров в раздел справки по командлетам](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-126">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="36d23-127">Добавляет содержимое для раздела "ВХОДные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-127">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-128">Дополнительные сведения см. в [разделе Добавление типов входных данных в раздел справки по командлетам](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-128">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="36d23-129">Добавляет содержимое для раздела "выходные данные" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-129">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-130">Дополнительные сведения см. в [разделе Добавление возвращаемых значений в раздел справки по командлетам](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-130">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="36d23-131">Добавляет содержимое для раздела "Примечания" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-131">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-132">Дополнительные сведения см. в [разделе Добавление заметок в раздел справки по командлетам](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-132">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="36d23-133">Добавляет содержимое для раздела "примеры" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-133">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-134">Дополнительные сведения см. в [разделе Добавление примеров в раздел справки по командлетам](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-134">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="36d23-135">Добавляет содержимое для раздела "связанные ссылки" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-135">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="36d23-136">Дополнительные сведения см. в [разделе Добавление связанных ссылок в раздел справки по командлетам](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-136">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="36d23-137">Пример</span><span class="sxs-lookup"><span data-stu-id="36d23-137">Example</span></span>

 <span data-ttu-id="36d23-138">Ниже приведен пример узла **команды** , который содержит узлы для различных разделов справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="36d23-138">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="36d23-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="36d23-139">See Also</span></span>

 [<span data-ttu-id="36d23-140">Добавление имени командлета и кратких обзоров</span><span class="sxs-lookup"><span data-stu-id="36d23-140">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-141">Добавление подробного описания в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="36d23-141">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="36d23-142">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-142">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-143">Добавление параметров в раздел справки по командлету</span><span class="sxs-lookup"><span data-stu-id="36d23-143">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="36d23-144">Как добавить типы входных данных в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-144">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-145">Как добавить возвращаемые значения в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-145">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-146">Добавление заметок в раздел справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="36d23-146">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-147">Как добавить примеры в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-147">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-148">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="36d23-148">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="36d23-149">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d23-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
