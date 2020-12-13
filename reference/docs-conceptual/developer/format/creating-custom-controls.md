---
ms.date: 09/13/2016
ms.topic: reference
title: Создание пользовательских элементов управления
description: Создание пользовательских элементов управления
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668054"
---
# <a name="creating-custom-controls"></a>Создание пользовательских элементов управления

Пользовательские элементы управления — это наиболее гибкие компоненты файла форматирования. В отличие от таблиц, списков и широких представлений, определяющих формальную структуру данных, например таблицу данных, пользовательские элементы управления позволяют определить способ отображения отдельного фрагмента данных. Можно определить общий набор пользовательских элементов управления, доступных для всех представлений файла форматирования, можно определить пользовательские элементы управления, доступные для конкретного представления, или определить набор элементов управления, доступных группе объектов.

## <a name="custom-control-example"></a>Пример пользовательского элемента управления

В следующем примере показан пользовательский элемент управления, определенный в Certificates.Format.ps1XML-файле. Этот пользовательский элемент управления используется для разделения объектов [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) , отображаемых в табличном представлении.

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
