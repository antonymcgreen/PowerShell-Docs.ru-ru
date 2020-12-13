---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить сведения о параметрах
description: Как добавить сведения о параметрах
ms.openlocfilehash: 8f4fc46ef256a77b058df4ba506124f80732cb39
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663059"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="4c3f6-103">Как добавить сведения о параметрах</span><span class="sxs-lookup"><span data-stu-id="4c3f6-103">How to Add Parameter Information</span></span>

<span data-ttu-id="4c3f6-104">В этом разделе описывается, как добавить содержимое, отображаемое в разделе " **Параметры** " раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-104">This section describes how to add content that is displayed in the **PARAMETERS** section of the cmdlet Help topic.</span></span> <span data-ttu-id="4c3f6-105">В разделе **параметров** раздела справки перечислены все параметры командлета, а также подробно описан каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-105">The **PARAMETERS** section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="4c3f6-106">Содержимое раздела **Parameters** должно соответствовать содержимому раздела **синтаксиса** раздела справки.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-106">The content of the **PARAMETERS** section should be consistent with the content of the **SYNTAX** section of the Help topic.</span></span> <span data-ttu-id="4c3f6-107">Автор справки должен убедиться, что узел **синтаксис** и **Параметры** содержат похожие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-107">It is the responsibility of the Help author to make sure that both the **Syntax** and **Parameters** node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="4c3f6-108">Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-108">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="4c3f6-109">Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-109">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="4c3f6-110">Добавление параметров</span><span class="sxs-lookup"><span data-stu-id="4c3f6-110">To Add Parameters</span></span>

1. <span data-ttu-id="4c3f6-111">Откройте файл справки командлета и перейдите к узлу команды для командлета, для которого выполняется документирование.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-111">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="4c3f6-112">При добавлении нового командлета необходимо создать новый узел команды.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-112">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="4c3f6-113">Файл справки будет содержать узел команды для каждого командлета, для которого предоставляется содержимое справки.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-113">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="4c3f6-114">Ниже приведен пример пустого узла команды.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-114">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

1. <span data-ttu-id="4c3f6-115">В узле команды выберите узел описание и добавьте узел Параметры, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-115">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span>
   <span data-ttu-id="4c3f6-116">Допускается только один узел параметров, и он должен следовать непосредственно за узлом синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-116">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

1. <span data-ttu-id="4c3f6-117">В узле параметры добавьте узел **параметров** для каждого параметра командлета, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-117">Within the Parameters node, add a **Parameter** node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="4c3f6-118">В этом примере для трех параметров добавляется узел **параметров** .</span><span class="sxs-lookup"><span data-stu-id="4c3f6-118">In this example, a **Parameter** node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="4c3f6-119">Поскольку это те же XML-теги, которые используются в узле синтаксиса, и так как указанные здесь параметры должны соответствовать параметрам, заданным в узле синтаксиса, можно скопировать узлы параметров из узла синтаксиса и вставить их в узел Параметры.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-119">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="4c3f6-120">Однако не забудьте скопировать только один экземпляр узла параметра, даже если параметр указан в синтаксисе в нескольких наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-120">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

1. <span data-ttu-id="4c3f6-121">Для каждого узла параметра задайте значения атрибутов, определяющие характеристики каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-121">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="4c3f6-122">К этим атрибутам относятся следующие: required, глобализации, пипелинеинпут и положением.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-122">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

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

1. <span data-ttu-id="4c3f6-123">Для каждого узла параметра добавьте имя параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-123">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="4c3f6-124">Ниже приведен пример имени параметра, добавляемого в узел параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-124">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="4c3f6-125">Для каждого узла **параметра** добавьте описание параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-125">For each **Parameter** node, add the description of the parameter.</span></span> <span data-ttu-id="4c3f6-126">Ниже приведен пример описания параметра, добавленного к узлу **параметров** .</span><span class="sxs-lookup"><span data-stu-id="4c3f6-126">Here is an example of the parameter description added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4c3f6-127">Для каждого узла **параметра** добавьте тип .NET параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-127">For each **Parameter** node, add the .NET type of the parameter.</span></span> <span data-ttu-id="4c3f6-128">Тип параметра отображается вместе с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-128">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="4c3f6-129">Ниже приведен пример типа .NET параметра, добавляемого в узел **параметра** .</span><span class="sxs-lookup"><span data-stu-id="4c3f6-129">Here is an example of the parameter .NET type added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4c3f6-130">Для каждого узла **параметра** добавьте значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-130">For each **Parameter** node, add the default value of the parameter.</span></span> <span data-ttu-id="4c3f6-131">Следующее предложение добавляется в описание параметра при отображении содержимого: **DefaultValue** является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-131">The following sentence is added to the parameter description when the content is displayed: **DefaultValue** is the default.</span></span>

   <span data-ttu-id="4c3f6-132">Ниже приведен пример значения параметра по умолчанию, добавляемого к узлу **параметров** .</span><span class="sxs-lookup"><span data-stu-id="4c3f6-132">Here is an example of the parameter default value is added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4c3f6-133">Для каждого параметра, имеющего несколько значений, добавьте узел возможных значений.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-133">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="4c3f6-134">Ниже приведен пример узла возможных значений, который определяет два возможных значения для параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-134">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="4c3f6-135">Ниже приведены некоторые моменты, которые следует помнить при добавлении параметров.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-135">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="4c3f6-136">Атрибуты параметра не отображаются во всех представлениях раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-136">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="4c3f6-137">Однако они отображаются в таблице после описания параметра, когда пользователь запрашивает **полное** `Get-Help <cmdletname> -full` представление () или **параметр** ( `Get-Help <cmdletname> -parameter` ) раздела.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-137">However, they are displayed in a table following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help <cmdletname> -parameter`) view of the topic.</span></span>

- <span data-ttu-id="4c3f6-138">Описание параметра является одной из наиболее важных частей раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-138">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="4c3f6-139">Описание должно быть кратким, а также подробным.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-139">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="4c3f6-140">Кроме того, помните, что если описание параметра станет слишком длинным, например, когда два параметра взаимодействуют друг с другом, можно добавить дополнительное содержимое в раздел "Примечания" раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-140">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="4c3f6-141">Описание параметра предоставляет два типа информации.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-141">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="4c3f6-142">Действие командлета при использовании параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-142">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="4c3f6-143">Допустимое значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-143">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="4c3f6-144">Поскольку значения параметров выражаются в виде объектов .NET, пользователям требуются дополнительные сведения об этих значениях, чем в традиционной справке по командной строке.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-144">Because the parameter values are expressed as .NET objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="4c3f6-145">Сообщите пользователю, какой тип данных предназначен для принятия параметра, и включите примеры.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-145">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="4c3f6-146">Значение параметра по умолчанию — значение, которое используется, если параметр не указан в командной строке.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-146">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="4c3f6-147">Обратите внимание, что значение по умолчанию является необязательным и не требуется для некоторых параметров, таких как обязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-147">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="4c3f6-148">Однако для большинства необязательных параметров следует указать значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-148">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="4c3f6-149">Значение по умолчанию помогает пользователю понять, какой результат не используется параметром.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-149">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="4c3f6-150">Опишите значение по умолчанию особенно, например "текущий каталог" или "каталог установки PowerShell ( `$PSHOME` )", для необязательного пути.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-150">Describe the default value very specifically, such as the "Current directory" or the "PowerShell installation directory (`$PSHOME`)" for an optional path.</span></span> <span data-ttu-id="4c3f6-151">Можно также написать предложение, описывающее значение по умолчанию, например следующее предложение, используемое для параметра **PassThru** : "Если параметр PassThru не указан, командлет не передает объекты по конвейеру".</span><span class="sxs-lookup"><span data-stu-id="4c3f6-151">You can also write a sentence that describes the default, such as the following sentence used for the **PassThru** parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span> <span data-ttu-id="4c3f6-152">Кроме того, поскольку значение отображается в противоположном **значении имени поля по умолчанию**, в записи не нужно включать термин "значение по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="4c3f6-152">Also, because the value is displayed opposite the field name **Default value**, you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="4c3f6-153">Значение параметра по умолчанию не отображается во всех представлениях раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-153">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="4c3f6-154">Однако он отображается в таблице (вместе с атрибутами параметров) после описания параметра, когда пользователь запрашивает **полное** `Get-Help <cmdletname> -full` представление () или **параметр** ( `Get-Help
<cmdletname> -parameter` ) раздела.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-154">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help
<cmdletname> -parameter`) view of the topic.</span></span>

<span data-ttu-id="4c3f6-155">В следующем коде XML показана пара `<dev:defaultValue>` тегов, добавленных в `<command:parameter>` узел.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-155">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span>
<span data-ttu-id="4c3f6-156">Обратите внимание, что значение по умолчанию следует сразу после закрывающего `</command:parameterValue>` тега (если указано значение параметра) или закрывающего `</maml:description>` тега описания параметра.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-156">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="4c3f6-157">имя.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-157">name.</span></span>

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

<span data-ttu-id="4c3f6-158">Добавление значений для перечислимых типов</span><span class="sxs-lookup"><span data-stu-id="4c3f6-158">Add Values for Enumerated Types</span></span>

<span data-ttu-id="4c3f6-159">Если параметр имеет несколько значений или значений перечисляемого типа, можно использовать необязательный \<dev:possibleValues> узел.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-159">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="4c3f6-160">Этот узел позволяет указать имя и описание для нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-160">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="4c3f6-161">Имейте в виду, что описания перечислимых значений не отображаются ни в одном из представлений справки по умолчанию, отображаемых `Get-Help` командлетом, но другие средства просмотра справки могут отображать это содержимое в своих представлениях.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-161">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="4c3f6-162">В следующем XML-коде показан `<dev:possibleValues>` узел с двумя указанными значениями.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-162">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

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
