---
title: Представление списка (метки) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: da45bd8dce7ac2149de6a34c11d5419d6cb4ddb0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773391"
---
# <a name="list-view-labels"></a>Представление списка (метки)

В этом примере показано, как реализовать представление списка, в котором отображается пользовательская метка для каждой строки списка. В этом представлении списка отображаются свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемое командлетом [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) . Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

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

- Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.

- Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.

- Элемент [Label](./label-element-for-listitem-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.

- Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.

## <a name="example"></a>Пример

Следующий XML-код определяет представление списка, в каждой строке которого отображается пользовательская метка. В этом случае метка содержит имя свойства с каждой буквой в прописной буквы и словом "свойство". В каждой строке отображается имя свойства, за которым следует значение свойства.

```xml
<Configuration>
  <ViewDefinitions>
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
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
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

В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a>См. также

[Примеры файлов форматирования](./examples-of-formatting-files.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
