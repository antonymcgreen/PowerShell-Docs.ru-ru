---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxService в DSC для Linux
ms.openlocfilehash: ab6544762862c9b2477e92f0d782b13afb96f2c9
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093574"
---
# <a name="dsc-for-linux-nxservice-resource"></a>Ресурс nxService в DSC для Linux

Ресурс **nxService** в настройке требуемого состояния PowerShell предоставляет механизм управления службами на узле Linux.

## <a name="syntax"></a>Синтаксис

```
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Свойства
|  Свойство |  Описание |
|---|---|
| Name| Указывает имя службы или управляющей программы, которую нужно настроить.|
| Контроллер| Указывает тип контроллера для использования при настройке службы.|
| Включен| Указывает, запускается ли служба во время загрузки.|
| State| Указывает, запущена ли служба. Установите для этого свойства значение Stopped, чтобы служба не выполнялась. Установите для этого свойства значение Running, чтобы служба выполнялась.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если **идентификатор** первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|

## <a name="additional-information"></a>Дополнительные сведения

Ресурс **nxService** не создает определение или сценарий службы, если они не существуют. Ресурс **nxFile** настройки требуемого состояния PowerShell можно использовать для управления существованием или содержанием сценария или файла определения службы.

## <a name="example"></a>Пример

В следующем примере показана конфигурация службы httpd (для HTTP-сервера Apache), зарегистрированной с использованием контроллера службы **SystemD**.

```powershell
Import-DSCResource -Module nx

Node $node {
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```