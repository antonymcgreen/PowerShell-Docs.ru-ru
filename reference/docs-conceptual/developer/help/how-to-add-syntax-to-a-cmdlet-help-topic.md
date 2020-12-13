---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить синтаксис в раздел справки для командлета
description: Как добавить синтаксис в раздел справки для командлета
ms.openlocfilehash: bcc037d22051c162cd0f70702da17afe7ed9c01a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659078"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="ca56d-103">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="ca56d-103">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="ca56d-104">Прежде чем начать код XML для схемы синтаксиса в файле справки по командлетам, прочтите этот раздел, чтобы получить четкое представление о типе данных, которые необходимо предоставить, например атрибуты параметров, а также способ отображения данных на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ca56d-104">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="ca56d-105">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="ca56d-105">Parameter Attributes</span></span>

- <span data-ttu-id="ca56d-106">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ca56d-106">Required</span></span>
  - <span data-ttu-id="ca56d-107">Если значение — true, параметр должен отображаться во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-107">If true, the parameter must appear in all commands that use the parameter set.</span></span>
  - <span data-ttu-id="ca56d-108">Если значение равно false, параметр является необязательным во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-108">If false, the parameter is optional in all commands that use the parameter set.</span></span>
- <span data-ttu-id="ca56d-109">Положение</span><span class="sxs-lookup"><span data-stu-id="ca56d-109">Position</span></span>
  - <span data-ttu-id="ca56d-110">Если задано имя, необходимо указать параметр Name.</span><span class="sxs-lookup"><span data-stu-id="ca56d-110">If named, the parameter name is required.</span></span>
  - <span data-ttu-id="ca56d-111">При позиционировании имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ca56d-111">If positional, the parameter name is optional.</span></span> <span data-ttu-id="ca56d-112">Если он не указан, значение параметра должно находиться в указанной положении в команде.</span><span class="sxs-lookup"><span data-stu-id="ca56d-112">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="ca56d-113">Например, если значение равно "1", значение параметра должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="ca56d-113">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>
- <span data-ttu-id="ca56d-114">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="ca56d-114">Pipeline Input</span></span>
  - <span data-ttu-id="ca56d-115">Если true (Бивалуе), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="ca56d-115">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="ca56d-116">Входные данные связаны с параметром ("привязано к"), даже если имя свойства и тип объекта не соответствуют ожидаемому типу.</span><span class="sxs-lookup"><span data-stu-id="ca56d-116">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span>
    <span data-ttu-id="ca56d-117">Компоненты привязки параметров PowerShell пытаются преобразовать входные данные в правильный тип и завершить команду только в том случае, если тип не может быть преобразован.</span><span class="sxs-lookup"><span data-stu-id="ca56d-117">The PowerShell parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="ca56d-118">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="ca56d-118">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="ca56d-119">Если true (Бипропертинаме), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="ca56d-119">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="ca56d-120">Однако входные данные связываются с параметром только в том случае, если имя параметра совпадает с именем свойства входного объекта.</span><span class="sxs-lookup"><span data-stu-id="ca56d-120">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="ca56d-121">Например, если имя параметра — `Path` , объекты, переданный в командлет, связываются с этим параметром только в том случае, если у объекта есть свойство с именем path.</span><span class="sxs-lookup"><span data-stu-id="ca56d-121">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>
  - <span data-ttu-id="ca56d-122">Если true (Бивалуе, Бипропертинаме), можно передать входные данные в параметр по имени свойства или по значению.</span><span class="sxs-lookup"><span data-stu-id="ca56d-122">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="ca56d-123">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="ca56d-123">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="ca56d-124">Если значение равно false, нельзя передавать входные данные в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="ca56d-124">If false, you cannot pipe input to this parameter.</span></span>
- <span data-ttu-id="ca56d-125">Глобализации</span><span class="sxs-lookup"><span data-stu-id="ca56d-125">Globbing</span></span>
  - <span data-ttu-id="ca56d-126">Если значение — true, текст, который пользователь вводит в качестве значения параметра, может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ca56d-126">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>
  - <span data-ttu-id="ca56d-127">Если значение равно false, то текст, который пользователь вводит в качестве значения параметра, не может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ca56d-127">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="ca56d-128">Атрибуты значения параметра</span><span class="sxs-lookup"><span data-stu-id="ca56d-128">Parameter Value Attributes</span></span>

- <span data-ttu-id="ca56d-129">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ca56d-129">Required</span></span>
  - <span data-ttu-id="ca56d-130">Если значение — true, указанное значение должно использоваться при использовании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="ca56d-130">If true, the specified value must be used whenever using the parameter in a command.</span></span>
  - <span data-ttu-id="ca56d-131">При значении false значение параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ca56d-131">If false, the parameter value is optional.</span></span> <span data-ttu-id="ca56d-132">Как правило, значение является необязательным, только если оно является одним из нескольких допустимых значений для параметра, например в перечислимом типе.</span><span class="sxs-lookup"><span data-stu-id="ca56d-132">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="ca56d-133">**Обязательный** атрибут значения параметра отличается от **обязательного** атрибута параметра.</span><span class="sxs-lookup"><span data-stu-id="ca56d-133">The **Required** attribute of a parameter value is different from the **Required** attribute of a parameter.</span></span>

<span data-ttu-id="ca56d-134">Обязательный атрибут параметра указывает, следует ли включать параметр (и его значение) при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-134">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="ca56d-135">В отличие от этого, обязательный атрибут значения параметра используется только в том случае, если параметр включен в команду.</span><span class="sxs-lookup"><span data-stu-id="ca56d-135">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="ca56d-136">Указывает, следует ли использовать это конкретное значение с параметром.</span><span class="sxs-lookup"><span data-stu-id="ca56d-136">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="ca56d-137">Обычно значения параметров, которые являются заполнителями, являются обязательными, а значения параметров, являющиеся литералом, не являются обязательными, так как они являются одним из нескольких значений, которые могут использоваться с параметром.</span><span class="sxs-lookup"><span data-stu-id="ca56d-137">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="ca56d-138">Сбор сведений о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="ca56d-138">Gathering Syntax Information</span></span>

1. <span data-ttu-id="ca56d-139">Начните с имени командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-139">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

1. <span data-ttu-id="ca56d-140">Перечислите все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-140">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="ca56d-141">Введите дефис ( `-` ) (ASCII 45) перед именем каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="ca56d-141">Type a hyphen (`-`) (ASCII 45) before each parameter name.</span></span>
   <span data-ttu-id="ca56d-142">Разделите параметры на наборы параметров (некоторые командлеты могут иметь только один набор параметров).</span><span class="sxs-lookup"><span data-stu-id="ca56d-142">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="ca56d-143">В этом примере командлет Get-Tech имеет два набора параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-143">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="ca56d-144">Запустите каждый набор параметров с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-144">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="ca56d-145">Сначала укажите набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ca56d-145">List the default parameter set first.</span></span> <span data-ttu-id="ca56d-146">Параметр по умолчанию задается классом командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-146">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="ca56d-147">Для каждого набора параметров сначала укажите его уникальный параметр, если не существуют параметры, которые должны отображаться первыми.</span><span class="sxs-lookup"><span data-stu-id="ca56d-147">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="ca56d-148">В предыдущем примере параметры Name и ID являются уникальными параметрами для двух наборов параметров (каждый набор параметров должен иметь один параметр, уникальный для этого набора параметров).</span><span class="sxs-lookup"><span data-stu-id="ca56d-148">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="ca56d-149">Это упрощает пользователям определение того, какой параметр необходимо предоставить для набора параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-149">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="ca56d-150">Перечислите параметры в том порядке, в котором они должны отображаться в команде.</span><span class="sxs-lookup"><span data-stu-id="ca56d-150">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="ca56d-151">Если порядок не имеет значения, перечислите связанные параметры вместе или сначала перечислите наиболее часто используемые параметры.</span><span class="sxs-lookup"><span data-stu-id="ca56d-151">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="ca56d-152">Обязательно перечислите параметры WhatIf и Confirm, если командлет поддерживает ShouldProcess.</span><span class="sxs-lookup"><span data-stu-id="ca56d-152">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="ca56d-153">Не перечислите общие параметры (например, Verbose, Debug и ErrorAction) в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ca56d-153">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="ca56d-154">`Get-Help`Командлет добавляет эти сведения при отображении раздела справки.</span><span class="sxs-lookup"><span data-stu-id="ca56d-154">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

1. <span data-ttu-id="ca56d-155">Добавьте значения параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-155">Add the parameter values.</span></span> <span data-ttu-id="ca56d-156">В PowerShell значения параметров представлены их типом .NET.</span><span class="sxs-lookup"><span data-stu-id="ca56d-156">In PowerShell, parameter values are represented by their .NET type.</span></span>
   <span data-ttu-id="ca56d-157">Однако имя типа может быть сокращено, например "String" для System. String.</span><span class="sxs-lookup"><span data-stu-id="ca56d-157">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="ca56d-158">Сокращенные типы при условии, что их смысл является понятным, например **String** для **System. String** и **int** для **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="ca56d-158">Abbreviate types as long as their meaning is clear, such as **string** for **System.String** and **int** for **System.Int32**.</span></span>

   <span data-ttu-id="ca56d-159">Перечислите все значения перечислений, например `-type` параметр в предыдущем примере, для которого можно задать значение **Basic** или **Advanced**.</span><span class="sxs-lookup"><span data-stu-id="ca56d-159">List all values of enumerations, such as the `-type` parameter in the previous example, which can be set to **basic** or **advanced**.</span></span>

   <span data-ttu-id="ca56d-160">Параметры коммутатора, например, `-list` в предыдущем примере, не имеют значений.</span><span class="sxs-lookup"><span data-stu-id="ca56d-160">Switch parameters, such as `-list` in the previous example, do not have values.</span></span>

1. <span data-ttu-id="ca56d-161">Добавьте угловые скобки в значения параметров, которые являются заполнителями, по сравнению со значениями параметров, которые являются литералами.</span><span class="sxs-lookup"><span data-stu-id="ca56d-161">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

1. <span data-ttu-id="ca56d-162">Заключите необязательные параметры и их а также корректируются в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="ca56d-162">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="ca56d-163">Заключите имена необязательных параметров (для параметров позиционирования) в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="ca56d-163">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="ca56d-164">Имя для параметров, которые являются позиционированными, например параметр Name в следующем примере, не обязательно включать в команду.</span><span class="sxs-lookup"><span data-stu-id="ca56d-164">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="ca56d-165">Если значение параметра может содержать несколько значений, например список имен в параметре name, добавьте пару квадратных скобок непосредственно после значения параметра.</span><span class="sxs-lookup"><span data-stu-id="ca56d-165">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="ca56d-166">Если пользователь может выбрать один из параметров или значений параметров, например параметр типа, заключите варианты в фигурные скобки и разделите их символом или (;).</span><span class="sxs-lookup"><span data-stu-id="ca56d-166">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

1. <span data-ttu-id="ca56d-167">Если значение параметра должно использовать определенное форматирование, например кавычки или круглые скобки, то в синтаксисе отображается формат.</span><span class="sxs-lookup"><span data-stu-id="ca56d-167">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="ca56d-168">Кодирование XML-кода схемы синтаксиса</span><span class="sxs-lookup"><span data-stu-id="ca56d-168">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="ca56d-169">Узел синтаксиса XML начинается сразу после узла Description, который заканчивается `</maml:description>` тегом.</span><span class="sxs-lookup"><span data-stu-id="ca56d-169">The syntax node of the XML begins immediately after the description node, which ends with the `</maml:description>` tag.</span></span> <span data-ttu-id="ca56d-170">Сведения о сборе данных, используемых в схеме синтаксиса, см. в разделе [сбор сведений о синтаксисе](#gathering-syntax-information).</span><span class="sxs-lookup"><span data-stu-id="ca56d-170">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="ca56d-171">Добавление синтаксического узла</span><span class="sxs-lookup"><span data-stu-id="ca56d-171">Adding a Syntax Node</span></span>

<span data-ttu-id="ca56d-172">Схема синтаксиса, отображаемая в разделе справки по командлетам, создается на основе данных в узле синтаксиса XML.</span><span class="sxs-lookup"><span data-stu-id="ca56d-172">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="ca56d-173">Узел синтаксиса заключен в пары, если `<command:syntax>` теги.</span><span class="sxs-lookup"><span data-stu-id="ca56d-173">The syntax node is enclosed in a pair if `<command:syntax>` tags.</span></span> <span data-ttu-id="ca56d-174">С каждым набором параметров командлета, заключенного в пару `<command:syntaxitem>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ca56d-174">With each parameter set of the cmdlet enclosed in a pair of `<command:syntaxitem>` tags.</span></span> <span data-ttu-id="ca56d-175">Количество `<command:syntaxitem>` тегов, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="ca56d-175">There is no limit to the number of `<command:syntaxitem>` tags that you can add.</span></span>

<span data-ttu-id="ca56d-176">В следующем примере показан узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-176">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="ca56d-177">Добавление имени командлета в данные набора параметров</span><span class="sxs-lookup"><span data-stu-id="ca56d-177">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="ca56d-178">Каждый набор параметров командлета указывается в узле элемента синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ca56d-178">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="ca56d-179">Каждый узел элемента синтаксиса начинается с пары `<maml:name>` тегов, включающих имя командлета.</span><span class="sxs-lookup"><span data-stu-id="ca56d-179">Each syntax item node begins with a pair of `<maml:name>` tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="ca56d-180">Следующий пример включает узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="ca56d-180">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="ca56d-181">Добавление параметров</span><span class="sxs-lookup"><span data-stu-id="ca56d-181">Adding Parameters</span></span>

<span data-ttu-id="ca56d-182">Каждый параметр, добавляемый в узел элемента синтаксиса, указывается в паре `<command:parameter>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ca56d-182">Each parameter added to the syntax item node is specified within a pair of `<command:parameter>` tags.</span></span> <span data-ttu-id="ca56d-183">`<command:parameter>`Для каждого параметра, включенного в набор параметров, требуется пара тегов, за исключением общих параметров, предоставляемых PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca56d-183">You need a pair of `<command:parameter>` tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by PowerShell.</span></span>

<span data-ttu-id="ca56d-184">Атрибуты открывающего `<command:parameter>` тега определяют, как параметр отображается на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ca56d-184">The attributes of the opening `<command:parameter>` tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="ca56d-185">Дополнительные сведения об атрибутах параметров см. в разделе [атрибуты параметров](#parameter-attributes).</span><span class="sxs-lookup"><span data-stu-id="ca56d-185">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="ca56d-186">`<command:parameter>`Тег поддерживает дочерний элемент `<maml:description>` , содержимое которого никогда не отображается.</span><span class="sxs-lookup"><span data-stu-id="ca56d-186">The `<command:parameter>` tag supports a child element `<maml:description>` whose content is never displayed.</span></span> <span data-ttu-id="ca56d-187">Описания параметров указываются в узле параметров XML.</span><span class="sxs-lookup"><span data-stu-id="ca56d-187">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="ca56d-188">Чтобы избежать несоответствий между данными в элементе синтаксиса бодес и узлом Parameter, опустите ( `<maml:description>` или оставьте его пустым.</span><span class="sxs-lookup"><span data-stu-id="ca56d-188">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (`<maml:description>` or leave it empty.</span></span>

<span data-ttu-id="ca56d-189">Следующий пример включает узел элемента синтаксиса для набора параметров с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="ca56d-189">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
