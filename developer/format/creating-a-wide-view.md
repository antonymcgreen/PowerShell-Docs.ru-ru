---
title: Создание широкое представление | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066725"
---
# <a name="creating-a-wide-view"></a>Создание широкого представления

Широкое представление отображает одно значение для каждого объекта, который отображается. Отображаемое значение может быть значение свойства объекта .NET или значение скрипта. По умолчанию отсутствует метка или заголовок для этого представления.

## <a name="a-wide-view-display"></a>Отображение широкое представление

В следующем примере показано, как Windows PowerShell отображает [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объект, возвращаемый [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) передается по конвейеру выходные данные командлета [ Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) командлета. (По умолчанию [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет возвращает представление таблицы.) В этом примере два столбца используются для отображения имени процесса для каждого возвращенного объекта. Имя свойства объекта не отображается, только значение свойства.

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a>Определение широкое представление

Следующий код XML показывает широкое представление схемы для [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

Следующие элементы XML используются для определения широкое представление:

- [Представление](./view-element-format.md) элемент является родительским для элемента широкое представление. (Это же родительский элемент для таблицы, список и представления пользовательского элемента управления).

- [Имя](./name-element-for-view-format.md) элемент задает имя представления. Этот элемент является обязательным для всех представлений.

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления. Этот элемент является обязательным.

- [GroupBy](./groupby-element-for-view-format.md) элемент определяет, когда отображается группу объектов. Новая группа запускается при каждом изменении значения определенных свойств или скрипта. Этот элемент является необязательным.

- [Элементов управления](./controls-element-for-view-format.md) элементов определяет пользовательские элементы управления, которые определяются широкое представление. Элементы управления позволяют для указания способа отображения данных. Этот элемент является необязательным. Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования. Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

- [WideControl](./widecontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении. В приведенном выше примере представление предназначена для отображения [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) свойство.

Например, полный файл форматирования, который определяет простой широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="providing-definitions-for-your-wide-view"></a>Предоставляет определения для вашей широкое представление

Широкие представления можно указать одно или несколько определений с помощью дочерних элементов элемента [WideControl](./widecontrol-element-format.md) элемент. Как правило представление будет иметь только одно определение. В следующем примере, представление будет содержать одно определение, которое отображает значение [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) свойство. Широкое представление может отображать значение свойства или значение сценария (не показано в примере).

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

Следующие элементы XML может использоваться для предоставления определения для широкое представление:

- [WideControl](./widecontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении.

- [AutoSize](./autosize-element-for-widecontrol-format.md) элемент указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных. Этот элемент является необязательным.

- [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) элемент указывает количество столбцов, отображаемых в широком представлении. Этот элемент является необязательным.

- [WideEntries](./wideentries-element-for-widecontrol-format.md) элемент предоставляет определения представления. В большинстве случаев представление будет иметь только одно определение. Этот элемент является обязательным.

- [WideEntry](./wideentry-element-for-widecontrol-format.md) элемент предоставляет определение представления. По крайней мере один [WideEntry](./wideentry-element-for-widecontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены. В большинстве случаев представление будет иметь только одно определение.

- [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент определяет объекты, которые отображаются по специфическим определением. Этот элемент является необязательным и требуется только в том случае, при определении нескольких [WideEntry](./wideentry-element-for-widecontrol-format.md) элементы, отображающие разные объекты.

- [WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении. В отличие от других типов представлений ширину элемента управления можно отобразить только один элемент.

- [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) определяет свойство, значение которого отображается в представлении. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент указывает сценарий, значение которого отображается в представлении. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

- [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) элемент определяет шаблон, который используется для отображения данных. Этот элемент является необязательным.

Например, полный файл форматирования, определяющий определение широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="defining-the-objects-that-use-the-wide-view"></a>Определение объектов, использующих широкое представление

Чтобы определить, какие объекты .NET использовать широкое представление двумя способами. Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления. В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.

В следующем примере показано, как для определения объектов, отображаемых элементом в широком представлении с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов. Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

Чтобы указать объекты, используемые широкое представление можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет, какие объекты отображаются по широкое представление.

- [TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает .NET, которое отображается в представлении. Полное имя типа .NET является обязательным. Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.

Например, полный файл форматирования, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов. Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении широкое представление и представление таблицы для те же объекты. Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

Чтобы указать объекты, используемые широкое представление можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет, какие объекты отображаются по широкое представление.

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении. Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.

В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение широкое представление, используя [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент. С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение. Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

Чтобы указать объекты, которые используются с конкретным определением широкое представление можно использовать следующие элементы XML:

- [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент определяет, какие объекты отображаются с помощью определения.

- [TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает .NET, которое отображается с помощью определения. При использовании этого элемента требуется полное имя типа .NET. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны. Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="displaying-groups-of-objects-in-a-wide-view"></a>Отображение групп объектов в широком представлении

Можно разделить объекты, которые отображаются по широкое представление, в группы. Это не означает, что можно определить группу, только для Windows PowerShell запускает новую группу, при каждом изменении значения определенных свойств или скрипта. В следующем примере запускается группу всякий раз, когда значение [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) изменения свойств.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Следующие элементы XML используются для определения при запуске группы:

- [GroupBy](./groupby-element-for-view-format.md) элемент определяет свойства или сценарий, который запускает новую группу и определяет порядок отображения группы.

- [PropertyName](./propertyname-element-for-groupby-format.md) элемент указывает свойство, которое запускает новую группу, при каждом изменении его значения. Необходимо указать свойство или скрипт для запуска в группу, но нельзя указать одновременно.

- [ScriptBlock](./scriptblock-element-for-groupby-format.md) элемент указывает сценарий, который запускает новую группу, при каждом изменении его значения. Необходимо указать сценарий или свойство для запуска в группу, но нельзя указать одновременно.

- [Метка](./label-element-for-groupby-format.md) элемент определяет метку, которая отображается в начале каждой группы. Помимо текст, заданный этим элементом Windows PowerShell отображает значение, которое активируется новая группа и добавляет пустой строки до и после метки. Этот элемент является необязательным.

- [Пользовательский элемент управления](./customcontrol-element-for-groupby-format.md) элемент определяет элемент управления, который используется для отображения данных. Этот элемент является необязательным.

- [CustomControlName](./customcontrolname-element-for-groupby-format.md) элемент указывает общий или просмотра элемента управления, который используется для отображения данных. Этот элемент является необязательным.

Например, полный файл форматирования, который определяет группы, см. в разделе [широкое представление (GroupBy)](./wide-view-groupby.md).

## <a name="using-format-strings"></a>С помощью строки формата

Строки форматирования могут добавляться в широком представлении, чтобы более детально определить способ отображения данных. Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

Следующие элементы XML может использоваться для указания шаблона формата:

- [WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении.

- [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) определяет свойство, значение которого отображается в представлении. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта. Скрипты можно вызвать любой метод объекта. Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

Следующий XML-элемент может использоваться для вызова метода `ToString` метод:

- [WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении.

- [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Широкое представление (Basic)](./wide-view-basic.md)

[Широкое представление (GroupBy)](./wide-view-groupby.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
