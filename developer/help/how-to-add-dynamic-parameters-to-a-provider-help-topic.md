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
ms.sourcegitcommit: 00083f07b13c73b86936e7d7307397df27c63c04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848114"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Как добавить динамические параметры в раздел справки для поставщика

В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.

*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.

Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.

Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика. При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.

Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой `DynamicParameters` элемент.

### <a name="to-add-dynamic-parameters"></a>Добавление динамических параметров

1. В `providerHelp` файле *AssemblyName*. длл-Хелп. XML в `DynamicParameters` элементе добавьте элемент. Элемент должен располагаться `Tasks` после элемента и перед `RelatedLinks` элементом. `DynamicParameters`

   Например:

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

   Если поставщик не реализует динамические параметры, `DynamicParameters` элемент может быть пустым.

2. В элементе для каждого динамического параметра `DynamicParameter` добавьте элемент. `DynamicParameters`

   Например:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. В каждом `DynamicParameter` элементе `Name` добавьте элемент и `CmdletSupported` .

   |Имя элемента|Описание|
   |------------------|-----------------|
   |Name|Указывает имя параметра.|
   |кмдлетсуппортед|Указывает командлеты, в которых параметр является допустимым. Введите разделенный запятыми список имен командлетов.|

   Например, следующий `Encoding` XML-документ описывает динамический параметр, который поставщик FileSystem Windows PowerShell добавляет `Add-Content`в командлеты, `Get-Content`, `Set-Content` .

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. В каждом `DynamicParameter` элементе `Type` добавьте элемент. Элемент является контейнером `Name` для элемента, который содержит тип .NET значения динамического параметра. `Type`

   Например, следующий XML-код показывает, что тип `Encoding` .NET динамического параметра — это перечисление [Microsoft. PowerShell. Commands. филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .

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

5. `Description` Добавьте элемент, содержащий краткое описание динамического параметра. При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).

   Например, следующий XML-код включает описание `Encoding` динамического параметра.

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

6. `PossibleValues` Добавьте элемент и его дочерние элементы. Вместе эти элементы описывают значения динамического параметра. Этот элемент предназначен для перечислимых значений. Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.

   В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.

   |Имя элемента|Описание|
   |------------------|-----------------|
   |поссиблевалуес|Этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте один `PossibleValues` элемент в каждый раздел справки по поставщику. Элемент может быть пустым.|
   |поссиблевалуе|Этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте по `PossibleValue` одному элементу для каждого значения динамического параметра.|
   |Значение|Задает имя значения.|
   |Описание|Этот элемент содержит `Para` элемент. Текст в `Para` элементе описывает значение, названное `Value` в элементе.|

   Например, следующий XML-код показывает один `PossibleValue` элемент `Encoding` динамического параметра.

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

## <a name="example"></a>Пример

В следующем примере показан `DynamicParameters` элемент `Encoding` динамического параметра.

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