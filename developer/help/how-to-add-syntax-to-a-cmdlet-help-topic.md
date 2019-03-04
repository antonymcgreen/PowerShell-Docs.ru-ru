---
title: Как добавить синтаксис для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c6d03f-1c1a-43d8-928e-e3290e90e0bc
caps.latest.revision: 5
ms.openlocfilehash: 947d0c0188df5bba3a9fb617fe5abf0b3b28eb51
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858000"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="01947-102">Как добавить синтаксис в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="01947-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

- [<span data-ttu-id="01947-103">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="01947-103">Parameter Attributes</span></span>](#Parameter-Attributes)

- [<span data-ttu-id="01947-104">Атрибуты значение параметра</span><span class="sxs-lookup"><span data-stu-id="01947-104">Parameter Value Attributes</span></span>](#Parameter-Value-Attributes)

- [<span data-ttu-id="01947-105">Сбор сведений о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="01947-105">Gathering Syntax Information</span></span>](#Gathering-Syntax-Information)

- [<span data-ttu-id="01947-106">Кодирование на схеме синтаксиса XML</span><span class="sxs-lookup"><span data-stu-id="01947-106">Coding the Syntax Diagram XML</span></span>](#Coding-the-Syntax-Diagram-XML)

## <a name="things-to-know-about-the-syntax-diagram-in-cmdlet-help"></a><span data-ttu-id="01947-107">Что нужно знать о диаграмма синтаксиса в справку по командлетам</span><span class="sxs-lookup"><span data-stu-id="01947-107">Things to Know About the Syntax Diagram in Cmdlet Help</span></span>

<span data-ttu-id="01947-108">Перед началом кода XML для диаграмма синтаксиса в файле справки командлета, ознакомьтесь с этим разделом, чтобы получить четкое представление о какие данные необходимо предоставить, такую как атрибуты параметров и отображения этих данных на схеме синтаксиса...</span><span class="sxs-lookup"><span data-stu-id="01947-108">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

### <a name="parameter-attributes"></a><span data-ttu-id="01947-109">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="01947-109">Parameter Attributes</span></span>

- <span data-ttu-id="01947-110">Обязательный</span><span class="sxs-lookup"><span data-stu-id="01947-110">Required</span></span>

  - <span data-ttu-id="01947-111">Если значение равно true, параметр должен указываться во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-111">If true, the parameter must appear in all commands that use the parameter set.</span></span>

  - <span data-ttu-id="01947-112">Если значение равно false, то параметр является необязательным во всех командах, использующих набор параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-112">If false, the parameter is optional in all commands that use the parameter set.</span></span>

- <span data-ttu-id="01947-113">положение</span><span class="sxs-lookup"><span data-stu-id="01947-113">Position</span></span>

  - <span data-ttu-id="01947-114">Если с именем, имя параметра не требуется.</span><span class="sxs-lookup"><span data-stu-id="01947-114">If named, the parameter name is required.</span></span>

  - <span data-ttu-id="01947-115">Если позиционные, имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="01947-115">If positional, the parameter name is optional.</span></span> <span data-ttu-id="01947-116">Если опущено, значение параметра должно быть в указанной позиции в команде.</span><span class="sxs-lookup"><span data-stu-id="01947-116">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="01947-117">Например, если значение равно позиции = «1», значение параметра должен быть первый или только неименованные значение параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="01947-117">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>

- <span data-ttu-id="01947-118">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="01947-118">Pipeline Input</span></span>

  - <span data-ttu-id="01947-119">Если значение равно true (ByValue), можно передать по конвейеру входные данные для параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-119">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="01947-120">Входные данные, связанные с («граница») даже в том случае, если имя свойства и тип объекта не соответствует ожидаемому типу параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-120">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span> <span data-ttu-id="01947-121">Windows PowerShell? компоненты привязки параметра попробуйте преобразовать входные данные для правильного типа и завершает команду со сбоем только в том случае, если тип не может быть преобразован.</span><span class="sxs-lookup"><span data-stu-id="01947-121">The Windows PowerShell? parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="01947-122">Может быть связан только один параметр в набор параметров по значению.</span><span class="sxs-lookup"><span data-stu-id="01947-122">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="01947-123">Если значение равно true (ByPropertyName), можно передать по конвейеру входные данные для параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-123">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="01947-124">Тем не менее входных данных связан с параметром, только в том случае, если имя параметра соответствует имени свойства входного объекта.</span><span class="sxs-lookup"><span data-stu-id="01947-124">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="01947-125">Например, если имя параметра является `Path`, объекты по конвейеру в командлет связаны с этот параметр только в том случае, если объект имеет свойство с именем пути.</span><span class="sxs-lookup"><span data-stu-id="01947-125">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>

  - <span data-ttu-id="01947-126">Если значение true (ByValue, ByPropertyName), можно передать по конвейеру входные данные для параметра по значению или по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="01947-126">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="01947-127">Может быть связан только один параметр в набор параметров по значению.</span><span class="sxs-lookup"><span data-stu-id="01947-127">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="01947-128">Если значение равно false, нельзя передать входные данные для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-128">If false, you cannot pipe input to this parameter.</span></span>

- <span data-ttu-id="01947-129">Глобализации</span><span class="sxs-lookup"><span data-stu-id="01947-129">Globbing</span></span>

  - <span data-ttu-id="01947-130">Если значение равно true, текст, который пользователь вводит для значения параметра может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="01947-130">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>

  - <span data-ttu-id="01947-131">Если значение равно false, текст, который пользователь вводит для значения параметра не может содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="01947-131">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="01947-132">Атрибуты значение параметра</span><span class="sxs-lookup"><span data-stu-id="01947-132">Parameter Value Attributes</span></span>

- <span data-ttu-id="01947-133">Обязательный</span><span class="sxs-lookup"><span data-stu-id="01947-133">Required</span></span>

  - <span data-ttu-id="01947-134">Значение true, если указанное значение должно использоваться всякий раз, когда с помощью параметра в команде.</span><span class="sxs-lookup"><span data-stu-id="01947-134">If true, the specified value must be used whenever using the parameter in a command.</span></span>

  - <span data-ttu-id="01947-135">Если значение равно false, значение параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="01947-135">If false, the parameter value is optional.</span></span> <span data-ttu-id="01947-136">Как правило значение является необязательным, только если это одно из нескольких допустимых значений для параметра, например в перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="01947-136">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="01947-137">Необходимый атрибут значение параметра отличается от обязательный атрибут параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-137">The Required attribute of a parameter value is different from the Required attribute of a parameter.</span></span>

<span data-ttu-id="01947-138">Обязательный атрибут параметра указывает, является ли параметр (и его значение) должен быть включен при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-138">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="01947-139">Напротив необходимый атрибут значение параметра используется только в том случае, если параметр включен в команду.</span><span class="sxs-lookup"><span data-stu-id="01947-139">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="01947-140">Он указывает, следует ли использовать с параметром, определенное значение.</span><span class="sxs-lookup"><span data-stu-id="01947-140">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="01947-141">Как правило значения параметров, которые представляют собой заполнители являются обязательными, и значения параметров, которые являются литералами не требуются, так как они являются одной из нескольких значений, которые могут использоваться с параметром.</span><span class="sxs-lookup"><span data-stu-id="01947-141">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="01947-142">Сбор сведений о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="01947-142">Gathering Syntax Information</span></span>

1. <span data-ttu-id="01947-143">Начинается с имени командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-143">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

2. <span data-ttu-id="01947-144">Перечислите все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-144">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="01947-145">Введите тире (также известная как «тире» или «минус» (ASCII 45) перед именем параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-145">Type a dash (also known as a "dash" or "minus sign" (ASCII 45) before each parameter name.</span></span> <span data-ttu-id="01947-146">Параметры разделения на наборы параметров (в некоторых командлетов может иметь только один набор параметров).</span><span class="sxs-lookup"><span data-stu-id="01947-146">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="01947-147">В этом примере Get-Технический командлет имеет два набора параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-147">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="01947-148">Запуск каждого параметра набор с именем командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-148">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="01947-149">Этот параметр по умолчанию, сначала задать в список.</span><span class="sxs-lookup"><span data-stu-id="01947-149">List the default parameter set first.</span></span> <span data-ttu-id="01947-150">Этот параметр по умолчанию указан в классе командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-150">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="01947-151">Для каждого набора параметров список ее уникальный параметр во-первых, только при наличии позиционные параметры, которые должно быть первым.</span><span class="sxs-lookup"><span data-stu-id="01947-151">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="01947-152">В предыдущем примере, имя и идентификатор равны уникальные параметры для двух наборов параметров (каждый набор параметров должен иметь один параметр, который уникален в этот набор параметров).</span><span class="sxs-lookup"><span data-stu-id="01947-152">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="01947-153">Это упрощает для пользователей определить, какой параметр, им нужно указать для параметра значение.</span><span class="sxs-lookup"><span data-stu-id="01947-153">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="01947-154">Вывести список параметров в порядке, в котором они должны располагаться в команде.</span><span class="sxs-lookup"><span data-stu-id="01947-154">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="01947-155">Если порядок не имеет значения, перечислены параметры, связанные друг с другом, или сначала перечислите наиболее часто используемые параметры.</span><span class="sxs-lookup"><span data-stu-id="01947-155">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="01947-156">Убедитесь, что перечислены параметры WhatIf и Confirm в том случае, если командлет поддерживает метод ShouldProcess.</span><span class="sxs-lookup"><span data-stu-id="01947-156">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="01947-157">Не указывайте Общие параметры (например, Verbose, Debug и ErrorAction) в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="01947-157">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="01947-158">`Get-Help` Командлет добавляет эту информацию для вас, когда он отображает раздел справки.</span><span class="sxs-lookup"><span data-stu-id="01947-158">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

3. <span data-ttu-id="01947-159">Добавьте значения параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-159">Add the parameter values.</span></span> <span data-ttu-id="01947-160">В Windows PowerShell?, значения параметров, представлены по типу .NET.</span><span class="sxs-lookup"><span data-stu-id="01947-160">In Windows PowerShell?, parameter values are represented by their .NET type.</span></span> <span data-ttu-id="01947-161">Тем не менее имя типа можно сократить, такие как «string» для System.String.</span><span class="sxs-lookup"><span data-stu-id="01947-161">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="01947-162">Использование вместо типов до тех пор, пока их значение становится ясно, такие как «string» для System.String и «int» для System.Int32.</span><span class="sxs-lookup"><span data-stu-id="01947-162">Abbreviate types as long as their meaning is clear, such as "string" for System.String and "int" for System.Int32.</span></span>

   <span data-ttu-id="01947-163">Список всех значений перечисления, такие как тип параметра - в предыдущем примере, который может быть присвоено «базовый» или «расширенный».</span><span class="sxs-lookup"><span data-stu-id="01947-163">List all values of enumerations, such as the -type parameter in the previous example, wich can be set to "basic" or "advanced".</span></span>

   <span data-ttu-id="01947-164">Переключение параметров, таких как - список в предыдущем примере, не имеют значений.</span><span class="sxs-lookup"><span data-stu-id="01947-164">Switch parameters, such as -list in the previous example, do not have values.</span></span>

4. <span data-ttu-id="01947-165">Добавьте значения параметров, которые являются заполнитель, по сравнению с значения параметров, которые являются литералами угловые скобки.</span><span class="sxs-lookup"><span data-stu-id="01947-165">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. <span data-ttu-id="01947-166">Заключите необязательные параметры и их значения в квадратных скобках.</span><span class="sxs-lookup"><span data-stu-id="01947-166">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. <span data-ttu-id="01947-167">Имена необязательных параметров (для позиционных параметров), следует заключайте в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="01947-167">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="01947-168">Имя для параметров, которые являются позиционными, такие как имя параметра в следующем примере, нет необходимости включается в команду.</span><span class="sxs-lookup"><span data-stu-id="01947-168">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. <span data-ttu-id="01947-169">Если значение параметра может содержать несколько значений, таких как список имен в параметре Name, добавьте пару квадратных скобках непосредственно после значения параметра.</span><span class="sxs-lookup"><span data-stu-id="01947-169">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. <span data-ttu-id="01947-170">Если пользователь может выбрать из параметров или значений параметров, таких как параметр типа, заключите варианты в фигурные скобки, разделив их эксклюзивное symbol(;) OR.</span><span class="sxs-lookup"><span data-stu-id="01947-170">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. <span data-ttu-id="01947-171">Если значение параметра необходимо использовать определенное форматирование, например двойных кавычек или фигурных скобок, представления формата в синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="01947-171">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="01947-172">Кодирование на схеме синтаксиса XML</span><span class="sxs-lookup"><span data-stu-id="01947-172">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="01947-173">Узел синтаксиса XML-начинается сразу после описания узла, который заканчивается \</maml:description > тег.</span><span class="sxs-lookup"><span data-stu-id="01947-173">The syntax node of the XML begins immediately after the description node, which ends with the \</maml:description> tag.</span></span> <span data-ttu-id="01947-174">Сведения о сборе данных, используемых на схеме синтаксиса см. в разделе [собирать сведения о синтаксисе](#Gathering-Syntax-Information).</span><span class="sxs-lookup"><span data-stu-id="01947-174">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#Gathering-Syntax-Information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="01947-175">Добавление узла синтаксиса</span><span class="sxs-lookup"><span data-stu-id="01947-175">Adding a Syntax Node</span></span>

<span data-ttu-id="01947-176">На схеме синтаксиса, отображаются в разделах справки создается на основе данных в узле синтаксис XML.</span><span class="sxs-lookup"><span data-stu-id="01947-176">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="01947-177">Узел синтаксиса заключается в пару, если \<синтаксис команды: > теги.</span><span class="sxs-lookup"><span data-stu-id="01947-177">The syntax node is enclosed in a pair if \<command:syntax> tags.</span></span> <span data-ttu-id="01947-178">С каждым набором параметров командлета, заключенный в паре \<команда: syntaxitem > теги.</span><span class="sxs-lookup"><span data-stu-id="01947-178">With each parameter set of the cmdlet enclosed in a pair of \<command:syntaxitem> tags.</span></span> <span data-ttu-id="01947-179">Нет ограничений на число \<команда: syntaxitem > теги, которые могут быть добавлены.</span><span class="sxs-lookup"><span data-stu-id="01947-179">There is no limit to the number of \<command:syntaxitem> tags that you can add.</span></span>

<span data-ttu-id="01947-180">В следующем примере показано синтаксис узел, содержащий синтаксические узлы элемента для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-180">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="01947-181">Добавление имени командлета в параметре набор данных</span><span class="sxs-lookup"><span data-stu-id="01947-181">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="01947-182">Каждый набор параметров командлета указывается в узле элемента синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="01947-182">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="01947-183">Каждый узел синтаксиса элемента начинается с пары \<maml:name > теги, которые включают это имя командлета.</span><span class="sxs-lookup"><span data-stu-id="01947-183">Each syntax item node begins with a pair of \<maml:name> tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="01947-184">Следующий пример включает синтаксис узел, содержащий синтаксические узлы элемента для двух наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="01947-184">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="01947-185">Добавление параметров</span><span class="sxs-lookup"><span data-stu-id="01947-185">Adding Parameters</span></span>

<span data-ttu-id="01947-186">Каждый параметр, добавляемый узел синтаксического элемента указанного в пару \<: параметр команды > теги.</span><span class="sxs-lookup"><span data-stu-id="01947-186">Each parameter added to the syntax item node is specified within a pair of \<command:parameter> tags.</span></span> <span data-ttu-id="01947-187">Нужно выделять пару \<: параметр команды > теги для каждого параметра, включенные в набор параметров, за исключением Общие параметры, предоставляемые Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="01947-187">You need a pair of \<command:parameter> tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by Windows PowerShell?.</span></span>

<span data-ttu-id="01947-188">Атрибуты открывающего \<: параметр команды > тег определяют, как параметр появляется на схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="01947-188">The attributes of the opening \<command:parameter> tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="01947-189">Сведения об атрибутах параметров, см. в разделе [атрибуты параметра](#Parameter-Attributes).</span><span class="sxs-lookup"><span data-stu-id="01947-189">For information on parameter attributes, see [Parameter Attributes](#Parameter-Attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="01947-190">\<: Параметр команды > тег поддерживает дочерний элемент \<maml:description >, содержимое которых никогда не отображается.</span><span class="sxs-lookup"><span data-stu-id="01947-190">The \<command:parameter> tag supports a child element \<maml:description> whose content is never displayed.</span></span> <span data-ttu-id="01947-191">Описания параметров указываются в узле параметра XML.</span><span class="sxs-lookup"><span data-stu-id="01947-191">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="01947-192">Чтобы избежать несогласованности между данными в синтаксис элемента проект и узел параметра, опустите (\<maml:description > или оставьте его пустым.</span><span class="sxs-lookup"><span data-stu-id="01947-192">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (\<maml:description> or leave it empty.</span></span>

<span data-ttu-id="01947-193">Следующий пример включает узел элемента синтаксиса для параметров с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="01947-193">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
