---
title: Как добавить сведения о параметрах | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6c1442-60aa-477a-8f30-ab02b1b11039
caps.latest.revision: 7
ms.openlocfilehash: d4a5fc934a41b00f89862674e44e4540680674f7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083371"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="bf08b-102">Как добавить сведения о параметрах</span><span class="sxs-lookup"><span data-stu-id="bf08b-102">How to Add Parameter Information</span></span>

<span data-ttu-id="bf08b-103">В этом разделе описывается добавление содержимого, которое отображается в разделе "Параметры" раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="bf08b-103">This section describes how to add content that is displayed in the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="bf08b-104">В разделе "Параметры" раздела справки перечислены все параметры командлета и содержит подробное описание каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-104">The PARAMETERS section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="bf08b-105">Содержимое раздела параметров должны соответствовать содержимое раздела "СИНТАКСИС" раздела справки.</span><span class="sxs-lookup"><span data-stu-id="bf08b-105">The content of the PARAMETERS section should be consistent with the content of the SYNTAX section of the Help topic.</span></span> <span data-ttu-id="bf08b-106">Он отвечает автор справки, чтобы убедиться в том, что синтаксис и параметры узла содержат аналогичные элементы XML.</span><span class="sxs-lookup"><span data-stu-id="bf08b-106">It is the responsibility of the Help author to make sure that both the Syntax and Parameters node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="bf08b-107">Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf08b-107">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="bf08b-108">Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf08b-108">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="bf08b-109">Чтобы добавить параметры</span><span class="sxs-lookup"><span data-stu-id="bf08b-109">To Add Parameters</span></span>

1. <span data-ttu-id="bf08b-110">Откройте файл справки командлета и найдите узел команд для командлета, о котором нужно документировать.</span><span class="sxs-lookup"><span data-stu-id="bf08b-110">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="bf08b-111">Если вы добавляете новый командлет, вам нужно будет создать новый узел команды.</span><span class="sxs-lookup"><span data-stu-id="bf08b-111">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="bf08b-112">Файл справки будет содержать узел для каждого командлета, вы предоставляете содержимого справки для команд.</span><span class="sxs-lookup"><span data-stu-id="bf08b-112">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="bf08b-113">Ниже приведен пример пустой узел команды.</span><span class="sxs-lookup"><span data-stu-id="bf08b-113">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

2. <span data-ttu-id="bf08b-114">Внутри узла команды перейдите к узлу описание и добавить узел параметров, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bf08b-114">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span> <span data-ttu-id="bf08b-115">Допускается только один узел параметров, и он должен следовать непосредственно за узел синтаксического.</span><span class="sxs-lookup"><span data-stu-id="bf08b-115">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. <span data-ttu-id="bf08b-116">В узел «параметры» добавьте узел параметра для каждого параметра командлета, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bf08b-116">Within the Parameters node, add a Parameter node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="bf08b-117">В этом примере узел параметра добавляется для трех параметров.</span><span class="sxs-lookup"><span data-stu-id="bf08b-117">In this example, a Parameter node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="bf08b-118">Так как это же XML-теги, которые используются в узле синтаксис и поскольку здесь указаны параметры должны соответствовать параметрам, указанным узла синтаксического можно копировать узлы параметров из узла синтаксического и вставьте их в узел «параметры».</span><span class="sxs-lookup"><span data-stu-id="bf08b-118">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="bf08b-119">Тем не менее, не забудьте скопировать только один экземпляр узел параметров, даже если этот параметр указан в нескольких параметр задает в синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="bf08b-119">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

4. <span data-ttu-id="bf08b-120">Для каждого параметра набора узлов, значения атрибутов, определяющих характеристики каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-120">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="bf08b-121">Эти атрибуты включают следующие: требуется, глобализации, pipelineinput и положение.</span><span class="sxs-lookup"><span data-stu-id="bf08b-121">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

5. <span data-ttu-id="bf08b-122">Для каждого параметра узла добавьте имя параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-122">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="bf08b-123">Вот пример добавляемый узел параметра имени параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-123">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. <span data-ttu-id="bf08b-124">Для каждого параметра узла добавьте описание параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-124">For each Parameter node, add the description of the parameter.</span></span> <span data-ttu-id="bf08b-125">Ниже приведен пример к узлу параметр добавляется описание параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-125">Here is an example of the parameter description added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

7. <span data-ttu-id="bf08b-126">Для каждого параметра узла добавление .NET Framework типа параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-126">For each Parameter node, add the .NET Framework type of the parameter.</span></span> <span data-ttu-id="bf08b-127">Тип параметра отображается вместе с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-127">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="bf08b-128">Вот пример типа платформы .NET Framework параметр, добавляемый узел параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-128">Here is an example of the parameter .NET Framework type added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

8. <span data-ttu-id="bf08b-129">Для каждого параметра узла добавьте значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bf08b-129">For each Parameter node, add the default value of the parameter.</span></span> <span data-ttu-id="bf08b-130">Следующее предложение добавляется описание параметра при отображении содержимого: «DefaultValue» используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bf08b-130">The following sentence is added to the parameter description when the content is displayed: "DefaultValue" is the default.</span></span>

   <span data-ttu-id="bf08b-131">Ниже приведен пример значения параметра по умолчанию добавляется к узлу параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-131">Here is an example of the parameter default value is added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

9. <span data-ttu-id="bf08b-132">Для каждого параметра, имеющей несколько значений Добавление узла возможные значения.</span><span class="sxs-lookup"><span data-stu-id="bf08b-132">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="bf08b-133">Вот пример возможных значений узла, который определяет два возможных значения для параметра</span><span class="sxs-lookup"><span data-stu-id="bf08b-133">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      /dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="bf08b-134">Ниже приведены некоторые важные советы при добавлении параметров.</span><span class="sxs-lookup"><span data-stu-id="bf08b-134">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="bf08b-135">Атрибуты параметра не отображаются во всех представлениях раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="bf08b-135">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="bf08b-136">Тем не менее, они отображаются в таблице, следуя описанию параметра, когда пользователь запрашивает полный (Get-Help \<cmdletname >-полная) или параметра (Get-Help \<cmdletname >-параметра) представление раздела.</span><span class="sxs-lookup"><span data-stu-id="bf08b-136">However, they are displayed in a table following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

- <span data-ttu-id="bf08b-137">Описание параметра является одним из наиболее важные части раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="bf08b-137">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="bf08b-138">Описание должно быть краткое, а также полной.</span><span class="sxs-lookup"><span data-stu-id="bf08b-138">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="bf08b-139">Кроме того помните, что если описание параметра становится слишком много времени, например, если два параметра взаимодействуют друг с другом, можно добавить дополнительные материалы в разделе "Примечания" раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="bf08b-139">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="bf08b-140">Описание параметра предоставляет два типа сведений.</span><span class="sxs-lookup"><span data-stu-id="bf08b-140">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="bf08b-141">Действиях командлета при использовании параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-141">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="bf08b-142">Какие допустимое значение — в параметре.</span><span class="sxs-lookup"><span data-stu-id="bf08b-142">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="bf08b-143">Так как значения параметров, выражаются в виде объектов .NET Framework, пользователи должны Дополнительные сведения об этих значениях, чем при работе в традиционных Справка по командной строке.</span><span class="sxs-lookup"><span data-stu-id="bf08b-143">Because the parameter values are expressed as .NET Framework objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="bf08b-144">Уведомить пользователя, какой тип данных параметра предназначена для приема и включают примеры.</span><span class="sxs-lookup"><span data-stu-id="bf08b-144">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="bf08b-145">Значение по умолчанию параметра является значение, которое используется, если этот параметр не указан в командной строке.</span><span class="sxs-lookup"><span data-stu-id="bf08b-145">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="bf08b-146">Обратите внимание, что значение по умолчанию является необязательным и не требуется для некоторых параметров, таких как обязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="bf08b-146">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="bf08b-147">Тем не менее следует указать значение по умолчанию для большинства необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="bf08b-147">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="bf08b-148">Значение по умолчанию помогает пользователю понять последствия не используя параметр.</span><span class="sxs-lookup"><span data-stu-id="bf08b-148">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="bf08b-149">Описания по умолчанию очень в частности, например «текущий каталог» или «Windows PowerShell каталог установки ($pshome)» дополнительный путь.</span><span class="sxs-lookup"><span data-stu-id="bf08b-149">Describe the default value very specifically, such as the "Current directory" or the "Windows PowerShell installation directory ($pshome)" for an optional path.</span></span> <span data-ttu-id="bf08b-150">Можно также создавать предложение, описывающее по умолчанию, например, следующее предложение для `PassThru` параметр: «Если PassThru не указан, командлет не передает объекты по конвейеру.»</span><span class="sxs-lookup"><span data-stu-id="bf08b-150">You can also write a sentence that describes the default, such as the following sentence used for the `PassThru` parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span>  <span data-ttu-id="bf08b-151">Кроме того поскольку напротив имени поля отображается значение "**значение по умолчанию**«, необходимо включить термин «значение по умолчанию» в записи.</span><span class="sxs-lookup"><span data-stu-id="bf08b-151">Also, because the value is displayed opposite the field name "**Default value**", you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="bf08b-152">Значение по умолчанию параметра не отображается во всех представлениях раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="bf08b-152">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="bf08b-153">Тем не менее, он отображается в таблице (а также атрибуты параметра) следуя описание параметра, когда пользователь запрашивает полный (Get-Help \<cmdletname >-полная) или параметра (Get-Help \<cmdletname >-параметра) представления раздела.</span><span class="sxs-lookup"><span data-stu-id="bf08b-153">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

<span data-ttu-id="bf08b-154">Следующий код XML показывает пару `<dev:defaultValue>` теги, добавляемые к `<command:parameter>` узла.</span><span class="sxs-lookup"><span data-stu-id="bf08b-154">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span> <span data-ttu-id="bf08b-155">Обратите внимание, что значение по умолчанию соответствует сразу после завершения `</command:parameterValue>` тега (Если указано значение параметра) или закрытие `</maml:description>` тег описание параметра.</span><span class="sxs-lookup"><span data-stu-id="bf08b-155">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="bf08b-156">Имя.</span><span class="sxs-lookup"><span data-stu-id="bf08b-156">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="bf08b-157">Добавьте значения для перечисляемых типов</span><span class="sxs-lookup"><span data-stu-id="bf08b-157">Add Values for Enumerated Types</span></span>

<span data-ttu-id="bf08b-158">Если параметр состоит из нескольких значений или значений перечисляемого типа, можно использовать необязательный \<dev:possibleValues > узла.</span><span class="sxs-lookup"><span data-stu-id="bf08b-158">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="bf08b-159">Этот узел позволяет указать имя и описание для нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="bf08b-159">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="bf08b-160">Имейте в виду, что описания перечисляемые значения не отображаются в по умолчанию представления справки, отображаемого элементом `Get-Help` командлета, но в других средствах просмотра справки может отобразить это содержимое в своих представлениях.</span><span class="sxs-lookup"><span data-stu-id="bf08b-160">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="bf08b-161">Следующий код XML показывает `<dev:possibleValues>` узел с двумя указанными значениями.</span><span class="sxs-lookup"><span data-stu-id="bf08b-161">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```