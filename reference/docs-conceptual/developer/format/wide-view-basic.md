---
ms.date: 09/13/2016
ms.topic: reference
title: Широкое представление (базовое)
description: Широкое представление (базовое)
ms.openlocfilehash: bfc647da9b78fcd22aac83cf330e466b6759471c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667697"
---
# <a name="wide-view-basic"></a>Широкое представление (базовое)

В этом примере показано, как реализовать базовое представление, которое отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые `Get-Service` командлетом. Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

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

- Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) , определяющий свойство, отображаемое представлением.

## <a name="example"></a>Пример

Следующий XML-код определяет расширенное представление, которое отображает значение свойства [System. ServiceProcess. ServiceController. ServiceName](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) .

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a>См. также:

[Примеры файлов форматирования](./examples-of-formatting-files.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
