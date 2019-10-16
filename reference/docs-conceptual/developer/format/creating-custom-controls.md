---
title: Создание настраиваемых элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363383"
---
# <a name="creating-custom-controls"></a>Создание пользовательских элементов управления

Пользовательские элементы управления — это наиболее гибкие компоненты файла форматирования. В отличие от таблиц, списков и широких представлений, определяющих формальную структуру данных, например таблицу данных, пользовательские элементы управления позволяют определить способ отображения отдельного фрагмента данных. Можно определить общий набор пользовательских элементов управления, доступных для всех представлений файла форматирования, можно определить пользовательские элементы управления, доступные для конкретного представления, или определить набор элементов управления, доступных группе объектов.

## <a name="custom-control-example"></a>Пример пользовательского элемента управления

В следующем примере показан пользовательский элемент управления, определенный в файле Certificates. Format. ps1xml. Этот пользовательский элемент управления используется для разделения объектов [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) , отображаемых в табличном представлении.

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
