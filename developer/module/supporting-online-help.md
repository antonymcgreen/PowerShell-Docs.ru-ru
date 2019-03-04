---
title: Поддержке справки в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: b76f45299d11dc10c8b16ed80f87c7f1fcc5ed65
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857920"
---
# <a name="supporting-online-help"></a>Поддержка справки в Интернете

Начиная с Windows PowerShell 3.0, существует два способа для поддержки `Get-Help` интерактивный инструмент для команд Windows PowerShell. В этом разделе объясняется, как реализовать эту функцию для разные типы команд.

## <a name="about-online-help"></a>О справке

Справка в Интернете всегда было важной частью работы Windows PowerShell. Несмотря на то что `Get-Help` командлет отображает разделы справки в командной строке, многие пользователи предпочитают процесс чтения через Интернет, в том числе цветовое кодирование, гиперссылки и обмена идеями в содержимое сообщества и документы на основе вики-сайта. Самое главное до появления обновляемую справку, Справка в Интернете указано самую последнюю версию файлов справки.

С появлением обновляемой справки в Windows PowerShell 3.0 Справка в Интернете по-прежнему играет важную роль. Помимо использования элементов интерфейса пользователя гибкий справку в Интернете предоставляет справку для пользователей, не устанавливает или не может использовать обновляемую справку для загрузки разделов справки.

## <a name="how-get-help--online-works"></a>Как Get-Help-Online Works

Чтобы помочь пользователям найти разделы справки для команд, `Get-Help` command имеет Online параметр, который открывает Интернет-версию раздела справки для команд в веб-браузере пользователя по умолчанию.

Например, следующая команда открывает раздела справки в Интернете для `Invoke-Command` командлета.

```powershell
Get-Help Invoke-Command -Online
```

Для реализации `Get-Help` -Интернете, `Get-Help` командлет ищет для универсального кода ресурса (URI) для интерактивной версии раздела справки в следующих расположениях.

- Первую ссылку в разделе "связанные ссылки" раздела справки для команды. Раздел справки необходимо установить на компьютере пользователя. Эта функция появилась в Windows PowerShell 2.0.

- Свойства HelpUri любую команду. Свойства HelpUri доступен даже в том случае, если раздел справки для команды не установлены на компьютере пользователя. Эта функция появилась в Windows PowerShell 3.0.

  `Get-Help` выполняет поиск с URI в первой записи в разделе ссылки по теме перед получением значения свойства HelpUri. Если значение свойства задан неверно, или был изменен, его можно переопределить, указав другое значение в первую связанную ссылку. Тем не менее в первую связанную ссылку работает только в том случае, если разделы справки, установленных на компьютере пользователя.

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a>Добавление URI в первую связанную ссылку разделу справки

Можно поддерживать `Get-Help` -Online для любой команды, добавив является допустимым URI для первой записи в разделе "ссылки по теме" раздела справки на основе XML для команды. Этот параметр допустим только в разделы справки на основе XML и работает только в том случае, если раздел справки установлена на компьютере пользователя. При установке раздела справки, а URI заполняется, это значение имеет приоритет над **HelpUri** свойства команды. Сведения о формате XML разделы справки для команд, см. в разделе [Writing XML-Based разделы справки для команд](../help/writing-xml-based-help-topics-for-commands.md).

Для поддержки этой возможности, URI должен присутствовать в `maml:uri` элемент под первым `maml:relatedLinks/maml:navigationLink` элемент в `maml:relatedLinks` элемент.

Следующий код XML показано правильное размещение URI. «Интернет-версии:» текст в `maml:linkText` элемент является лучшим способом, но это не обязательно.

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>http://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a>Добавление свойства HelpUri команды

В этом разделе показано, как добавить свойства HelpUri к командам различных типов.

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a>Добавление свойства HelpUri в командлет

Для командлетов, написанных на C#, добавьте **HelpUri** атрибут в классе командлета. Значение атрибута должно быть URI, который начинается с «http» или «https».

В следующем коде показано атрибут HelpUri `Get-History` класса cmdlet.

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a>Добавление свойства HelpUri в дополнительную функцию

Расширенные функции, добавьте **HelpUri** свойства **CmdletBinding** атрибута. Значение свойства должно быть URI, который начинается с «http» или «https».

В следующем коде показано атрибута HelpUri функции New-календаря

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a>Добавление атрибута HelpUri команды CIM

Для команды CIM, добавьте **HelpUri** атрибут **CmdletMetadata** в файле CDXML. Значение атрибута должно быть URI, который начинается с «http» или «https».

В следующем коде показано атрибута HelpUri команды Start-Debug CIM

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a>Добавление атрибута HelpUri рабочего процесса

Для рабочих процессов, написанных на языке Windows PowerShell, добавьте **. ExternalHelp** comment-директива код рабочего процесса. Значение директивы должен быть URI, который начинается с «http» или «https».

> [!NOTE]
> Свойства HelpUri не поддерживается для рабочих процессов на основе XAML в Windows PowerShell.

В следующем коде показан. Директива ExternalHelp в файл рабочего процесса.

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```