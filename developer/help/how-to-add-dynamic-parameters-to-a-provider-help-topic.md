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
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Как добавить динамические параметры в раздел справки для поставщика

В этом разделе объясняется, как для заполнения **ДИНАМИЧЕСКИХ параметров** раздела справки на поставщика.

*Динамические параметры* параметров командлета или функции, которые доступны только при выполнении указанных условий.

Динамические параметры, которые описаны в разделе справки поставщика являются динамические параметры, которые поставщик добавляет в командлет или функцию, при использовании командлета или функции на диске поставщика.

Динамические параметры можно также задокументировать в справке пользовательского командлета для поставщика. При написании справки о поставщике и Справка пользовательского командлета для поставщика, включить в документации динамический параметр обоих документов. Дополнительные сведения о справке пользовательского командлета см. в разделе [написание Windows PowerShell пользовательских Справка по командлету для поставщиков](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).

Если поставщик не реализует динамических параметров, раздел справки поставщика содержит пустой `DynamicParameters` элемент.

### <a name="to-add-dynamic-parameters"></a>Для добавления динамических параметров

1. В *AssemblyName*.dll help.xml файл в `providerHelp` элемента, добавьте `DynamicParameters` элемент. `DynamicParameters` Должен появиться элемент после `Tasks` элемента и до `RelatedLinks` элемент.

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

2. В рамках `DynamicParameters` добавить элемент, для каждого динамического параметра `DynamicParameter` элемент.

   Например:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. В каждом `DynamicParameter` элемента, добавьте `Name` и `CmdletSupported` элемент.

   |Имя элемента|Описание|
   |------------------|-----------------|
   |Name|Указывает имя параметра.|
   |CmdletSupported|Задает командлеты, в котором данный параметр является допустимым. Введите разделенный запятыми список имен командлетов.|

   Например, следующий XML-документов `Encoding` динамический параметр, добавляемый поставщиком Windows PowerShell FileSystem для `Add-Content`, `Get-Content`, `Set-Content` командлетов.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. В каждом `DynamicParameter` элемента, добавьте `Type` элемент. `Type` Элемент — это контейнер для `Name` элемент, который содержит тип .NET значение динамического параметра.

   Например, следующий код XML показывает, что тип .NET `Encoding` динамический параметр — [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) перечисления.

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

5. Добавление `Description` элемент, который содержит краткое описание динамического параметра. При создании описания, следуйте рекомендациям, указано для всех параметров командлета в [как добавить сведения о параметрах](./how-to-add-parameter-information.md).

   Например, следующий код XML включает описание `Encoding` динамических параметров.

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

6. Добавление `PossibleValues` элемент и его дочерние элементы. Вместе эти элементы описывают значения динамического параметра. Этот элемент предназначен для перечисляемых значений. Если динамический параметр принимает значение, например в случае с параметром коммутатора, или на значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.

   В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.

   |Имя элемента|Описание|
   |------------------|-----------------|
   |PossibleValues|Этот элемент является контейнером. Ниже приведено описание его дочерних элементов. Добавьте одно `PossibleValues` элемент для каждого раздела справки поставщика. Элемент может быть пустым.|
   |PossibleValue|Этот элемент является контейнером. Ниже приведено описание его дочерних элементов. Добавьте одно `PossibleValue` элемент для каждого значения динамического параметра.|
   |Значение|Указывает имя значения.|
   |Описание|Этот элемент содержит `Para` элемент. Текст в `Para` элемент описывает значения, который называется `Value` элемент.|

   Например, следующий код XML показывает один `PossibleValue` элемент `Encoding` динамических параметров.

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

В следующем примере показан `DynamicParameters` элемент `Encoding` динамических параметров.

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