---
title: Создание файла справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 08e05939f8aee42f2cd502a3da7a528d8460dec1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083252"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>Как создать файл справки командлета

В этом разделе описывается, как создать допустимый XML-файл, содержащий содержимое для разделы справки по командлетам Windows PowerShell. В этом разделе рассматриваются принципы присвоения имен в файле справки, как добавить соответствующие заголовки XML и процесс добавления узлов, которые будут содержать разные разделы справки командлета.

> [!NOTE]
> Для просмотра полного файла справки, откройте один из файлов dll Help.xml расположен в каталоге установки Windows PowerShell. Например файл Microsoft.PowerShell.Commands.Management.dll Help.xml содержимым для нескольких командлетов Windows PowerShell.

### <a name="how-to-create-a-cmdlet-help-file"></a>Создание файла справки по командлетам

1. Создайте текстовый файл и сохраните его с использованием кодировки UTF8. Имя файла должно иметь следующий формат, Windows PowerShell позволяет распознавать его как файл справки для командлета.

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. Добавьте следующие заголовки XML в текстовом файле. Имейте в виду, что файл будет проверена на соответствие схеме языка моделирования нескольких агентов (MAML). В настоящее время Windows PowerShell не поддерживает любые средства для проверки файла.

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. Добавьте узел команд к файлу справки, командлет для каждого командлета в сборке. Каждый узел в узле команду относится к различным разделам раздела справки командлета.

   Ниже перечислены XML-элемент для каждого узла, следуют описания каждого узла.

   |Узел|Описание|
   |----------|-----------------|
   |`<details>`|Добавляет содержимое для ИМЕНИ и краткий обзор разделов раздела справки командлета. Дополнительные сведения см. в разделе [как добавить имя командлета и краткий обзор](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).|
   |`<maml:description>`|Добавляет содержимое раздела описание раздела справки командлета. Дополнительные сведения см. в разделе [Добавление подробное описание для раздела справки командлета](./how-to-add-a-cmdlet-description.md).|
   |`<command:syntax>`|Добавляет содержимое в разделе "СИНТАКСИС" раздела справки командлета. Дополнительные сведения см. в разделе [как добавить синтаксис для раздела справки командлета](./how-to-add-syntax-to-a-cmdlet-help-topic.md).|
   |`<command:parameters>`|Добавляет содержимое раздела параметров раздела справки командлета. Дополнительные сведения см. в разделе [как добавление параметров для раздела справки командлета](./how-to-add-parameter-information.md).|
   |`<command:inputTypes>`|Добавляет содержимое раздела справки командлета раздела входных данных. Дополнительные сведения см. в разделе [как добавление типов входных данных для раздела справки командлета](./how-to-add-input-types-to-a-cmdlet-help-topic.md).|
   |`<command:returnValues>`|Добавляет содержимое для раздела справки командлета разделе выходных данных. Дополнительные сведения см. в разделе [как добавить возвращаемые значения для раздела справки командлета](./how-to-add-return-values-to-a-cmdlet-help-topic.md).|
   |`<maml:alertset>`|Добавляет содержимое в раздел "Примечания" раздела справки командлета. Дополнительные сведения см. в разделе [Добавление заметки для раздела справки командлета](./how-to-add-notes-to-a-cmdlet-help-topic.md).|
   |`<command:examples>`|Добавляет содержимое для раздела "ПРИМЕРЫ" раздела справки командлета. Дополнительные сведения см. в разделе [как добавить примеры для раздела справки командлета](./how-to-add-examples-to-a-cmdlet-help-topic.md).|
   |`<maml:relatedLinks>`|Добавляет содержимое раздела ссылки по ТЕМЕ раздела справки командлета. Дополнительные сведения см. в разделе [как добавить ссылки по теме для раздела справки командлета](./how-to-add-related-links-to-a-cmdlet-help-topic.md).|

## <a name="example"></a>Пример

 Ниже приведен пример команды узла, который включает в себя узлы для раздела справки командлета на различные разделы.

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

 [Как добавить имя командлета и краткий обзор](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [Как добавить подробное описание раздела справки по командлету](./how-to-add-a-cmdlet-description.md)

 [Как добавить синтаксис для раздела справки по командлету](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [Как добавить параметры для раздела справки по командлету](./how-to-add-parameter-information.md)

 [Добавление типов входных данных для раздела справки по командлету](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [Как добавить возвращаемые значения для раздела справки по командлету](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [Добавление заметки для раздела справки командлета](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [Как добавить примеры для раздела справки по командлету](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [Добавление ссылки по теме раздела справки по командлету](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)