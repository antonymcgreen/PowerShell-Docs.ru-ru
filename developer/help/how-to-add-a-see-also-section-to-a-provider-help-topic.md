---
title: Как добавить см. также раздел справки поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858350"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>Как добавить раздел "См. также" в раздел справки для поставщика

В этом разделе объясняется, как для заполнения **см. также** раздела справки на поставщика.

**См. также** раздел состоит из списка разделов, которые относятся к поставщику или может помочь пользователю лучше понять и использовать поставщик. Список разделов может включать справку по командлетам, справку по поставщикам и концептуальные («about») разделы справки в Windows PowerShell. Он также могут включать ссылки на книги, документ и разделы, включая версию текущего поставщика раздела справки в Интернете.

При ссылке на разделы, укажите URI или условие поиска в виде обычного текста. `Get-Help` Командлет не связать или перенаправлять любой из разделов в списке. Кроме того `Online` параметр `Get-Help` командлет не работает с помощью поставщика.

В разделе см. в разделе также создается на основе `RelatedLinks` элемента и теги, которые она содержит. Следующий код XML показано, как добавлять теги.

### <a name="to-add-see-also-topics"></a>Чтобы добавить разделы «См.»

1. В *AssemblyName*.dll help.xml файл в `providerHelp` элемента, добавьте `RelatedLinks` элемент. `RelatedLinks` Элемент должен быть последним элементом в `providerHelp` элемент. Только один `RelatedLinks` элемент допустим в каждый раздел справки поставщика.

   Например:

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. Для каждого раздела в **см. также** в разделе `RelatedLinks` элемента, добавьте `navigationLink` элемент. Затем, внутри каждого `navigationLink` элемента, добавьте один `linkText` элемент и один `uri` элемент. Если вы не используете `uri` элемент, его можно добавить пустой элемент (\<uri / >).

   Например:

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

3. Введите имя раздела между `linkText` теги. Если вы предоставляете URI, введите его между `uri` теги. Чтобы указать Интернет-версию текущего раздела справки поставщика, между `linkText` теги, типа «Интернет-версии:» вместо имени раздела. Как правило «версия в Интернете: «ссылка находится в первом разделе Список разделов также см. в разделе.

   Следующий пример включены три см. также разделы. Первый ссылаться на Интернет-версию текущего раздела. Второе — для раздела справки командлета Windows PowerShell. Третий ссылается на другой раздел справки.

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