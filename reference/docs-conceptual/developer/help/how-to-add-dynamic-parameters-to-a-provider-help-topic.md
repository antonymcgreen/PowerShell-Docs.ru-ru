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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361263"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Как добавить динамические параметры в раздел справки для поставщика

В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.

*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.

Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.

Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика. При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.

Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой элемент `DynamicParameters`.

### <a name="to-add-dynamic-parameters"></a>Добавление динамических параметров

1. В файле *AssemblyName*. длл-Хелп. XML в элементе `providerHelp` добавьте элемент `DynamicParameters`. Элемент `DynamicParameters` должен располагаться после элемента `Tasks` и перед элементом `RelatedLinks`.

   Пример:

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

   Если поставщик не реализует динамические параметры, элемент `DynamicParameters` может быть пустым.

2. В элементе `DynamicParameters` для каждого динамического параметра добавьте элемент `DynamicParameter`.

   Пример:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. В каждом элементе `DynamicParameter` добавьте `Name` и элемент `CmdletSupported`.

   |Имя элемента|Описание|
   |------------------|-----------------|
   |Название|Указывает имя параметра.|
   |кмдлетсуппортед|Указывает командлеты, в которых параметр является допустимым. Введите разделенный запятыми список имен командлетов.|

   Например, следующий XML-документ описывает `Encoding` динамический параметр, который поставщик FileSystem Windows PowerShell добавляет в командлеты `Add-Content`, `Get-Content``Set-Content`.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. В каждом элементе `DynamicParameter` добавьте элемент `Type`. Элемент `Type` является контейнером для элемента `Name`, который содержит тип .NET значения динамического параметра.

   Например, следующий XML-код показывает, что тип .NET `Encoding`ного динамического параметра — это перечисление [Microsoft. PowerShell. Commands. филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .

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

5. Добавьте элемент `Description`, содержащий краткое описание динамического параметра. При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).

   Например, следующий XML-код включает описание динамического параметра `Encoding`.

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

6. Добавьте элемент `PossibleValues` и его дочерние элементы. Вместе эти элементы описывают значения динамического параметра. Этот элемент предназначен для перечислимых значений. Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой элемент `PossibleValues`.

   В следующей таблице перечислены и описаны элемент `PossibleValues` и его дочерние элементы.

   |Имя элемента|Описание|
   |------------------|-----------------|
   |поссиблевалуес|Этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте один элемент `PossibleValues` в каждый раздел справки по поставщику. Элемент может быть пустым.|
   |поссиблевалуе|Этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте один элемент `PossibleValue` для каждого значения динамического параметра.|
   |Применение|Задает имя значения.|
   |Описание|Этот элемент содержит элемент `Para`. Текст в элементе `Para` описывает значение с именем в элементе `Value`.|

   Например, следующий XML-код показывает один элемент `PossibleValue` динамического параметра `Encoding`.

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

В следующем примере показан элемент `DynamicParameters` динамического параметра `Encoding`.

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