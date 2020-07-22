---
title: Как добавить раздел "См. также" в раздел справки для поставщика
ms.date: 09/12/2016
ms.openlocfilehash: 54adf4bb941888583eb749b7b5322b27d84c7af7
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893481"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>Как добавить раздел "См. также" в раздел справки для поставщика

В этом разделе объясняется, как заполнить раздел " **см. также** " в разделе справки поставщика.

Раздел **см. также** содержит список разделов, связанных с поставщиком, или может помочь пользователю лучше понять и использовать поставщик. Список разделов может включать справку по командлетам, справку поставщика и концептуальные разделы справки в Windows PowerShell. Он также может включать ссылки на книги, документы и статьи в Интернете, включая интерактивную версию текущего раздела справки поставщика.

При ссылке на разделы в Интернете укажите универсальный код ресурса (URI) или условие поиска в виде обычного текста. `Get-Help`Командлет не выполняет связывание или перенаправление к любому из разделов в списке. Кроме того, `Online` параметр `Get-Help` командлета не работает со справкой поставщика.

Раздел **см. также** создается на основе `RelatedLinks` элемента и содержащихся в нем тегов.
В следующем коде XML показано, как добавить теги.

### <a name="to-add-see-also-topics"></a>Для добавления см. также разделы

1. В `<AssemblyName>.dll-help.xml` файле в `providerHelp` элементе добавьте `RelatedLinks` элемент. `RelatedLinks`Элемент должен быть последним элементом в `providerHelp` элементе. `RelatedLinks`В каждом разделе справки по поставщику допускается только один элемент.

   Пример:

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

1. Для каждого раздела в разделе " **см. также** " в `RelatedLinks` элементе добавьте `navigationLink` элемент. Затем в каждом `navigationLink` элементе добавьте один `linkText` элемент и один `uri` элемент. Если элемент не используется `uri` , его можно добавить как пустой элемент ( \<uri/> ).

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

1. Введите имя раздела между `linkText` тегами. Если вы предоставляете универсальный код ресурса (URI), введите его между `uri` тегами. Чтобы указать Интернет-версию текущего раздела справки поставщика, между `linkText` тегами введите "Оперативная версия:", а не имя раздела. Как правило, ссылка "Оперативная версия:" является первой темой в списке "см. также".

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
                <uri>https://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```
