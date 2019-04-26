---
title: Как добавить сведения о параметрах | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6c1442-60aa-477a-8f30-ab02b1b11039
caps.latest.revision: 7
ms.openlocfilehash: d4a5fc934a41b00f89862674e44e4540680674f7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083371"
---
# <a name="how-to-add-parameter-information"></a>Как добавить сведения о параметрах

В этом разделе описывается добавление содержимого, которое отображается в разделе "Параметры" раздела справки командлета. В разделе "Параметры" раздела справки перечислены все параметры командлета и содержит подробное описание каждого параметра.

Содержимое раздела параметров должны соответствовать содержимое раздела "СИНТАКСИС" раздела справки. Он отвечает автор справки, чтобы убедиться в том, что синтаксис и параметры узла содержат аналогичные элементы XML.

> [!NOTE]
> Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell. Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.

### <a name="to-add-parameters"></a>Чтобы добавить параметры

1. Откройте файл справки командлета и найдите узел команд для командлета, о котором нужно документировать. Если вы добавляете новый командлет, вам нужно будет создать новый узел команды. Файл справки будет содержать узел для каждого командлета, вы предоставляете содержимого справки для команд. Ниже приведен пример пустой узел команды.

    ```xml
    <command:command>
    </command:command>
    ```

2. Внутри узла команды перейдите к узлу описание и добавить узел параметров, как показано ниже. Допускается только один узел параметров, и он должен следовать непосредственно за узел синтаксического.

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. В узел «параметры» добавьте узел параметра для каждого параметра командлета, как показано ниже.

   В этом примере узел параметра добавляется для трех параметров.

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   Так как это же XML-теги, которые используются в узле синтаксис и поскольку здесь указаны параметры должны соответствовать параметрам, указанным узла синтаксического можно копировать узлы параметров из узла синтаксического и вставьте их в узел «параметры». Тем не менее, не забудьте скопировать только один экземпляр узел параметров, даже если этот параметр указан в нескольких параметр задает в синтаксисе.

4. Для каждого параметра набора узлов, значения атрибутов, определяющих характеристики каждого параметра. Эти атрибуты включают следующие: требуется, глобализации, pipelineinput и положение.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

5. Для каждого параметра узла добавьте имя параметра. Вот пример добавляемый узел параметра имени параметра.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. Для каждого параметра узла добавьте описание параметра. Ниже приведен пример к узлу параметр добавляется описание параметра.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

7. Для каждого параметра узла добавление .NET Framework типа параметра. Тип параметра отображается вместе с именем параметра.

   Вот пример типа платформы .NET Framework параметр, добавляемый узел параметра.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

8. Для каждого параметра узла добавьте значение параметра по умолчанию. Следующее предложение добавляется описание параметра при отображении содержимого: «DefaultValue» используется по умолчанию.

   Ниже приведен пример значения параметра по умолчанию добавляется к узлу параметра.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

9. Для каждого параметра, имеющей несколько значений Добавление узла возможные значения.

   Вот пример возможных значений узла, который определяет два возможных значения для параметра

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      /dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

Ниже приведены некоторые важные советы при добавлении параметров.

- Атрибуты параметра не отображаются во всех представлениях раздела справки командлета. Тем не менее, они отображаются в таблице, следуя описанию параметра, когда пользователь запрашивает полный (Get-Help \<cmdletname >-полная) или параметра (Get-Help \<cmdletname >-параметра) представление раздела.

- Описание параметра является одним из наиболее важные части раздела справки командлета. Описание должно быть краткое, а также полной. Кроме того помните, что если описание параметра становится слишком много времени, например, если два параметра взаимодействуют друг с другом, можно добавить дополнительные материалы в разделе "Примечания" раздела справки командлета.

  Описание параметра предоставляет два типа сведений.

- Действиях командлета при использовании параметра.

- Какие допустимое значение — в параметре.

- Так как значения параметров, выражаются в виде объектов .NET Framework, пользователи должны Дополнительные сведения об этих значениях, чем при работе в традиционных Справка по командной строке. Уведомить пользователя, какой тип данных параметра предназначена для приема и включают примеры.

Значение по умолчанию параметра является значение, которое используется, если этот параметр не указан в командной строке. Обратите внимание, что значение по умолчанию является необязательным и не требуется для некоторых параметров, таких как обязательные параметры. Тем не менее следует указать значение по умолчанию для большинства необязательных параметров.

Значение по умолчанию помогает пользователю понять последствия не используя параметр. Описания по умолчанию очень в частности, например «текущий каталог» или «Windows PowerShell каталог установки ($pshome)» дополнительный путь. Можно также создавать предложение, описывающее по умолчанию, например, следующее предложение для `PassThru` параметр: «Если PassThru не указан, командлет не передает объекты по конвейеру.»  Кроме того поскольку напротив имени поля отображается значение "**значение по умолчанию**«, необходимо включить термин «значение по умолчанию» в записи.

Значение по умолчанию параметра не отображается во всех представлениях раздела справки командлета. Тем не менее, он отображается в таблице (а также атрибуты параметра) следуя описание параметра, когда пользователь запрашивает полный (Get-Help \<cmdletname >-полная) или параметра (Get-Help \<cmdletname >-параметра) представления раздела.

Следующий код XML показывает пару `<dev:defaultValue>` теги, добавляемые к `<command:parameter>` узла. Обратите внимание, что значение по умолчанию соответствует сразу после завершения `</command:parameterValue>` тега (Если указано значение параметра) или закрытие `</maml:description>` тег описание параметра. Имя.

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

Добавьте значения для перечисляемых типов

Если параметр состоит из нескольких значений или значений перечисляемого типа, можно использовать необязательный \<dev:possibleValues > узла. Этот узел позволяет указать имя и описание для нескольких значений.

Имейте в виду, что описания перечисляемые значения не отображаются в по умолчанию представления справки, отображаемого элементом `Get-Help` командлета, но в других средствах просмотра справки может отобразить это содержимое в своих представлениях.

Следующий код XML показывает `<dev:possibleValues>` узел с двумя указанными значениями.

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```