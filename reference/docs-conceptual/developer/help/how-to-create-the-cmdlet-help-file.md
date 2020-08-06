---
title: Создание файла справки по командлетам | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7ab0404e5d0122a64483883e6e2d4760dfa5038d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779834"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>Как создать файл справки командлета

В этом разделе описывается создание допустимого XML-файла, содержащего содержимое разделов справки по командлетам Windows PowerShell. В этом разделе описывается, как присвоить имя файлу справки, как добавить соответствующие заголовки XML и как добавить узлы, которые будут содержать различные разделы содержимого справки по командлетам.

> [!NOTE]
> Для получения полного представления файла справки откройте один из `dll-Help.xml` файлов, расположенных в каталоге установки Windows PowerShell. Например, `Microsoft.PowerShell.Commands.Management.dll-Help.xml` файл содержит содержимое для некоторых командлетов PowerShell.

### <a name="how-to-create-a-cmdlet-help-file"></a>Создание файла справки по командлету

1. Создайте текстовый файл и сохраните его с помощью кодировки UTF8. Имя файла должно иметь следующий формат, чтобы Windows PowerShell могла обнаружить его как файл справки командлета.

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. Добавьте следующие XML-заголовки в текстовый файл. Имейте в виду, что файл будет проверен в соответствии со схемой языка разметки Microsoft Assistance (MAML). В настоящее время PowerShell не предоставляет никаких средств для проверки файла.

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. Добавьте узел **команды** в файл справки командлета для каждого командлета в сборке. Каждый узел в узле **команды** относится к разным разделам справки по командлетам.

   В следующей таблице перечислены элементы XML для каждого узла, за которыми следуют описания каждого узла.

   |           Узел           |                                                                                                     Описание                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | Добавляет содержимое для разделов "имя" и "КРАТКИй Обзор" раздела справки по командлетам. Дополнительные сведения см. в разделе [Добавление имени командлета и кратких](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)сведений. |
   | `<maml:description>`     | Добавляет содержимое для раздела описания в разделе справки по командлету. Дополнительные сведения см. в [разделе Добавление подробного описания в раздел справки по командлетам](./how-to-add-a-cmdlet-description.md).                    |
   | `<command:syntax>`       | Добавляет содержимое для раздела СИНТАКСИСа раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление синтаксиса в раздел справки по командлетам](./how-to-add-syntax-to-a-cmdlet-help-topic.md).                                  |
   | `<command:parameters>`   | Добавляет содержимое для раздела "Параметры" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление параметров в раздел справки по командлетам](./how-to-add-parameter-information.md).                                  |
   | `<command:inputTypes>`   | Добавляет содержимое для раздела "ВХОДные данные" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление типов входных данных в раздел справки по командлетам](./how-to-add-input-types-to-a-cmdlet-help-topic.md).                        |
   | `<command:returnValues>` | Добавляет содержимое для раздела "выходные данные" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление возвращаемых значений в раздел справки по командлетам](./how-to-add-return-values-to-a-cmdlet-help-topic.md).                   |
   | `<maml:alertset>`        | Добавляет содержимое для раздела "Примечания" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление заметок в раздел справки по командлетам](./how-to-add-notes-to-a-cmdlet-help-topic.md).                                      |
   | `<command:examples>`     | Добавляет содержимое для раздела "примеры" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление примеров в раздел справки по командлетам](./how-to-add-examples-to-a-cmdlet-help-topic.md).                            |
   | `<maml:relatedLinks>`    | Добавляет содержимое для раздела "связанные ссылки" раздела справки по командлетам. Дополнительные сведения см. в [разделе Добавление связанных ссылок в раздел справки по командлетам](./how-to-add-related-links-to-a-cmdlet-help-topic.md).             |

## <a name="example"></a>Пример

 Ниже приведен пример узла **команды** , который содержит узлы для различных разделов справки по командлетам.

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a>См. также

 [Добавление имени командлета и кратких обзоров](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [Добавление подробного описания в раздел справки по командлету](./how-to-add-a-cmdlet-description.md)

 [Как добавить синтаксис в раздел справки для командлета](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [Добавление параметров в раздел справки по командлету](./how-to-add-parameter-information.md)

 [Как добавить типы входных данных в раздел справки для командлета](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [Как добавить возвращаемые значения в раздел справки для командлета](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [Добавление заметок в раздел справки по командлетам](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [Как добавить примеры в раздел справки для командлета](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [Как добавить связанные ссылки в раздел справки для командлета](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
