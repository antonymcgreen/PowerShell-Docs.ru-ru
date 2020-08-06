---
title: Создание представления списка | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 24eb673e0db011a1439fa5ba1f2966fcc3bdc338
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783778"
---
# <a name="creating-a-list-view"></a>Создание представления списка

Представление списка отображает данные в одном столбце (в последовательном порядке). Данные, отображаемые в списке, могут быть значением свойства .NET или значением скрипта.

## <a name="a-list-view-display"></a>Отображение представления списка

В следующих выходных данных показано, как Windows PowerShell отображает свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) . В этом примере были возвращены три объекта, каждый из которых отделяется от предыдущего объекта на пустую строку.

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

В следующем коде XML показана схема представления списка для отображения нескольких свойств [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект. Необходимо указать каждое свойство, которое должно отображаться в представлении списка.

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

Для определения представления списка используются следующие XML-элементы:

- Элемент [View](./view-element-format.md) является родительским элементом представления списка. (Это тот же родительский элемент для представлений таблицы, широкие и настраиваемых элементов управления.)

- Элемент [Name](./name-element-for-view-format.md) указывает имя представления. Этот элемент является обязательным для всех представлений.

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, которые используют представление. Этот элемент является обязательным.

- Элемент [GroupBy](./groupby-element-for-view-format.md) определяет, когда отображается новая группа объектов. Новая группа запускается каждый раз при изменении значения определенного свойства или сценария. Этот элемент является необязательным.

- Элемент [Controls](./controls-element-for-view-format.md) определяет пользовательские элементы управления, определяемые представлением списка. Элементы управления позволяют дополнительно указать способ отображения данных. Этот элемент является необязательным. Представление может определять собственные пользовательские элементы управления или использовать стандартные элементы управления, которые могут использоваться любыми представлениями в файле форматирования. Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

- Элемент [ListControl](./listcontrol-element-format.md) определяет, что отображается в представлении и как оно форматируется. Как и во всех других представлениях, представление списка может отображать значения свойств объектов или значений, создаваемых скриптом.

Пример полного файла форматирования, определяющего простое представление списка, см. в разделе [представление списка (базовый)](./list-view-basic.md).

## <a name="providing-definitions-for-your-list-view"></a>Предоставление определений для представления списка

Представления списка могут предоставлять одно или несколько определений с помощью дочерних элементов элемента [ListControl](./listcontrol-element-format.md) . Как правило, представление будет иметь только одно определение. В следующем примере представление предоставляет одно определение, в котором отображаются несколько свойств [System. Diagnostics. Process? DisplayProperty = FullName](/dotnet/api/System.Diagnostics.Process) , объект. В представлении списка может отображаться значение свойства или значение скрипта (не показано в примере).

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

Следующие XML-элементы можно использовать для предоставления определений для представления списка:

- Элемент [ListControl](./listcontrol-element-format.md) и его дочерние элементы определяют, что отображается в представлении.

- Элемент [листентриес](./listentries-element-for-listcontrol-format.md) предоставляет определения представления. В большинстве случаев представление будет иметь только одно определение. Этот элемент является обязательным.

- Элемент [листентри](./listentry-element-for-listcontrol-format.md) предоставляет определение представления. Требуется по крайней мере один [листентри](./listentry-element-for-listcontrol-format.md) ; Однако максимальное количество элементов, которые можно добавить, не ограничено. В большинстве случаев представление будет иметь только одно определение.

- Элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) указывает объекты, отображаемые конкретным определением. Этот элемент является необязательным и необходим только при определении нескольких элементов [листентри](./listentry-element-for-listcontrol-format.md) , отображающих разные объекты.

- Элемент [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) указывает свойства и скрипты, значения которых отображаются в строках представления списка.

- Элемент [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) указывает свойство или скрипт, значение которого отображается в строке представления списка. В представлении списка должно быть указано по крайней мере одно свойство или скрипт. Максимальное число строк, которое можно указать, не ограничено.

- Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) указывает свойство, значение которого отображается в строке. Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.

- Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) указывает скрипт, значение которого отображается в строке. Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.

- Элемент [Label](./label-element-for-listitem-for-listcontrol-format.md) Указывает метку, которая отображается слева от значения свойства или скрипта в строке. Этот элемент является необязательным. Если метка не указана, отображается имя свойства или скрипт. Полный пример см. в разделе [представление списка (метки)](./list-view-labels.md).

- Элемент [итемселектионкондитион](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) указывает условие, которое должно существовать для отображения строки. Дополнительные сведения о добавлении условий в представление списка см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md). Этот элемент является необязательным.

- Элемент [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) задает шаблон, используемый для вывода значения свойства или скрипта. Этот элемент является необязательным.

Пример полного файла форматирования, определяющего простое представление списка, см. в разделе [представление списка (базовый)](./list-view-basic.md).

## <a name="defining-the-objects-that-use-the-list-view"></a>Определение объектов, использующих представление списка

Существует два способа определения объектов .NET, использующих представление списка. Элемент [виевселектедби](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться всеми определениями представления, или можно использовать элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) для определения объектов, отображаемых определенным определением представления. В большинстве случаев представление имеет только одно определение, поэтому объекты обычно определяются элементом [виевселектедби](./viewselectedby-element-format.md) .

В следующем примере показано, как определить объекты, отображаемые представлением списка с помощью элементов [виевселектедби](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) . Количество элементов [TypeName](./typename-element-for-viewselectedby-format.md) , которые можно указать, не ограничено, и их порядок не важен.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.

- Элемент [TypeName](./typename-element-for-viewselectedby-format.md) задает объект .NET, отображаемый представлением. Требуется полное имя типа .NET. Необходимо указать по крайней мере один тип или набор элементов для представления, но максимальное количество заданных объектов не предусмотрено.

Пример полного файла форматирования см. в разделе [представление списка (базовый)](./list-view-basic.md).

В следующем примере используются элементы [виевселектедби](./viewselectedby-element-format.md) и [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) . Используйте наборы выбора, в которых имеется связанный набор объектов, отображаемых с помощью нескольких представлений, например при определении представления списка и табличного представления для тех же объектов. Дополнительные сведения о создании набора выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.

- Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) указывает набор объектов, которые могут быть отображены представлением. Необходимо указать хотя бы один набор выбора или тип для представления, но максимальное количество элементов, которое можно указать, не существует.

В следующем примере показано, как определить объекты, отображаемые определенным определением представления списка с помощью элемента [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) . С помощью этого элемента можно указать имя типа .NET объекта, набор элементов выбора объектов или условие выбора, которое указывает, когда используется определение. Дополнительные сведения о создании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

Следующие XML-элементы можно использовать для указания объектов, которые используются в определенном определении представления списка:

- Элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) определяет, какие объекты отображаются в определении.

- Элемент [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) указывает объект .NET, который отображается в определении. При использовании этого элемента требуется полное имя типа .NET. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.

- Элемент [селектионсетнаме](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показан) задает набор объектов, которые могут отображаться в этом определении. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.

- Элемент [селектионкондитион](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает условие, которое должно существовать, чтобы использовать это определение. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено. Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="displaying-groups-of-objects-in-a-list-view"></a>Отображение групп объектов в представлении списка

Можно разделить объекты, отображаемые представлением списка, на группы. Это не означает, что вы определяете группу, а только то, что Windows PowerShell запускает новую группу всякий раз, когда изменяется значение определенного свойства или сценария. В следующем примере новая группа запускается всякий раз, когда изменяется свойство [System. ServiceProcess. ServiceController. serviceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) .

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Следующие XML-элементы используются для определения времени запуска группы:

- Элемент [GroupBy](./groupby-element-for-view-format.md) определяет свойство или скрипт, который запускает новую группу и определяет, как будет отображаться группа.

- Элемент [PropertyName](./propertyname-element-for-groupby-format.md) указывает свойство, которое запускает новую группу при изменении ее значения. Необходимо указать свойство или скрипт для запуска группы, но нельзя указать и то, и другое.

- Элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) указывает скрипт, который запускает новую группу при изменении ее значения. Необходимо указать скрипт или свойство для запуска группы, но нельзя указать и то, и другое.

- Элемент [Label](./label-element-for-groupby-format.md) определяет метку, которая отображается в начале каждой группы. В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает значение, вызвавшее новую группу, и добавляет пустую строку до и после метки. Этот элемент является необязательным.

- Элемент [Ошибка customcontrol](./customcontrol-element-for-groupby-format.md) определяет элемент управления, используемый для вывода данных. Этот элемент является необязательным.

- Элемент [кустомконтролнаме](./customcontrolname-element-for-groupby-format.md) указывает общий элемент управления или представление, которое используется для отображения данных. Этот элемент является необязательным.

Пример полного файла форматирования, определяющего группы, см. в разделе [представление списка (GroupBy)](./list-view-groupby.md).

## <a name="using-format-strings"></a>Использование строк формата

Строки форматирования можно добавить в представление, чтобы дополнительно определить способ отображения данных. В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

Для указания шаблона формата можно использовать следующие XML-элементы:

- Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) указывает данные, отображаемые представлением.

- Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) указывает свойство, значение которого отображается в представлении. Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.

- Элемент [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.

- Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении. Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.

В следующем примере `ToString` метод вызывается для форматирования значения скрипта. Скрипты могут вызывать любой метод объекта. Таким образом, если у объекта есть метод, такой как `ToString` , имеющий параметры форматирования, скрипт может вызвать этот метод для форматирования выходного значения скрипта.

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

Для вызова метода можно использовать следующий XML-элемент `ToString` :

- Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) указывает данные, отображаемые представлением.

- Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении. Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md)
