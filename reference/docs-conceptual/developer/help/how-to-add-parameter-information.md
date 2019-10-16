---
title: Добавление сведений о параметрах | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6c1442-60aa-477a-8f30-ab02b1b11039
caps.latest.revision: 7
ms.openlocfilehash: d4a5fc934a41b00f89862674e44e4540680674f7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361233"
---
# <a name="how-to-add-parameter-information"></a>Как добавить сведения о параметрах

В этом разделе описывается, как добавить содержимое, отображаемое в разделе "Параметры" раздела справки по командлетам. В разделе параметров раздела справки перечислены все параметры командлета, а также подробно описан каждый параметр.

Содержимое раздела PARAMETERS должно соответствовать содержимому раздела СИНТАКСИСа раздела справки. Автор справки должен убедиться, что узел синтаксис и параметры содержат похожие XML-элементы.

> [!NOTE]
> Для получения полного представления файла справки откройте один из файлов длл-Хелп. XML, расположенный в каталоге установки Windows PowerShell. Например, файл Microsoft. PowerShell. Commands. Management. длл-Хелп. XML содержит содержимое для некоторых командлетов Windows PowerShell.

### <a name="to-add-parameters"></a>Добавление параметров

1. Откройте файл справки командлета и перейдите к узлу команды для командлета, для которого выполняется документирование. При добавлении нового командлета необходимо создать новый узел команды. Файл справки будет содержать узел команды для каждого командлета, для которого предоставляется содержимое справки. Ниже приведен пример пустого узла команды.

    ```xml
    <command:command>
    </command:command>
    ```

2. В узле команды выберите узел описание и добавьте узел Параметры, как показано ниже. Допускается только один узел параметров, и он должен следовать непосредственно за узлом синтаксиса.

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. В узле параметры добавьте узел параметров для каждого параметра командлета, как показано ниже.

   В этом примере для трех параметров добавляется узел параметров.

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   Поскольку это те же XML-теги, которые используются в узле синтаксиса, и так как указанные здесь параметры должны соответствовать параметрам, заданным в узле синтаксиса, можно скопировать узлы параметров из узла синтаксиса и вставить их в узел Параметры. Однако не забудьте скопировать только один экземпляр узла параметра, даже если параметр указан в синтаксисе в нескольких наборах параметров.

4. Для каждого узла параметра задайте значения атрибутов, определяющие характеристики каждого параметра. К этим атрибутам относятся следующие: required, глобализации, пипелинеинпут и положением.

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

5. Для каждого узла параметра добавьте имя параметра. Ниже приведен пример имени параметра, добавляемого в узел параметра.

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. Для каждого узла параметра добавьте описание параметра. Ниже приведен пример описания параметра, добавленного к узлу параметров.

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

7. Для каждого узла параметра добавьте тип .NET Framework параметра. Тип параметра отображается вместе с именем параметра.

   Ниже приведен пример параметра .NET Framework типа, добавленного в узел параметра.

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

8. Для каждого узла параметра добавьте значение параметра по умолчанию. Следующее предложение добавляется в описание параметра при отображении содержимого: по умолчанию используется значение DefaultValue.

   Ниже приведен пример значения параметра по умолчанию, добавляемого к узлу параметров.

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

9. Для каждого параметра, имеющего несколько значений, добавьте узел возможных значений.

   Ниже приведен пример узла возможных значений, который определяет два возможных значения для параметра.

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

Ниже приведены некоторые моменты, которые следует помнить при добавлении параметров.

- Атрибуты параметра не отображаются во всех представлениях раздела справки по командлетам. Однако они отображаются в таблице после описания параметра, когда пользователь запрашивает полное представление (Get-Help \<cmdletname >-Full) или параметр (Get-Help \<cmdletname >-Parameter) раздела.

- Описание параметра является одной из наиболее важных частей раздела справки по командлетам. Описание должно быть кратким, а также подробным. Кроме того, помните, что если описание параметра станет слишком длинным, например, когда два параметра взаимодействуют друг с другом, можно добавить дополнительное содержимое в раздел "Примечания" раздела справки по командлетам.

  Описание параметра предоставляет два типа информации.

- Действие командлета при использовании параметра.

- Допустимое значение для параметра.

- Поскольку значения параметров выражаются как .NET Framework объекты, пользователям требуются дополнительные сведения об этих значениях, чем в традиционной справке по командной строке. Сообщите пользователю, какой тип данных предназначен для принятия параметра, и включите примеры.

Значение параметра по умолчанию — значение, которое используется, если параметр не указан в командной строке. Обратите внимание, что значение по умолчанию является необязательным и не требуется для некоторых параметров, таких как обязательные параметры. Однако для большинства необязательных параметров следует указать значение по умолчанию.

Значение по умолчанию помогает пользователю понять, какой результат не используется параметром. Опишите значение по умолчанию особенно, например "текущий каталог" или "каталог установки Windows PowerShell ($pshome)", для необязательного пути. Можно также написать предложение, описывающее значение по умолчанию, например следующее предложение, используемое для параметра `PassThru`: "Если параметр PassThru не указан, командлет не передает объекты по конвейеру".  Кроме того, поскольку значение отображается обратно в поле "**значение по умолчанию**", не нужно включать в запись термин "значение по умолчанию".

Значение параметра по умолчанию не отображается во всех представлениях раздела справки по командлетам. Однако он отображается в таблице (вместе с атрибутами параметров) после описания параметра, когда пользователь запрашивает полное представление (Get-Help \<cmdletname >-Full) или параметр (Get-Help \<cmdletname >-Parameter) раздела.

В следующем коде XML показана пара тегов `<dev:defaultValue>`, добавленных в узел `<command:parameter>`. Обратите внимание, что значение по умолчанию следует сразу после закрывающего тега `</command:parameterValue>` (если указано значение параметра) или закрывающего тега `</maml:description>` описания параметра. безымян.

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

Добавление значений для перечислимых типов

Если параметр имеет несколько значений или значений перечисляемого типа, можно использовать необязательный узел \<dev: Поссиблевалуес >. Этот узел позволяет указать имя и описание для нескольких значений.

Имейте в виду, что описания перечислимых значений не отображаются ни в одном из представлений справки по умолчанию, отображаемых командлетом `Get-Help`, но другие средства просмотра справки могут отображать это содержимое в своих представлениях.

В следующем XML-коде показан узел `<dev:possibleValues>` с двумя указанными значениями.

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