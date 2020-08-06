---
title: Создание настраиваемых элементов управления | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c36fa9b778e01501a3c88f735cdefdfbb04411a0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786124"
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

## <a name="see-also"></a>См. также

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
