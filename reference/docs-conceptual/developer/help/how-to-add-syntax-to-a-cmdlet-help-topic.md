---
title: Как добавить синтаксис в раздел справки для командлета
ms.date: 09/12/2016
ms.openlocfilehash: 3457341a577b283bf3da5dc010de9bbbb36b78d2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893056"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="dad5d-102">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="dad5d-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="dad5d-103">Прежде чем начать код XML для схемы синтаксиса в файле справки по командлетам, прочтите этот раздел, чтобы получить четкое представление о типе данных, которые необходимо предоставить, например атрибуты параметров, а также способ отображения данных на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dad5d-103">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="dad5d-104">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="dad5d-104">Parameter Attributes</span></span>

- <span data-ttu-id="dad5d-105">Обязательное</span><span class="sxs-lookup"><span data-stu-id="dad5d-105">Required</span></span>
  - <span data-ttu-id="dad5d-106">Если значение — true, параметр должен отображаться во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-106">If true, the parameter must appear in all commands that use the parameter set.</span></span>
  - <span data-ttu-id="dad5d-107">Если значение равно false, параметр является необязательным во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-107">If false, the parameter is optional in all commands that use the parameter set.</span></span>
- <span data-ttu-id="dad5d-108">Положение</span><span class="sxs-lookup"><span data-stu-id="dad5d-108">Position</span></span>
  - <span data-ttu-id="dad5d-109">Если задано имя, необходимо указать параметр Name.</span><span class="sxs-lookup"><span data-stu-id="dad5d-109">If named, the parameter name is required.</span></span>
  - <span data-ttu-id="dad5d-110">При позиционировании имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dad5d-110">If positional, the parameter name is optional.</span></span> <span data-ttu-id="dad5d-111">Если он не указан, значение параметра должно находиться в указанной положении в команде.</span><span class="sxs-lookup"><span data-stu-id="dad5d-111">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="dad5d-112">Например, если значение равно "1", значение параметра должно быть первым или единственным неименованным значением параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="dad5d-112">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>
- <span data-ttu-id="dad5d-113">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="dad5d-113">Pipeline Input</span></span>
  - <span data-ttu-id="dad5d-114">Если true (Бивалуе), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="dad5d-114">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="dad5d-115">Входные данные связаны с параметром ("привязано к"), даже если имя свойства и тип объекта не соответствуют ожидаемому типу.</span><span class="sxs-lookup"><span data-stu-id="dad5d-115">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span>
    <span data-ttu-id="dad5d-116">Компоненты привязки параметров PowerShell пытаются преобразовать входные данные в правильный тип и завершить команду только в том случае, если тип не может быть преобразован.</span><span class="sxs-lookup"><span data-stu-id="dad5d-116">The PowerShell parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="dad5d-117">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="dad5d-117">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="dad5d-118">Если true (Бипропертинаме), можно передать входные данные в параметр.</span><span class="sxs-lookup"><span data-stu-id="dad5d-118">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="dad5d-119">Однако входные данные связываются с параметром только в том случае, если имя параметра совпадает с именем свойства входного объекта.</span><span class="sxs-lookup"><span data-stu-id="dad5d-119">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="dad5d-120">Например, если имя параметра — `Path` , объекты, переданный в командлет, связываются с этим параметром только в том случае, если у объекта есть свойство с именем path.</span><span class="sxs-lookup"><span data-stu-id="dad5d-120">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>
  - <span data-ttu-id="dad5d-121">Если true (Бивалуе, Бипропертинаме), можно передать входные данные в параметр по имени свойства или по значению.</span><span class="sxs-lookup"><span data-stu-id="dad5d-121">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="dad5d-122">Только один параметр в наборе параметров может быть связан по значению.</span><span class="sxs-lookup"><span data-stu-id="dad5d-122">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="dad5d-123">Если значение равно false, нельзя передавать входные данные в этот параметр.</span><span class="sxs-lookup"><span data-stu-id="dad5d-123">If false, you cannot pipe input to this parameter.</span></span>
- <span data-ttu-id="dad5d-124">Глобализации</span><span class="sxs-lookup"><span data-stu-id="dad5d-124">Globbing</span></span>
  - <span data-ttu-id="dad5d-125">Если значение — true, текст, который пользователь вводит в качестве значения параметра, может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="dad5d-125">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>
  - <span data-ttu-id="dad5d-126">Если значение равно false, то текст, который пользователь вводит в качестве значения параметра, не может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="dad5d-126">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="dad5d-127">Атрибуты значения параметра</span><span class="sxs-lookup"><span data-stu-id="dad5d-127">Parameter Value Attributes</span></span>

- <span data-ttu-id="dad5d-128">Обязательное</span><span class="sxs-lookup"><span data-stu-id="dad5d-128">Required</span></span>
  - <span data-ttu-id="dad5d-129">Если значение — true, указанное значение должно использоваться при использовании параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="dad5d-129">If true, the specified value must be used whenever using the parameter in a command.</span></span>
  - <span data-ttu-id="dad5d-130">При значении false значение параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dad5d-130">If false, the parameter value is optional.</span></span> <span data-ttu-id="dad5d-131">Как правило, значение является необязательным, только если оно является одним из нескольких допустимых значений для параметра, например в перечислимом типе.</span><span class="sxs-lookup"><span data-stu-id="dad5d-131">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="dad5d-132">**Обязательный** атрибут значения параметра отличается от **обязательного** атрибута параметра.</span><span class="sxs-lookup"><span data-stu-id="dad5d-132">The **Required** attribute of a parameter value is different from the **Required** attribute of a parameter.</span></span>

<span data-ttu-id="dad5d-133">Обязательный атрибут параметра указывает, следует ли включать параметр (и его значение) при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-133">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="dad5d-134">В отличие от этого, обязательный атрибут значения параметра используется только в том случае, если параметр включен в команду.</span><span class="sxs-lookup"><span data-stu-id="dad5d-134">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="dad5d-135">Указывает, следует ли использовать это конкретное значение с параметром.</span><span class="sxs-lookup"><span data-stu-id="dad5d-135">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="dad5d-136">Обычно значения параметров, которые являются заполнителями, являются обязательными, а значения параметров, являющиеся литералом, не являются обязательными, так как они являются одним из нескольких значений, которые могут использоваться с параметром.</span><span class="sxs-lookup"><span data-stu-id="dad5d-136">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="dad5d-137">Сбор сведений о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="dad5d-137">Gathering Syntax Information</span></span>

1. <span data-ttu-id="dad5d-138">Начните с имени командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-138">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

1. <span data-ttu-id="dad5d-139">Перечислите все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-139">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="dad5d-140">Введите дефис ( `-` ) (ASCII 45) перед именем каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="dad5d-140">Type a hyphen (`-`) (ASCII 45) before each parameter name.</span></span>
   <span data-ttu-id="dad5d-141">Разделите параметры на наборы параметров (некоторые командлеты могут иметь только один набор параметров).</span><span class="sxs-lookup"><span data-stu-id="dad5d-141">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="dad5d-142">В этом примере командлет Get-Tech имеет два набора параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-142">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="dad5d-143">Запустите каждый набор параметров с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-143">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="dad5d-144">Сначала укажите набор параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dad5d-144">List the default parameter set first.</span></span> <span data-ttu-id="dad5d-145">Параметр по умолчанию задается классом командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-145">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="dad5d-146">Для каждого набора параметров сначала укажите его уникальный параметр, если не существуют параметры, которые должны отображаться первыми.</span><span class="sxs-lookup"><span data-stu-id="dad5d-146">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="dad5d-147">В предыдущем примере параметры Name и ID являются уникальными параметрами для двух наборов параметров (каждый набор параметров должен иметь один параметр, уникальный для этого набора параметров).</span><span class="sxs-lookup"><span data-stu-id="dad5d-147">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="dad5d-148">Это упрощает пользователям определение того, какой параметр необходимо предоставить для набора параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-148">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="dad5d-149">Перечислите параметры в том порядке, в котором они должны отображаться в команде.</span><span class="sxs-lookup"><span data-stu-id="dad5d-149">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="dad5d-150">Если порядок не имеет значения, перечислите связанные параметры вместе или сначала перечислите наиболее часто используемые параметры.</span><span class="sxs-lookup"><span data-stu-id="dad5d-150">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="dad5d-151">Обязательно перечислите параметры WhatIf и Confirm, если командлет поддерживает ShouldProcess.</span><span class="sxs-lookup"><span data-stu-id="dad5d-151">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="dad5d-152">Не перечислите общие параметры (например, Verbose, Debug и ErrorAction) в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dad5d-152">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="dad5d-153">`Get-Help`Командлет добавляет эти сведения при отображении раздела справки.</span><span class="sxs-lookup"><span data-stu-id="dad5d-153">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

1. <span data-ttu-id="dad5d-154">Добавьте значения параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-154">Add the parameter values.</span></span> <span data-ttu-id="dad5d-155">В PowerShell значения параметров представлены их типом .NET.</span><span class="sxs-lookup"><span data-stu-id="dad5d-155">In PowerShell, parameter values are represented by their .NET type.</span></span>
   <span data-ttu-id="dad5d-156">Однако имя типа может быть сокращено, например "String" для System. String.</span><span class="sxs-lookup"><span data-stu-id="dad5d-156">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="dad5d-157">Сокращенные типы при условии, что их смысл является понятным, например **String** для **System. String** и **int** для **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="dad5d-157">Abbreviate types as long as their meaning is clear, such as **string** for **System.String** and **int** for **System.Int32**.</span></span>

   <span data-ttu-id="dad5d-158">Перечислите все значения перечислений, например `-type` параметр в предыдущем примере, для которого можно задать значение **Basic** или **Advanced**.</span><span class="sxs-lookup"><span data-stu-id="dad5d-158">List all values of enumerations, such as the `-type` parameter in the previous example, which can be set to **basic** or **advanced**.</span></span>

   <span data-ttu-id="dad5d-159">Параметры коммутатора, например, `-list` в предыдущем примере, не имеют значений.</span><span class="sxs-lookup"><span data-stu-id="dad5d-159">Switch parameters, such as `-list` in the previous example, do not have values.</span></span>

1. <span data-ttu-id="dad5d-160">Добавьте угловые скобки в значения параметров, которые являются заполнителями, по сравнению со значениями параметров, которые являются литералами.</span><span class="sxs-lookup"><span data-stu-id="dad5d-160">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

1. <span data-ttu-id="dad5d-161">Заключите необязательные параметры и их а также корректируются в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="dad5d-161">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="dad5d-162">Заключите имена необязательных параметров (для параметров позиционирования) в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="dad5d-162">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="dad5d-163">Имя для параметров, которые являются позиционированными, например параметр Name в следующем примере, не обязательно включать в команду.</span><span class="sxs-lookup"><span data-stu-id="dad5d-163">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="dad5d-164">Если значение параметра может содержать несколько значений, например список имен в параметре name, добавьте пару квадратных скобок непосредственно после значения параметра.</span><span class="sxs-lookup"><span data-stu-id="dad5d-164">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="dad5d-165">Если пользователь может выбрать один из параметров или значений параметров, например параметр типа, заключите варианты в фигурные скобки и разделите их символом или (;).</span><span class="sxs-lookup"><span data-stu-id="dad5d-165">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

1. <span data-ttu-id="dad5d-166">Если значение параметра должно использовать определенное форматирование, например кавычки или круглые скобки, то в синтаксисе отображается формат.</span><span class="sxs-lookup"><span data-stu-id="dad5d-166">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="dad5d-167">Кодирование XML-кода схемы синтаксиса</span><span class="sxs-lookup"><span data-stu-id="dad5d-167">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="dad5d-168">Узел синтаксиса XML начинается сразу после узла Description, который заканчивается `</maml:description>` тегом.</span><span class="sxs-lookup"><span data-stu-id="dad5d-168">The syntax node of the XML begins immediately after the description node, which ends with the `</maml:description>` tag.</span></span> <span data-ttu-id="dad5d-169">Сведения о сборе данных, используемых в схеме синтаксиса, см. в разделе [сбор сведений о синтаксисе](#gathering-syntax-information).</span><span class="sxs-lookup"><span data-stu-id="dad5d-169">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="dad5d-170">Добавление синтаксического узла</span><span class="sxs-lookup"><span data-stu-id="dad5d-170">Adding a Syntax Node</span></span>

<span data-ttu-id="dad5d-171">Схема синтаксиса, отображаемая в разделе справки по командлетам, создается на основе данных в узле синтаксиса XML.</span><span class="sxs-lookup"><span data-stu-id="dad5d-171">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="dad5d-172">Узел синтаксиса заключен в пары, если `<command:syntax>` теги.</span><span class="sxs-lookup"><span data-stu-id="dad5d-172">The syntax node is enclosed in a pair if `<command:syntax>` tags.</span></span> <span data-ttu-id="dad5d-173">С каждым набором параметров командлета, заключенного в пару `<command:syntaxitem>` тегов.</span><span class="sxs-lookup"><span data-stu-id="dad5d-173">With each parameter set of the cmdlet enclosed in a pair of `<command:syntaxitem>` tags.</span></span> <span data-ttu-id="dad5d-174">Количество `<command:syntaxitem>` тегов, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="dad5d-174">There is no limit to the number of `<command:syntaxitem>` tags that you can add.</span></span>

<span data-ttu-id="dad5d-175">В следующем примере показан узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-175">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="dad5d-176">Добавление имени командлета в данные набора параметров</span><span class="sxs-lookup"><span data-stu-id="dad5d-176">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="dad5d-177">Каждый набор параметров командлета указывается в узле элемента синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dad5d-177">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="dad5d-178">Каждый узел элемента синтаксиса начинается с пары `<maml:name>` тегов, включающих имя командлета.</span><span class="sxs-lookup"><span data-stu-id="dad5d-178">Each syntax item node begins with a pair of `<maml:name>` tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="dad5d-179">Следующий пример включает узел синтаксиса, который содержит узлы элементов синтаксиса для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="dad5d-179">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="dad5d-180">Добавление параметров</span><span class="sxs-lookup"><span data-stu-id="dad5d-180">Adding Parameters</span></span>

<span data-ttu-id="dad5d-181">Каждый параметр, добавляемый в узел элемента синтаксиса, указывается в паре `<command:parameter>` тегов.</span><span class="sxs-lookup"><span data-stu-id="dad5d-181">Each parameter added to the syntax item node is specified within a pair of `<command:parameter>` tags.</span></span> <span data-ttu-id="dad5d-182">`<command:parameter>`Для каждого параметра, включенного в набор параметров, требуется пара тегов, за исключением общих параметров, предоставляемых PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dad5d-182">You need a pair of `<command:parameter>` tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by PowerShell.</span></span>

<span data-ttu-id="dad5d-183">Атрибуты открывающего `<command:parameter>` тега определяют, как параметр отображается на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dad5d-183">The attributes of the opening `<command:parameter>` tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="dad5d-184">Дополнительные сведения об атрибутах параметров см. в разделе [атрибуты параметров](#parameter-attributes).</span><span class="sxs-lookup"><span data-stu-id="dad5d-184">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="dad5d-185">`<command:parameter>`Тег поддерживает дочерний элемент `<maml:description>` , содержимое которого никогда не отображается.</span><span class="sxs-lookup"><span data-stu-id="dad5d-185">The `<command:parameter>` tag supports a child element `<maml:description>` whose content is never displayed.</span></span> <span data-ttu-id="dad5d-186">Описания параметров указываются в узле параметров XML.</span><span class="sxs-lookup"><span data-stu-id="dad5d-186">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="dad5d-187">Чтобы избежать несоответствий между данными в элементе синтаксиса бодес и узлом Parameter, опустите ( `<maml:description>` или оставьте его пустым.</span><span class="sxs-lookup"><span data-stu-id="dad5d-187">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (`<maml:description>` or leave it empty.</span></span>

<span data-ttu-id="dad5d-188">Следующий пример включает узел элемента синтаксиса для набора параметров с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="dad5d-188">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
