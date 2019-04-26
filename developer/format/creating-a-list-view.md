---
title: Создание представления списка | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c7a40ca-1786-46f0-bab5-6ce229daa7ee
caps.latest.revision: 14
ms.openlocfilehash: 25d24063501196d44e0f806a55bb699c82f771ce
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066861"
---
# <a name="creating-a-list-view"></a>Создание представления списка

Представление списка отображает данные в виде одного столбца (в последовательном порядке). Данные, отображаемые в списке может быть значение свойства .NET или значение скрипта.

## <a name="a-list-view-display"></a>Отображения представления списка

Ниже показано, как Windows PowerShell отображает свойства [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета. В этом примере были возвращены три объекта, с каждым объектом, который отделен от предыдущего объекта с пустыми строками.

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a>Определение представления списка

Следующий код XML показывает схему представления списка для отображения нескольких свойств [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекта. Укажите каждое свойство, которое будет отображаться в представлении списка.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

Следующие элементы XML используются для определения представления списка:

- [Представление](./view-element-format.md) элемент является родительским для элемента представления списка. (Это же родительского элемента для таблицы, представления широкий и пользовательских элементов управления).

- [Имя](./name-element-for-view-format.md) элемент задает имя представления. Этот элемент является обязательным для всех представлений.

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления. Этот элемент является обязательным.

- [GroupBy](./groupby-element-for-view-format.md) элемент определяет, когда отображается группу объектов. Новая группа запускается при каждом изменении значения определенных свойств или скрипта. Этот элемент является необязательным.

- [Элементов управления](./controls-element-for-view-format.md) элемент определяет пользовательские элементы управления, которые определены в представлении списка. Элементы управления позволяют для указания способа отображения данных. Этот элемент является необязательным. Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования. Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

- [ListControl](./listcontrol-element-format.md) элемент определяет отображаемые в представлении и форматирования. Как и с другими представлениями, представление списка можно отобразить значения свойств объекта или значения, создаваемые сценарием.

Например, полный файл форматирования, определяющий простое представление списка, см. в разделе [представление списка (Basic)](./list-view-basic.md).

## <a name="providing-definitions-for-your-list-view"></a>Предоставляет определения для представления списка

Списки можно указать одно или несколько определений с помощью дочерних элементов элемента [ListControl](./listcontrol-element-format.md) элемент. Как правило представление будет иметь только одно определение. В следующем примере, представление будет содержать одного определения, отображающий несколько свойств [System.Diagnostics.Process? Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) объекта. Представление списка можно отобразить значение свойства или значение сценария (не показано в примере).

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

Следующие элементы XML может использоваться для предоставления определения для представления списка:

- [ListControl](./listcontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении.

- [ListEntries](./listentries-element-for-listcontrol-format.md) элемент предоставляет определения представления. В большинстве случаев представление будет иметь только одно определение. Этот элемент является обязательным.

- [ListEntry](./listentry-element-for-listcontrol-format.md) элемент предоставляет определение представления. По крайней мере один [ListEntry](./listentry-element-for-listcontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены. В большинстве случаев представление будет иметь только одно определение.

- [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент определяет объекты, которые отображаются по специфическим определением. Этот элемент является необязательным и требуется только в том случае, при определении нескольких [ListEntry](./listentry-element-for-listcontrol-format.md) элементы, отображающие разные объекты.

- [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) определяет свойства и скрипты, значения которых отображаются в строках представления "list".

- [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) элемент указывает свойство или скрипта, значение которого отображается в строке в представлении списка. Представление списка необходимо указать по крайней мере одно свойство или скрипт. Не ограничено максимальное число строк, которые могут быть указаны.

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) определяет свойство, значение которого отображается в строке. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент указывает сценарий, значение которого отображается в строке. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

- [Метка](./label-element-for-listitem-for-listcontrol-format.md) элемент указывает метку, которая отображается слева от значения свойства или сценарий, в строке. Этот элемент является необязательным. Если метка не указана, отображается имя свойства или скрипт. Полный пример см. в разделе [представление списка (метки)](./list-view-labels.md).

- [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) элемент указывает условие, которое должен существовать для строки для отображения. Дополнительные сведения о добавлении условий в представлении списка см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md). Этот элемент является необязательным.

- [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) элемент определяет шаблон, который используется для отображения значения свойства или скрипт. Этот элемент является необязательным.

Например, полный файл форматирования, определяющий простое представление списка, см. в разделе [представление списка (Basic)](./list-view-basic.md).

## <a name="defining-the-objects-that-use-the-list-view"></a>Определив объекты, используемые в представлении списка

Существует два способа определить, какие объекты .NET использованию представления списка. Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления. В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.

В следующем примере показано, как для определения объектов, которые отображаются в представлении списка с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов. Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.

- [TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает объект .NET, которое отображается в представлении. Полное имя типа .NET является обязательным. Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.

Например, полный файл форматирования, см. в разделе [представление списка (Basic)](./list-view-basic.md).

В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов. Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении представления списка и представление таблицы для те же объекты. Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении. Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.

В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение представления списка, используя [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент. С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение. Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

Чтобы указать объекты, которые используются с конкретным определением в представлении списка можно использовать следующие элементы XML:

- [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент определяет, какие объекты отображаются с помощью определения.

- [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) элемент указывает объект .NET, которое отображается с помощью определения. При использовании этого элемента, требуется полное имя типа .NET. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны. Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="displaying-groups-of-objects-in-a-list-view"></a>Отображение групп объектов в представлении списка

Можно разделить объекты, которые отображаются в представлении списка в группы. Это не означает, что можно определить группу, только для Windows PowerShell запускает новую группу, при каждом изменении значения определенных свойств или скрипта. В следующем примере запускается группу всякий раз, когда значение [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) изменения свойств.

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

Например, полный файл форматирования, который определяет группы, см. в разделе [представление списка (GroupBy)](./list-view-groupby.md).

## <a name="using-format-strings"></a>С помощью строки формата

Строки форматирования можно добавить в представление, чтобы более детально определить способ отображения данных. Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

Следующие элементы XML может использоваться для указания шаблона формата:

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент указывает данные, которые отображаются в представлении.

- [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) определяет свойство, значение которого отображается в представлении. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта. Скрипты можно вызвать любой метод объекта. Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

Следующий XML-элемент может использоваться для вызова метода `ToString` метод:

- [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент указывает данные, которые отображаются в представлении.

- [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
