---
title: Добавление динамических параметров в раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: cc4877242a16a9caa99564aeaae985f85e38791e
ms.sourcegitcommit: ffcc1c55f5b3adc063353cb75f2a2183acc2234a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70737598"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="1f61e-102">Как добавить динамические параметры в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="1f61e-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="1f61e-103">В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f61e-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="1f61e-104">*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.</span><span class="sxs-lookup"><span data-stu-id="1f61e-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="1f61e-105">Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f61e-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="1f61e-106">Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика.</span><span class="sxs-lookup"><span data-stu-id="1f61e-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="1f61e-107">При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.</span><span class="sxs-lookup"><span data-stu-id="1f61e-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span> <span data-ttu-id="1f61e-108">Дополнительные сведения о пользовательской справке по командлетам см. в разделе [Создание справки по пользовательскому командлету Windows PowerShell для поставщиков](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span><span class="sxs-lookup"><span data-stu-id="1f61e-108">For more information about custom cmdlet help, see [Writing Windows PowerShell Custom Cmdlet Help for Providers](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span></span>

<span data-ttu-id="1f61e-109">Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой `DynamicParameters` элемент.</span><span class="sxs-lookup"><span data-stu-id="1f61e-109">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="1f61e-110">Добавление динамических параметров</span><span class="sxs-lookup"><span data-stu-id="1f61e-110">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="1f61e-111">В `providerHelp` файле *AssemblyName*. длл-Хелп. XML в `DynamicParameters` элементе добавьте элемент.</span><span class="sxs-lookup"><span data-stu-id="1f61e-111">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="1f61e-112">Элемент должен располагаться `Tasks` после элемента и перед `RelatedLinks` элементом. `DynamicParameters`</span><span class="sxs-lookup"><span data-stu-id="1f61e-112">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="1f61e-113">Например:</span><span class="sxs-lookup"><span data-stu-id="1f61e-113">For example:</span></span>

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

   <span data-ttu-id="1f61e-114">Если поставщик не реализует динамические параметры, `DynamicParameters` элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="1f61e-114">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

2. <span data-ttu-id="1f61e-115">В элементе для каждого динамического параметра `DynamicParameter` добавьте элемент. `DynamicParameters`</span><span class="sxs-lookup"><span data-stu-id="1f61e-115">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="1f61e-116">Например:</span><span class="sxs-lookup"><span data-stu-id="1f61e-116">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. <span data-ttu-id="1f61e-117">В каждом `DynamicParameter` элементе `Name` добавьте элемент и `CmdletSupported` .</span><span class="sxs-lookup"><span data-stu-id="1f61e-117">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   |<span data-ttu-id="1f61e-118">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="1f61e-118">Element Name</span></span>|<span data-ttu-id="1f61e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1f61e-119">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="1f61e-120">Name</span><span class="sxs-lookup"><span data-stu-id="1f61e-120">Name</span></span>|<span data-ttu-id="1f61e-121">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-121">Specifies the parameter name.</span></span>|
   |<span data-ttu-id="1f61e-122">кмдлетсуппортед</span><span class="sxs-lookup"><span data-stu-id="1f61e-122">CmdletSupported</span></span>|<span data-ttu-id="1f61e-123">Указывает командлеты, в которых параметр является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1f61e-123">Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="1f61e-124">Введите разделенный запятыми список имен командлетов.</span><span class="sxs-lookup"><span data-stu-id="1f61e-124">Type a comma-separated list of cmdlet names.</span></span>|

   <span data-ttu-id="1f61e-125">Например, следующий `Encoding` XML-документ описывает динамический параметр, который поставщик FileSystem Windows PowerShell добавляет `Add-Content`в командлеты, `Get-Content`, `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="1f61e-125">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. <span data-ttu-id="1f61e-126">В каждом `DynamicParameter` элементе `Type` добавьте элемент.</span><span class="sxs-lookup"><span data-stu-id="1f61e-126">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="1f61e-127">Элемент является контейнером `Name` для элемента, который содержит тип .NET значения динамического параметра. `Type`</span><span class="sxs-lookup"><span data-stu-id="1f61e-127">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="1f61e-128">Например, следующий XML-код показывает, что тип `Encoding` .NET динамического параметра — это перечисление [Microsoft. PowerShell. Commands. филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .</span><span class="sxs-lookup"><span data-stu-id="1f61e-128">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

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

5. <span data-ttu-id="1f61e-129">`Description` Добавьте элемент, содержащий краткое описание динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-129">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="1f61e-130">При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="1f61e-130">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="1f61e-131">Например, следующий XML-код включает описание `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-131">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

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

6. <span data-ttu-id="1f61e-132">`PossibleValues` Добавьте элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="1f61e-132">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="1f61e-133">Вместе эти элементы описывают значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-133">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="1f61e-134">Этот элемент предназначен для перечислимых значений.</span><span class="sxs-lookup"><span data-stu-id="1f61e-134">This element is designed for enumerated values.</span></span> <span data-ttu-id="1f61e-135">Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.</span><span class="sxs-lookup"><span data-stu-id="1f61e-135">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="1f61e-136">В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="1f61e-136">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   |<span data-ttu-id="1f61e-137">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="1f61e-137">Element Name</span></span>|<span data-ttu-id="1f61e-138">Описание</span><span class="sxs-lookup"><span data-stu-id="1f61e-138">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="1f61e-139">поссиблевалуес</span><span class="sxs-lookup"><span data-stu-id="1f61e-139">PossibleValues</span></span>|<span data-ttu-id="1f61e-140">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="1f61e-140">This element is a container.</span></span> <span data-ttu-id="1f61e-141">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="1f61e-141">Its child elements are described below.</span></span> <span data-ttu-id="1f61e-142">Добавьте один `PossibleValues` элемент в каждый раздел справки по поставщику.</span><span class="sxs-lookup"><span data-stu-id="1f61e-142">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="1f61e-143">Элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="1f61e-143">The element can be empty.</span></span>|
   |<span data-ttu-id="1f61e-144">поссиблевалуе</span><span class="sxs-lookup"><span data-stu-id="1f61e-144">PossibleValue</span></span>|<span data-ttu-id="1f61e-145">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="1f61e-145">This element is a container.</span></span> <span data-ttu-id="1f61e-146">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="1f61e-146">Its child elements are described below.</span></span> <span data-ttu-id="1f61e-147">Добавьте по `PossibleValue` одному элементу для каждого значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-147">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>|
   |<span data-ttu-id="1f61e-148">Значение</span><span class="sxs-lookup"><span data-stu-id="1f61e-148">Value</span></span>|<span data-ttu-id="1f61e-149">Задает имя значения.</span><span class="sxs-lookup"><span data-stu-id="1f61e-149">Specifies the value name.</span></span>|
   |<span data-ttu-id="1f61e-150">Описание</span><span class="sxs-lookup"><span data-stu-id="1f61e-150">Description</span></span>|<span data-ttu-id="1f61e-151">Этот элемент содержит `Para` элемент.</span><span class="sxs-lookup"><span data-stu-id="1f61e-151">This element contains a `Para` element.</span></span> <span data-ttu-id="1f61e-152">Текст в `Para` элементе описывает значение, названное `Value` в элементе.</span><span class="sxs-lookup"><span data-stu-id="1f61e-152">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>|

   <span data-ttu-id="1f61e-153">Например, следующий XML-код показывает один `PossibleValue` элемент `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-153">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="1f61e-154">Пример</span><span class="sxs-lookup"><span data-stu-id="1f61e-154">Example</span></span>

<span data-ttu-id="1f61e-155">В следующем примере показан `DynamicParameters` элемент `Encoding` динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="1f61e-155">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

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