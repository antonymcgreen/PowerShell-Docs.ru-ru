---
ms.date: 09/13/2016
ms.topic: reference
title: Как добавить динамические параметры в раздел справки для поставщика
description: Как добавить динамические параметры в раздел справки для поставщика
ms.openlocfilehash: 9542538cfacf5fb293ca8d1350b80fb250c71ac6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649641"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="e4f76-103">Как добавить динамические параметры в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="e4f76-103">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="e4f76-104">В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4f76-104">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="e4f76-105">*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.</span><span class="sxs-lookup"><span data-stu-id="e4f76-105">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="e4f76-106">Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4f76-106">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="e4f76-107">Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4f76-107">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="e4f76-108">При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.</span><span class="sxs-lookup"><span data-stu-id="e4f76-108">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span>

<span data-ttu-id="e4f76-109">Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой `DynamicParameters` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-109">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="e4f76-110">Добавление динамических параметров</span><span class="sxs-lookup"><span data-stu-id="e4f76-110">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="e4f76-111">В `<AssemblyName>.dll-help.xml` файле в `providerHelp` элементе добавьте `DynamicParameters` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-111">In the `<AssemblyName>.dll-help.xml` file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="e4f76-112">`DynamicParameters`Элемент должен располагаться после `Tasks` элемента и перед `RelatedLinks` элементом.</span><span class="sxs-lookup"><span data-stu-id="e4f76-112">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="e4f76-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="e4f76-113">For example:</span></span>

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   <span data-ttu-id="e4f76-114">Если поставщик не реализует динамические параметры, `DynamicParameters` элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="e4f76-114">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

1. <span data-ttu-id="e4f76-115">В `DynamicParameters` элементе для каждого динамического параметра добавьте `DynamicParameter` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-115">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="e4f76-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="e4f76-116">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

1. <span data-ttu-id="e4f76-117">В каждом `DynamicParameter` элементе добавьте `Name` `CmdletSupported` элемент и.</span><span class="sxs-lookup"><span data-stu-id="e4f76-117">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   - <span data-ttu-id="e4f76-118">Имя — указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-118">Name - Specifies the parameter name</span></span>
   - <span data-ttu-id="e4f76-119">Кмдлетсуппортед — указывает командлеты, в которых параметр является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e4f76-119">CmdletSupported - Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="e4f76-120">Введите разделенный запятыми список имен командлетов.</span><span class="sxs-lookup"><span data-stu-id="e4f76-120">Type a comma-separated list of cmdlet names.</span></span>

   <span data-ttu-id="e4f76-121">Например, следующий XML-документ описывает `Encoding` динамический параметр, который поставщик FileSystem Windows PowerShell добавляет в `Add-Content` `Get-Content` командлеты,, `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="e4f76-121">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

1. <span data-ttu-id="e4f76-122">В каждом `DynamicParameter` элементе добавьте `Type` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-122">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="e4f76-123">`Type`Элемент является контейнером для `Name` элемента, который содержит тип .NET значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-123">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="e4f76-124">Например, в следующем XML-коде показано, что тип .NET `Encoding` динамического параметра — это перечисление [филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .</span><span class="sxs-lookup"><span data-stu-id="e4f76-124">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="e4f76-125">Добавьте `Description` элемент, содержащий краткое описание динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-125">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="e4f76-126">При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="e4f76-126">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="e4f76-127">Например, следующий XML-код включает описание `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-127">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="e4f76-128">Добавьте `PossibleValues` элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="e4f76-128">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="e4f76-129">Вместе эти элементы описывают значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-129">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="e4f76-130">Этот элемент предназначен для перечислимых значений.</span><span class="sxs-lookup"><span data-stu-id="e4f76-130">This element is designed for enumerated values.</span></span> <span data-ttu-id="e4f76-131">Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-131">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="e4f76-132">В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="e4f76-132">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   - <span data-ttu-id="e4f76-133">Поссиблевалуес — этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="e4f76-133">PossibleValues - This element is a container.</span></span> <span data-ttu-id="e4f76-134">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="e4f76-134">Its child elements are described below.</span></span> <span data-ttu-id="e4f76-135">Добавьте один `PossibleValues` элемент в каждый раздел справки по поставщику.</span><span class="sxs-lookup"><span data-stu-id="e4f76-135">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="e4f76-136">Элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="e4f76-136">The element can be empty.</span></span>
   - <span data-ttu-id="e4f76-137">Поссиблевалуе — этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="e4f76-137">PossibleValue - This element is a container.</span></span> <span data-ttu-id="e4f76-138">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="e4f76-138">Its child elements are described below.</span></span> <span data-ttu-id="e4f76-139">Добавьте `PossibleValue` по одному элементу для каждого значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-139">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>
   - <span data-ttu-id="e4f76-140">Значение — указывает имя значения.</span><span class="sxs-lookup"><span data-stu-id="e4f76-140">Value - Specifies the value name.</span></span>
   - <span data-ttu-id="e4f76-141">Описание — этот элемент содержит `Para` элемент.</span><span class="sxs-lookup"><span data-stu-id="e4f76-141">Description - This element contains a `Para` element.</span></span> <span data-ttu-id="e4f76-142">Текст в `Para` элементе описывает значение, названное в `Value` элементе.</span><span class="sxs-lookup"><span data-stu-id="e4f76-142">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>

   <span data-ttu-id="e4f76-143">Например, следующий XML-код показывает один `PossibleValue` элемент `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-143">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a><span data-ttu-id="e4f76-144">Пример</span><span class="sxs-lookup"><span data-stu-id="e4f76-144">Example</span></span>

<span data-ttu-id="e4f76-145">В следующем примере показан `DynamicParameters` элемент `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f76-145">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```
