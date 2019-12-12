---
title: Добавление раздела "см. также" в раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367843"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>Как добавить раздел "См. также" в раздел справки для поставщика

В этом разделе объясняется, как заполнить раздел " **см. также** " в разделе справки поставщика.

Раздел **см. также** содержит список разделов, связанных с поставщиком, или может помочь пользователю лучше понять и использовать поставщик. Список разделов может включать справку по командлетам, справку поставщика и концептуальные разделы справки в Windows PowerShell. Он также может включать ссылки на книги, документы и статьи в Интернете, включая интерактивную версию текущего раздела справки поставщика.

При ссылке на разделы в Интернете укажите универсальный код ресурса (URI) или условие поиска в виде обычного текста. Командлет `Get-Help` не выполняет связывание или перенаправление к любому из разделов в списке. Кроме того, параметр `Online` командлета `Get-Help` не работает со справкой поставщика.

Раздел см. также создается на основе элемента `RelatedLinks` и содержащихся в нем тегов. В следующем коде XML показано, как добавить теги.

### <a name="to-add-see-also-topics"></a>Добавление разделов «см. также»

1. В файле *AssemblyName*. длл-Хелп. XML в элементе `providerHelp` добавьте элемент `RelatedLinks`. Элемент `RelatedLinks` должен быть последним элементом в элементе `providerHelp`. В каждом разделе справки по поставщику допускается только один элемент `RelatedLinks`.

   Пример:

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. Для каждого раздела в разделе " **см. также** " в элементе `RelatedLinks` добавьте элемент `navigationLink`. Затем в каждом элементе `navigationLink` добавьте один элемент `linkText` и один элемент `uri`. Если элемент `uri` не используется, его можно добавить как пустой элемент (\<URI/>).

   Пример:

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> </linkText>
                <uri> </uri>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

3. Введите имя раздела между тегами `linkText`. Если вы предоставляете универсальный код ресурса (URI), введите его между тегами `uri`. Чтобы указать Интернет-версию текущего раздела справки поставщика, между тегами `linkText` введите "Online Version:" вместо имени раздела. Как правило, ссылка "Оперативная версия:" является первой темой в списке "см. также".

   В следующем примере показано три раздела см. также: Первый раздел относится к интерактивной версии текущего раздела. Второй — раздел справки по командлетам Windows PowerShell. Третья статья относится к другому разделу в Интернете.

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> Online version: </linkText>
                <uri>http://www.fabrikam.com/help/myFunction.htm</uri>
            </navigationLink>
            <navigationLink>
                <linkText> about_functions </linkText>
                <uri/>
            </navigationLink>
            <navigationLink>
                <linkText> Windows PowerShell Getting Started Guide </linkText>
                <uri>http://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```