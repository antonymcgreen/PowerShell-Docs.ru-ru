---
title: Добавление синтаксиса в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c6d03f-1c1a-43d8-928e-e3290e90e0bc
caps.latest.revision: 5
ms.openlocfilehash: 0210b5ed3104777541692a0e78e7d3b16f9c8256
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361213"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="fc0e7-102">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="fc0e7-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="fc0e7-103">Прежде чем начать код XML для схемы синтаксиса в файле справки по командлетам, прочтите этот раздел, чтобы получить четкое представление о типе данных, которые необходимо предоставить, например атрибуты параметров, а также способ отображения данных на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-103">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

### <a name="parameter-attributes"></a><span data-ttu-id="fc0e7-104">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="fc0e7-104">Parameter Attributes</span></span>

- <span data-ttu-id="fc0e7-105">Обязательный</span><span class="sxs-lookup"><span data-stu-id="fc0e7-105">Required</span></span>

  - <span data-ttu-id="fc0e7-106">Если значение — true, параметр должен отображаться во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-106">If true, the parameter must appear in all commands that use the parameter set.</span></span>

  - <span data-ttu-id="fc0e7-107">Если значение равно false, параметр является необязательным во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-107">If false, the parameter is optional in all commands that use the parameter set.</span></span>

- <span data-ttu-id="fc0e7-108">Разместить</span><span class="sxs-lookup"><span data-stu-id="fc0e7-108">Position</span></span>

  - <span data-ttu-id="fc0e7-109">Если задано имя, необходимо указать параметр Name.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-109">If named, the parameter name is required.</span></span>

  - <span data-ttu-id="fc0e7-110">При позиционировании имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-110">If positional, the parameter name is optional.</span></span> <span data-ttu-id="fc0e7-111">Если он не указан, значение параметра должно находиться в указанной положении в команде.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-111">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="fc0e7-112">Например, если значение равно "1", значение параметра должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-112">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>

- <span data-ttu-id="fc0e7-113">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="fc0e7-113">Pipeline Input</span></span>

  - <span data-ttu-id="fc0e7-114">Если true (Бивалуе), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-114">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="fc0e7-115">Входные данные связаны с параметром ("привязано к"), даже если имя свойства и тип объекта не соответствуют ожидаемому типу.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-115">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span> <span data-ttu-id="fc0e7-116">Windows PowerShell? компоненты привязки параметров пытаются преобразовать входные данные в правильный тип и завершить команду только в том случае, если тип не может быть преобразован.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-116">The Windows PowerShell? parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="fc0e7-117">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-117">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="fc0e7-118">Если true (Бипропертинаме), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-118">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="fc0e7-119">Однако входные данные связываются с параметром только в том случае, если имя параметра совпадает с именем свойства входного объекта.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-119">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="fc0e7-120">Например, если имя параметра — `Path`, объекты, переданный в командлет, связываются с этим параметром только в том случае, если у объекта есть свойство с именем path.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-120">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>

  - <span data-ttu-id="fc0e7-121">Если true (Бивалуе, Бипропертинаме), можно передать входные данные в параметр по имени свойства или по значению.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-121">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="fc0e7-122">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-122">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="fc0e7-123">Если значение равно false, нельзя передавать входные данные в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-123">If false, you cannot pipe input to this parameter.</span></span>

- <span data-ttu-id="fc0e7-124">Глобализации</span><span class="sxs-lookup"><span data-stu-id="fc0e7-124">Globbing</span></span>

  - <span data-ttu-id="fc0e7-125">Если значение — true, текст, который пользователь вводит в качестве значения параметра, может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-125">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>

  - <span data-ttu-id="fc0e7-126">Если значение равно false, то текст, который пользователь вводит в качестве значения параметра, не может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-126">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="fc0e7-127">Атрибуты значения параметра</span><span class="sxs-lookup"><span data-stu-id="fc0e7-127">Parameter Value Attributes</span></span>

- <span data-ttu-id="fc0e7-128">Обязательный</span><span class="sxs-lookup"><span data-stu-id="fc0e7-128">Required</span></span>

  - <span data-ttu-id="fc0e7-129">Если значение — true, указанное значение должно использоваться при использовании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-129">If true, the specified value must be used whenever using the parameter in a command.</span></span>

  - <span data-ttu-id="fc0e7-130">При значении false значение параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-130">If false, the parameter value is optional.</span></span> <span data-ttu-id="fc0e7-131">Как правило, значение является необязательным, только если оно является одним из нескольких допустимых значений для параметра, например в перечислимом типе.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-131">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="fc0e7-132">Обязательный атрибут значения параметра отличается от обязательного атрибута параметра.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-132">The Required attribute of a parameter value is different from the Required attribute of a parameter.</span></span>

<span data-ttu-id="fc0e7-133">Обязательный атрибут параметра указывает, следует ли включать параметр (и его значение) при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-133">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="fc0e7-134">В отличие от этого, обязательный атрибут значения параметра используется только в том случае, если параметр включен в команду.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-134">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="fc0e7-135">Указывает, следует ли использовать это конкретное значение с параметром.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-135">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="fc0e7-136">Обычно значения параметров, которые являются заполнителями, являются обязательными, а значения параметров, являющиеся литералом, не являются обязательными, так как они являются одним из нескольких значений, которые могут использоваться с параметром.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-136">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="fc0e7-137">Сбор сведений о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="fc0e7-137">Gathering Syntax Information</span></span>

1. <span data-ttu-id="fc0e7-138">Начните с имени командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-138">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

2. <span data-ttu-id="fc0e7-139">Перечислите все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-139">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="fc0e7-140">Перед именем каждого параметра введите тире (тире или знак "минус" (ASCII 45).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-140">Type a dash (also known as a "dash" or "minus sign" (ASCII 45) before each parameter name.</span></span> <span data-ttu-id="fc0e7-141">Разделите параметры на наборы параметров (некоторые командлеты могут иметь только один набор параметров).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-141">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="fc0e7-142">В этом примере командлет Get-Tech имеет два набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-142">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="fc0e7-143">Запустите каждый набор параметров с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-143">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="fc0e7-144">Сначала укажите набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-144">List the default parameter set first.</span></span> <span data-ttu-id="fc0e7-145">Параметр по умолчанию задается классом командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-145">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="fc0e7-146">Для каждого набора параметров сначала укажите его уникальный параметр, если не существуют параметры, которые должны отображаться первыми.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-146">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="fc0e7-147">В предыдущем примере параметры Name и ID являются уникальными параметрами для двух наборов параметров (каждый набор параметров должен иметь один параметр, уникальный для этого набора параметров).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-147">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="fc0e7-148">Это упрощает пользователям определение того, какой параметр необходимо предоставить для набора параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-148">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="fc0e7-149">Перечислите параметры в том порядке, в котором они должны отображаться в команде.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-149">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="fc0e7-150">Если порядок не имеет значения, перечислите связанные параметры вместе или сначала перечислите наиболее часто используемые параметры.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-150">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="fc0e7-151">Обязательно перечислите параметры WhatIf и Confirm, если командлет поддерживает ShouldProcess.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-151">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="fc0e7-152">Не перечислите общие параметры (например, Verbose, Debug и ErrorAction) в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-152">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="fc0e7-153">Командлет `Get-Help` добавляет эти сведения при отображении раздела справки.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-153">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

3. <span data-ttu-id="fc0e7-154">Добавьте значения параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-154">Add the parameter values.</span></span> <span data-ttu-id="fc0e7-155">В Windows PowerShell? значения параметров представлены их типом .NET.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-155">In Windows PowerShell?, parameter values are represented by their .NET type.</span></span> <span data-ttu-id="fc0e7-156">Однако имя типа может быть сокращено, например "String" для System. String.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-156">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="fc0e7-157">Сокращенные типы при условии, что их значение является ясным, например "String" для System. String и "int" для System. Int32.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-157">Abbreviate types as long as their meaning is clear, such as "string" for System.String and "int" for System.Int32.</span></span>

   <span data-ttu-id="fc0e7-158">Перечислите все значения перечислений, например параметр-Type в предыдущем примере, для которого можно задать значение Basic или Advanced.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-158">List all values of enumerations, such as the -type parameter in the previous example, which can be set to "basic" or "advanced".</span></span>

   <span data-ttu-id="fc0e7-159">Параметры коммутатора, такие как-List в предыдущем примере, не имеют значений.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-159">Switch parameters, such as -list in the previous example, do not have values.</span></span>

4. <span data-ttu-id="fc0e7-160">Добавьте угловые скобки в значения параметров, которые являются заполнителями, по сравнению со значениями параметров, которые являются литералами.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-160">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. <span data-ttu-id="fc0e7-161">Заключите необязательные параметры и их а также корректируются в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-161">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. <span data-ttu-id="fc0e7-162">Заключите имена необязательных параметров (для параметров позиционирования) в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-162">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="fc0e7-163">Имя для параметров, которые являются позиционированными, например параметр Name в следующем примере, не обязательно включать в команду.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-163">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. <span data-ttu-id="fc0e7-164">Если значение параметра может содержать несколько значений, например список имен в параметре name, добавьте пару квадратных скобок непосредственно после значения параметра.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-164">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. <span data-ttu-id="fc0e7-165">Если пользователь может выбрать один из параметров или значений параметров, например параметр типа, заключите варианты в фигурные скобки и разделите их символом или (;).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-165">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. <span data-ttu-id="fc0e7-166">Если значение параметра должно использовать определенное форматирование, например кавычки или круглые скобки, то в синтаксисе отображается формат.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-166">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="fc0e7-167">Кодирование XML-кода схемы синтаксиса</span><span class="sxs-lookup"><span data-stu-id="fc0e7-167">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="fc0e7-168">Узел синтаксиса XML начинается сразу после узла Description, который заканчивается тегом \</MAML: Description >.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-168">The syntax node of the XML begins immediately after the description node, which ends with the \</maml:description> tag.</span></span> <span data-ttu-id="fc0e7-169">Сведения о сборе данных, используемых в схеме синтаксиса, см. в разделе [сбор сведений о синтаксисе](#gathering-syntax-information).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-169">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="fc0e7-170">Добавление синтаксического узла</span><span class="sxs-lookup"><span data-stu-id="fc0e7-170">Adding a Syntax Node</span></span>

<span data-ttu-id="fc0e7-171">Схема синтаксиса, отображаемая в разделе справки по командлетам, создается на основе данных в узле синтаксиса XML.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-171">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="fc0e7-172">Узел синтаксиса заключен в пару, если \<command: синтаксис > тегами.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-172">The syntax node is enclosed in a pair if \<command:syntax> tags.</span></span> <span data-ttu-id="fc0e7-173">С каждым набором параметров командлета, заключенного в пару \<command: синтакситем > Tags.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-173">With each parameter set of the cmdlet enclosed in a pair of \<command:syntaxitem> tags.</span></span> <span data-ttu-id="fc0e7-174">Количество тегов \<command: синтакситем >, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-174">There is no limit to the number of \<command:syntaxitem> tags that you can add.</span></span>

<span data-ttu-id="fc0e7-175">В следующем примере показан узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-175">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    ...
    <!--Parameter Set 1 (default parameter set) parameters go here-->
    ...
  </command:syntaxItem>
  <command:syntaxItem>
    ...
    <!--Parameter Set 2 parameters go here-->
    ...
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="fc0e7-176">Добавление имени командлета в данные набора параметров</span><span class="sxs-lookup"><span data-stu-id="fc0e7-176">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="fc0e7-177">Каждый набор параметров командлета указывается в узле элемента синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-177">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="fc0e7-178">Каждый узел элемента синтаксиса начинается с пары \<maml: name > тегов, включающих имя командлета.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-178">Each syntax item node begins with a pair of \<maml:name> tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="fc0e7-179">Следующий пример включает узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-179">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-parameters"></a><span data-ttu-id="fc0e7-180">Добавление параметров</span><span class="sxs-lookup"><span data-stu-id="fc0e7-180">Adding Parameters</span></span>

<span data-ttu-id="fc0e7-181">Каждый параметр, добавляемый в узел элемента синтаксиса, указывается в паре тегов \<command: Parameter >.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-181">Each parameter added to the syntax item node is specified within a pair of \<command:parameter> tags.</span></span> <span data-ttu-id="fc0e7-182">Для каждого параметра, включенного в набор параметров, требуется пара \<command: параметр > тегов, за исключением общих параметров, предоставляемых Windows PowerShell?.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-182">You need a pair of \<command:parameter> tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by Windows PowerShell?.</span></span>

<span data-ttu-id="fc0e7-183">Атрибуты открывающего \<command: Parameter > тега определяют, как параметр отображается на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-183">The attributes of the opening \<command:parameter> tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="fc0e7-184">Дополнительные сведения об атрибутах параметров см. в разделе [атрибуты параметров](#parameter-attributes).</span><span class="sxs-lookup"><span data-stu-id="fc0e7-184">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="fc0e7-185">Тег \<command: Parameter > поддерживает дочерний элемент \<maml: Description >, содержимое которого никогда не отображается.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-185">The \<command:parameter> tag supports a child element \<maml:description> whose content is never displayed.</span></span> <span data-ttu-id="fc0e7-186">Описания параметров указываются в узле параметров XML.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-186">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="fc0e7-187">Чтобы избежать несоответствий между данными в элементе синтаксиса бодес и узлом параметров, опустите параметр (\<maml: Description > или оставьте его пустым.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-187">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (\<maml:description> or leave it empty.</span></span>

<span data-ttu-id="fc0e7-188">Следующий пример включает узел элемента синтаксиса для набора параметров с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="fc0e7-188">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

```xml
<command:syntaxItem>
  <maml:name>Cmdlet-Name</maml:name>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByValue)" position="1">
    <maml:name>ParameterName1</maml:name>
    <command:parameterValue required="true">
      string[]
    </command:parameterValue>
  </command:parameter>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByPropertyName)">
    <maml:name>ParameterName2</maml:name>
    <command:parameterValue required="true">
      int32[]
    </command:parameterValue>
  </command:parameter>
</command:syntaxItem>
```
