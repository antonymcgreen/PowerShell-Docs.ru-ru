---
title: Как добавить динамические параметры в раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: cc4877242a16a9caa99564aeaae985f85e38791e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859880"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="d1142-102">Как добавить динамические параметры в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="d1142-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="d1142-103">В этом разделе объясняется, как для заполнения **ДИНАМИЧЕСКИХ параметров** раздела справки на поставщика.</span><span class="sxs-lookup"><span data-stu-id="d1142-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="d1142-104">*Динамические параметры* параметров командлета или функции, которые доступны только при выполнении указанных условий.</span><span class="sxs-lookup"><span data-stu-id="d1142-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="d1142-105">Динамические параметры, которые описаны в разделе справки поставщика являются динамические параметры, которые поставщик добавляет в командлет или функцию, при использовании командлета или функции на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="d1142-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="d1142-106">Динамические параметры можно также задокументировать в справке пользовательского командлета для поставщика.</span><span class="sxs-lookup"><span data-stu-id="d1142-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="d1142-107">При написании справки о поставщике и Справка пользовательского командлета для поставщика, включить в документации динамический параметр обоих документов.</span><span class="sxs-lookup"><span data-stu-id="d1142-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span> <span data-ttu-id="d1142-108">Дополнительные сведения о справке пользовательского командлета см. в разделе [написание Windows PowerShell пользовательских Справка по командлету для поставщиков](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span><span class="sxs-lookup"><span data-stu-id="d1142-108">For more information about custom cmdlet help, see [Writing Windows PowerShell Custom Cmdlet Help for Providers](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span></span>

<span data-ttu-id="d1142-109">Если поставщик не реализует динамических параметров, раздел справки поставщика содержит пустой `DynamicParameters` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-109">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="d1142-110">Для добавления динамических параметров</span><span class="sxs-lookup"><span data-stu-id="d1142-110">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="d1142-111">В *AssemblyName*.dll help.xml файл в `providerHelp` элемента, добавьте `DynamicParameters` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-111">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="d1142-112">`DynamicParameters` Должен появиться элемент после `Tasks` элемента и до `RelatedLinks` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-112">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="d1142-113">Например:</span><span class="sxs-lookup"><span data-stu-id="d1142-113">For example:</span></span>

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

   <span data-ttu-id="d1142-114">Если поставщик не реализует динамические параметры, `DynamicParameters` элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="d1142-114">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

2. <span data-ttu-id="d1142-115">В рамках `DynamicParameters` добавить элемент, для каждого динамического параметра `DynamicParameter` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-115">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="d1142-116">Например:</span><span class="sxs-lookup"><span data-stu-id="d1142-116">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. <span data-ttu-id="d1142-117">В каждом `DynamicParameter` элемента, добавьте `Name` и `CmdletSupported` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-117">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   |<span data-ttu-id="d1142-118">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="d1142-118">Element Name</span></span>|<span data-ttu-id="d1142-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d1142-119">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="d1142-120">Name</span><span class="sxs-lookup"><span data-stu-id="d1142-120">Name</span></span>|<span data-ttu-id="d1142-121">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="d1142-121">Specifies the parameter name.</span></span>|
   |<span data-ttu-id="d1142-122">CmdletSupported</span><span class="sxs-lookup"><span data-stu-id="d1142-122">CmdletSupported</span></span>|<span data-ttu-id="d1142-123">Задает командлеты, в котором данный параметр является допустимым.</span><span class="sxs-lookup"><span data-stu-id="d1142-123">Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="d1142-124">Введите разделенный запятыми список имен командлетов.</span><span class="sxs-lookup"><span data-stu-id="d1142-124">Type a comma-separated list of cmdlet names.</span></span>|

   <span data-ttu-id="d1142-125">Например, следующий XML-документов `Encoding` динамический параметр, добавляемый поставщиком Windows PowerShell FileSystem для `Add-Content`, `Get-Content`, `Set-Content` командлетов.</span><span class="sxs-lookup"><span data-stu-id="d1142-125">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. <span data-ttu-id="d1142-126">В каждом `DynamicParameter` элемента, добавьте `Type` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-126">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="d1142-127">`Type` Элемент — это контейнер для `Name` элемент, который содержит тип .NET значение динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="d1142-127">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="d1142-128">Например, следующий код XML показывает, что тип .NET `Encoding` динамический параметр — [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) перечисления.</span><span class="sxs-lookup"><span data-stu-id="d1142-128">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

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

5. <span data-ttu-id="d1142-129">Добавление `Description` элемент, который содержит краткое описание динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="d1142-129">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="d1142-130">При создании описания, следуйте рекомендациям, указано для всех параметров командлета в [как добавить сведения о параметрах](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="d1142-130">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="d1142-131">Например, следующий код XML включает описание `Encoding` динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="d1142-131">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

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

6. <span data-ttu-id="d1142-132">Добавление `PossibleValues` элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="d1142-132">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="d1142-133">Вместе эти элементы описывают значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="d1142-133">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="d1142-134">Этот элемент предназначен для перечисляемых значений.</span><span class="sxs-lookup"><span data-stu-id="d1142-134">This element is designed for enumerated values.</span></span> <span data-ttu-id="d1142-135">Если динамический параметр принимает значение, например в случае с параметром коммутатора, или на значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-135">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="d1142-136">В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="d1142-136">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   |<span data-ttu-id="d1142-137">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="d1142-137">Element Name</span></span>|<span data-ttu-id="d1142-138">Описание</span><span class="sxs-lookup"><span data-stu-id="d1142-138">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="d1142-139">PossibleValues</span><span class="sxs-lookup"><span data-stu-id="d1142-139">PossibleValues</span></span>|<span data-ttu-id="d1142-140">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="d1142-140">This element is a container.</span></span> <span data-ttu-id="d1142-141">Ниже приведено описание его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d1142-141">Its child elements are described below.</span></span> <span data-ttu-id="d1142-142">Добавьте одно `PossibleValues` элемент для каждого раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="d1142-142">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="d1142-143">Элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="d1142-143">The element can be empty.</span></span>|
   |<span data-ttu-id="d1142-144">PossibleValue</span><span class="sxs-lookup"><span data-stu-id="d1142-144">PossibleValue</span></span>|<span data-ttu-id="d1142-145">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="d1142-145">This element is a container.</span></span> <span data-ttu-id="d1142-146">Ниже приведено описание его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d1142-146">Its child elements are described below.</span></span> <span data-ttu-id="d1142-147">Добавьте одно `PossibleValue` элемент для каждого значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="d1142-147">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>|
   |<span data-ttu-id="d1142-148">Значение</span><span class="sxs-lookup"><span data-stu-id="d1142-148">Value</span></span>|<span data-ttu-id="d1142-149">Указывает имя значения.</span><span class="sxs-lookup"><span data-stu-id="d1142-149">Specifies the value name.</span></span>|
   |<span data-ttu-id="d1142-150">Описание</span><span class="sxs-lookup"><span data-stu-id="d1142-150">Description</span></span>|<span data-ttu-id="d1142-151">Этот элемент содержит `Para` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-151">This element contains a `Para` element.</span></span> <span data-ttu-id="d1142-152">Текст в `Para` элемент описывает значения, который называется `Value` элемент.</span><span class="sxs-lookup"><span data-stu-id="d1142-152">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>|

   <span data-ttu-id="d1142-153">Например, следующий код XML показывает один `PossibleValue` элемент `Encoding` динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="d1142-153">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="d1142-154">Пример</span><span class="sxs-lookup"><span data-stu-id="d1142-154">Example</span></span>

<span data-ttu-id="d1142-155">В следующем примере показан `DynamicParameters` элемент `Encoding` динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="d1142-155">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

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