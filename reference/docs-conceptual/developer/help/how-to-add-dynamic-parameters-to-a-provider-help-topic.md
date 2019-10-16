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
ms.openlocfilehash: 59839e9b8b6f2a56f2f1a9c755f2f1a85deb34aa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361263"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="5b4f9-102">Как добавить динамические параметры в раздел справки для поставщика</span><span class="sxs-lookup"><span data-stu-id="5b4f9-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="5b4f9-103">В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="5b4f9-104">*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="5b4f9-105">Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="5b4f9-106">Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="5b4f9-107">При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span>

<span data-ttu-id="5b4f9-108">Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой элемент `DynamicParameters`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-108">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="5b4f9-109">Добавление динамических параметров</span><span class="sxs-lookup"><span data-stu-id="5b4f9-109">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="5b4f9-110">В файле *AssemblyName*. длл-Хелп. XML в элементе `providerHelp` добавьте элемент `DynamicParameters`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-110">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="5b4f9-111">Элемент `DynamicParameters` должен располагаться после элемента `Tasks` и перед элементом `RelatedLinks`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-111">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="5b4f9-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="5b4f9-112">For example:</span></span>

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

   <span data-ttu-id="5b4f9-113">Если поставщик не реализует динамические параметры, элемент `DynamicParameters` может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-113">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

2. <span data-ttu-id="5b4f9-114">В элементе `DynamicParameters` для каждого динамического параметра добавьте элемент `DynamicParameter`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-114">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="5b4f9-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="5b4f9-115">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. <span data-ttu-id="5b4f9-116">В каждом элементе `DynamicParameter` добавьте элемент `Name` и `CmdletSupported`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-116">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   |<span data-ttu-id="5b4f9-117">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="5b4f9-117">Element Name</span></span>|<span data-ttu-id="5b4f9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5b4f9-118">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="5b4f9-119">Название</span><span class="sxs-lookup"><span data-stu-id="5b4f9-119">Name</span></span>|<span data-ttu-id="5b4f9-120">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-120">Specifies the parameter name.</span></span>|
   |<span data-ttu-id="5b4f9-121">кмдлетсуппортед</span><span class="sxs-lookup"><span data-stu-id="5b4f9-121">CmdletSupported</span></span>|<span data-ttu-id="5b4f9-122">Указывает командлеты, в которых параметр является допустимым.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-122">Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="5b4f9-123">Введите разделенный запятыми список имен командлетов.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-123">Type a comma-separated list of cmdlet names.</span></span>|

   <span data-ttu-id="5b4f9-124">Например, следующий XML-документ описывает динамический параметр `Encoding`, добавляемый поставщиком файловой системы Windows PowerShell в командлеты `Add-Content`, `Get-Content`, `Set-Content`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-124">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. <span data-ttu-id="5b4f9-125">В каждом элементе `DynamicParameter` добавьте элемент `Type`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-125">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="5b4f9-126">Элемент `Type` является контейнером для элемента `Name`, который содержит тип .NET значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-126">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="5b4f9-127">Например, в следующем XML-коде показано, что тип .NET для динамического параметра `Encoding` — это перечисление [Microsoft. PowerShell. Commands. филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .</span><span class="sxs-lookup"><span data-stu-id="5b4f9-127">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

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

5. <span data-ttu-id="5b4f9-128">Добавьте элемент `Description`, который содержит краткое описание динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-128">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="5b4f9-129">При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="5b4f9-129">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="5b4f9-130">Например, следующий XML-код включает описание динамического параметра `Encoding`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-130">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

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

6. <span data-ttu-id="5b4f9-131">Добавьте элемент `PossibleValues` и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-131">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="5b4f9-132">Вместе эти элементы описывают значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-132">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="5b4f9-133">Этот элемент предназначен для перечислимых значений.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-133">This element is designed for enumerated values.</span></span> <span data-ttu-id="5b4f9-134">Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой элемент `PossibleValues`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-134">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="5b4f9-135">В следующей таблице перечислены и описаны элемент `PossibleValues` и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-135">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   |<span data-ttu-id="5b4f9-136">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="5b4f9-136">Element Name</span></span>|<span data-ttu-id="5b4f9-137">Описание</span><span class="sxs-lookup"><span data-stu-id="5b4f9-137">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="5b4f9-138">поссиблевалуес</span><span class="sxs-lookup"><span data-stu-id="5b4f9-138">PossibleValues</span></span>|<span data-ttu-id="5b4f9-139">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-139">This element is a container.</span></span> <span data-ttu-id="5b4f9-140">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-140">Its child elements are described below.</span></span> <span data-ttu-id="5b4f9-141">Добавьте один элемент `PossibleValues` в каждый раздел справки поставщика.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-141">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="5b4f9-142">Элемент может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-142">The element can be empty.</span></span>|
   |<span data-ttu-id="5b4f9-143">поссиблевалуе</span><span class="sxs-lookup"><span data-stu-id="5b4f9-143">PossibleValue</span></span>|<span data-ttu-id="5b4f9-144">Этот элемент является контейнером.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-144">This element is a container.</span></span> <span data-ttu-id="5b4f9-145">Его дочерние элементы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-145">Its child elements are described below.</span></span> <span data-ttu-id="5b4f9-146">Добавьте один элемент `PossibleValue` для каждого значения динамического параметра.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-146">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>|
   |<span data-ttu-id="5b4f9-147">Применение</span><span class="sxs-lookup"><span data-stu-id="5b4f9-147">Value</span></span>|<span data-ttu-id="5b4f9-148">Задает имя значения.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-148">Specifies the value name.</span></span>|
   |<span data-ttu-id="5b4f9-149">Описание</span><span class="sxs-lookup"><span data-stu-id="5b4f9-149">Description</span></span>|<span data-ttu-id="5b4f9-150">Этот элемент содержит элемент `Para`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-150">This element contains a `Para` element.</span></span> <span data-ttu-id="5b4f9-151">Текст в элементе `Para` описывает значение с именем в элементе `Value`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-151">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>|

   <span data-ttu-id="5b4f9-152">Например, следующий XML-код показывает один элемент `PossibleValue` в динамическом параметре `Encoding`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-152">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="5b4f9-153">Пример</span><span class="sxs-lookup"><span data-stu-id="5b4f9-153">Example</span></span>

<span data-ttu-id="5b4f9-154">В следующем примере показан элемент `DynamicParameters` для динамического параметра `Encoding`.</span><span class="sxs-lookup"><span data-stu-id="5b4f9-154">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

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