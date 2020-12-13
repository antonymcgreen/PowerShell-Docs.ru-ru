---
ms.date: 09/13/2016
ms.topic: reference
title: Представление списка (с группировкой)
description: Представление списка (с группировкой)
ms.openlocfilehash: e039c38d1e4e93f65a508fe60aaaf35c64ebe2ed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666626"
---
# <a name="list-view-groupby"></a>Представление списка (с группировкой)

В этом примере показано, как реализовать представление списка, которое разделяет строки списка на группы. В этом представлении списка отображаются свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) . Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

### <a name="to-load-this-formatting-file"></a>Загрузка этого файла форматирования

1. Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.

2. Сохраните текстовый файл. Не забудьте добавить `format.ps1xml` расширение в файл, чтобы обозначить его как файл форматирования.

3. Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile` .

   > [!WARNING]
   > Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell. Этот параметр необходимо использовать `prependPath` при выполнении командлета, и этот файл форматирования нельзя загрузить как модуль.

## <a name="demonstrates"></a>Что демонстрирует

В этом файле форматирования показаны следующие XML-элементы:

- Элемент [Name](./name-element-for-view-format.md) для представления.

- Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.

- Элемент [GroupBy](./viewselectedby-element-format.md) , определяющий, как отображается новая группа объектов.

- Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.

- Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.

- Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.

## <a name="example"></a>Пример

Следующий XML-код определяет представление списка, которое запускает новую группу всякий раз, когда изменяется значение свойства [System. ServiceProcess. ServiceController. status](/dotnet/api/System.ServiceProcess.ServiceController.Status) . При запуске каждой группы отображается пользовательская метка, которая содержит новое значение свойства.

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
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
                <PropertyName>ServiceType</PropertyName>
              </ListItem>
            </ListItems>
          </ListEntry>
        </ListEntries>
      </ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования. Windows PowerShell автоматически добавляет пустые строки, добавленные до и после метки группы.

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>См. также:

[Примеры файлов форматирования](./examples-of-formatting-files.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
