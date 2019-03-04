---
title: Создание пользовательских элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853200"
---
# <a name="creating-custom-controls"></a>Создание пользовательских элементов управления

Пользовательские элементы управления — это самый гибкий компоненты форматирования файла. В отличие от таблицы, список и широкие представления, которые определяют формальную структуру данных, таких как таблицу данных пользовательские элементы управления позволяют определять способ отображения отдельного элемента данных. Можно определить общий набор пользовательских элементов управления, доступные для всех представлений для форматирования файла, можно определить пользовательские элементы управления, доступные к определенному представлению, или можно определить набор элементов управления, доступные для группы объектов.

## <a name="custom-control-example"></a>Пример пользовательского элемента управления

В следующем примере пользовательский элемент управления, который определен в файле Certificates.Format.ps1xml. Этот пользовательский элемент управления используется для разделения [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) объектов, отображаемых в табличном представлении.

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

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
