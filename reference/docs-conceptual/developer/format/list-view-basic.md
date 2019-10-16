---
title: Представление списка (основное) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 918f381c-43e6-4594-a468-a40bfa8a16d6
caps.latest.revision: 7
ms.openlocfilehash: 3c94d8e98f179286112a417230fce659dc0b614c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362813"
---
# <a name="list-view-basic"></a>Представление списка (базовое)

В этом примере показано, как реализовать базовое представление списка, в котором отображается [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) . Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

### <a name="to-load-this-formatting-file"></a>Загрузка этого файла форматирования

1. Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.

2. Сохраните текстовый файл. Не забудьте добавить в файл расширение `format.ps1xml`, чтобы обозначить его как файл форматирования.

3. Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile`.

   > [!WARNING]
   > Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell. При выполнении командлета необходимо использовать параметр `prependPath`, и этот файл форматирования нельзя загрузить как модуль.

## <a name="demonstrates"></a>Демонстрирующее

В этом файле форматирования показаны следующие XML-элементы:

- Элемент [Name](./name-element-for-view-format.md) для представления.

- Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.

- Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.

- Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.

- Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.

## <a name="example"></a>Пример

Следующий XML-код определяет представление списка, в котором отображаются четыре свойства элемента [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект. В каждой строке отображается имя свойства, за которым следует значение свойства.

```xml
<Configuration>
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
</Configuration>
```

В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>См. также:

[Примеры файлов форматирования](./examples-of-formatting-files.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
