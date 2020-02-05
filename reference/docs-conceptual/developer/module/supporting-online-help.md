---
title: Поддержка справки в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: cf181e8f26ebd4b9c57b5b0191809211f2471f13
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76995573"
---
# <a name="supporting-online-help"></a>Поддержка справки в Интернете

Начиная с Windows PowerShell 3,0, существует два способа поддержки функции `Get-Help` Online для команд Windows PowerShell. В этом разделе объясняется, как реализовать эту функцию для различных типов команд.

## <a name="about-online-help"></a>Справка в Интернете

Интерактивная справка всегда была важной частью Windows PowerShell. Несмотря на то, что командлет `Get-Help` отображает разделы справки в командной строке, многие пользователи предпочитают возможность чтения через Интернет, включая выделение цветом, гиперссылки и идеи для совместного использования в содержимом сообщества и на вики-документах. Самое важное, прежде чем поступать с обновляемой справкой, Справка в Интернете предоставляла самые последние версии файлов справки.

С появлением обновляемой справки в Windows PowerShell 3,0 интерактивная справка по-прежнему играет важную роль. В дополнение к гибкому интерфейсу пользователя Справка в Интернете предоставляет пользователям, которые не могут использовать обновляемую справку для загрузки разделов справки.

## <a name="how-get-help--online-works"></a>Как Get-Help-Online работает

Чтобы помочь пользователям найти разделы справки в Интернете для команд, команда `Get-Help` имеет параметр Online, который открывает интерактивную версию раздела справки для команды в Интернет-браузере по умолчанию пользователя.

Например, следующая команда открывает раздел справки в Интернете для командлета `Invoke-Command`.

```powershell
Get-Help Invoke-Command -Online
```

Чтобы реализовать `Get-Help`-Online, командлет `Get-Help` ищет универсальный код ресурса (URI) для раздела справки по интерактивной версии в следующих расположениях.

- Первая ссылка в разделе "связанные ссылки" раздела справки для команды. Раздел справки должен быть установлен на компьютере пользователя. Эта функция появилась в Windows PowerShell 2,0.

- Свойство HelpUri любой команды. Свойство HelpUri доступно, даже если раздел справки для команды не установлен на компьютере пользователя. Эта функция появилась в Windows PowerShell 3,0.

  `Get-Help` ищет URI в первой записи в разделе связанных ссылок перед получением значения свойства HelpUri. Если значение свойства неверно или изменилось, его можно переопределить, введя другое значение в первой связанной ссылке. Однако первая связанная ссылка работает только в том случае, если разделы справки установлены на компьютере пользователя.

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a>Добавление URI в первую связанную ссылку раздела справки по команде

Вы можете поддерживать `Get-Help`-Online для любой команды, добавив допустимый URI в первую запись в разделе связанных ссылок раздела справки на основе XML для команды. Этот параметр допустим только в разделах справки на основе XML и работает только при установке раздела справки на компьютере пользователя. Если раздел справки установлен и URI заполнен, это значение имеет приоритет над свойством **HelpUri** команды.

Для поддержки этой функции URI должен присутствовать в элементе `maml:uri` под первым `maml:relatedLinks/maml:navigationLink`ным элементом в элементе `maml:relatedLinks`.

В следующем XML-коде показано правильное размещение URI. Рекомендуется использовать текст "онлайн Version:" в элементе `maml:linkText`, но он не является обязательным.

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a>Добавление свойства HelpUri в команду

В этом разделе показано, как добавить свойство HelpUri в команды различных типов.

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a>Добавление свойства HelpUri в командлет

Для командлетов, C#написанных в, добавьте атрибут **HelpUri** в класс командлета. Значение атрибута должно быть URI, начинающимся с "http" или "HTTPS".

В следующем коде показан атрибут HelpUri класса командлета `Get-History`.

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a>Добавление свойства HelpUri в расширенную функцию

Для расширенных функций добавьте свойство **HelpUri** в атрибут **CmdletBinding** . Значение свойства должно быть URI, начинающимся с "http" или "HTTPS".

В следующем коде показан атрибут HelpUri функции New-Calendar.

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a>Добавление атрибута HelpUri в команду CIM

Для команд CIM добавьте атрибут **HelpUri** в элемент **КМДЛЕТМЕТАДАТА** в файле CDXML. Значение атрибута должно быть URI, начинающимся с "http" или "HTTPS".

В следующем коде показан атрибут HelpUri команды CIM Start-Debug.

```
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a>Добавление атрибута HelpUri в рабочий процесс

Для рабочих процессов, написанных на языке Windows PowerShell, добавьте **.** Директива комментария екстерналхелп к коду рабочего процесса. Значение директивы должно быть универсальным кодом ресурса (URI), начинающимся с "http" или "HTTPS".

> [!NOTE]
> Свойство HelpUri не поддерживается для рабочих процессов на основе XAML в Windows PowerShell.

В следующем коде показан объект. Директива Екстерналхелп в файле рабочего процесса.

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```