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
# <a name="creating-custom-controls"></a><span data-ttu-id="985f3-103">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="985f3-103">Creating Custom Controls</span></span>

<span data-ttu-id="985f3-104">Пользовательские элементы управления — это наиболее гибкие компоненты файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="985f3-104">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="985f3-105">В отличие от таблиц, списков и широких представлений, определяющих формальную структуру данных, например таблицу данных, пользовательские элементы управления позволяют определить способ отображения отдельного фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="985f3-105">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="985f3-106">Можно определить общий набор пользовательских элементов управления, доступных для всех представлений файла форматирования, можно определить пользовательские элементы управления, доступные для конкретного представления, или определить набор элементов управления, доступных группе объектов.</span><span class="sxs-lookup"><span data-stu-id="985f3-106">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="985f3-107">Пример пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="985f3-107">Custom Control Example</span></span>

<span data-ttu-id="985f3-108">В следующем примере показан пользовательский элемент управления, определенный в Certificates.Format.ps1XML-файле.</span><span class="sxs-lookup"><span data-stu-id="985f3-108">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="985f3-109">Этот пользовательский элемент управления используется для разделения объектов [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) , отображаемых в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="985f3-109">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="985f3-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="985f3-110">See Also</span></span>

[<span data-ttu-id="985f3-111">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="985f3-111">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
