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
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Как добавить динамические параметры в раздел справки для поставщика

В этом разделе объясняется, как заполнить раздел **динамических параметров** раздела справки поставщика.

*Динамические параметры* — это параметры командлета или функции, доступные только при указанных условиях.

Динамические параметры, описанные в разделе справки поставщика, — это динамические параметры, которые поставщик добавляет в командлет или функцию при использовании командлета или функции на диске поставщика.

Динамические параметры также могут быть описаны в справке по пользовательскому командлету для поставщика. При написании справки поставщика и справки по пользовательскому командлету для поставщика включите документацию по динамическим параметрам в оба документа.

Если поставщик не реализует динамические параметры, раздел справки поставщика содержит пустой `DynamicParameters` элемент.

### <a name="to-add-dynamic-parameters"></a>Добавление динамических параметров

1. В `<AssemblyName>.dll-help.xml` файле в `providerHelp` элементе добавьте `DynamicParameters` элемент. `DynamicParameters`Элемент должен располагаться после `Tasks` элемента и перед `RelatedLinks` элементом.

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

   Если поставщик не реализует динамические параметры, `DynamicParameters` элемент может быть пустым.

1. В `DynamicParameters` элементе для каждого динамического параметра добавьте `DynamicParameter` элемент.

   Пример:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

1. В каждом `DynamicParameter` элементе добавьте `Name` `CmdletSupported` элемент и.

   - Имя — указывает имя параметра.
   - Кмдлетсуппортед — указывает командлеты, в которых параметр является допустимым. Введите разделенный запятыми список имен командлетов.

   Например, следующий XML-документ описывает `Encoding` динамический параметр, который поставщик FileSystem Windows PowerShell добавляет в `Add-Content` `Get-Content` командлеты,, `Set-Content` .

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

1. В каждом `DynamicParameter` элементе добавьте `Type` элемент. `Type`Элемент является контейнером для `Name` элемента, который содержит тип .NET значения динамического параметра.

   Например, в следующем XML-коде показано, что тип .NET `Encoding` динамического параметра — это перечисление [филесистемкмдлетпровидеренкодинг](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .

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

1. Добавьте `Description` элемент, содержащий краткое описание динамического параметра. При создании описания используйте рекомендации для всех параметров командлета в [инструкции по добавлению сведений о параметрах](./how-to-add-parameter-information.md).

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

1. Добавьте `PossibleValues` элемент и его дочерние элементы. Вместе эти элементы описывают значения динамического параметра. Этот элемент предназначен для перечислимых значений. Если динамический параметр не принимает значение, например, в случае с параметром Switch, или значения не могут быть перечислены, добавьте пустой `PossibleValues` элемент.

   В следующей таблице перечислены и описаны `PossibleValues` элемент и его дочерние элементы.

   - Поссиблевалуес — этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте один `PossibleValues` элемент в каждый раздел справки по поставщику. Элемент может быть пустым.
   - Поссиблевалуе — этот элемент является контейнером. Его дочерние элементы описаны ниже. Добавьте `PossibleValue` по одному элементу для каждого значения динамического параметра.
   - Значение — указывает имя значения.
   - Описание — этот элемент содержит `Para` элемент. Текст в `Para` элементе описывает значение, названное в `Value` элементе.

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
