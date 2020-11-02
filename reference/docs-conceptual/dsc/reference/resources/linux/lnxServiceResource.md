---
ms.date: 07/17/2020
ms.topic: reference
title: Ресурс nxService в DSC для Linux
description: Ресурс nxService в DSC для Linux
ms.openlocfilehash: 4eefe491c491c9245732def1cc85260f368ef9e1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648783"
---
# <a name="dsc-for-linux-nxservice-resource"></a>Ресурс nxService в DSC для Linux

Ресурс **nxService** в настройке требуемого состояния PowerShell предоставляет механизм управления службами на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
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

|Свойство |Description |
|---|---|
|Имя |Указывает имя службы или управляющей программы, которую нужно настроить. |
|Контроллер |Указывает тип контроллера для использования при настройке службы. |
|Активировано |Указывает, запускается ли служба во время загрузки. |
|Штат |Указывает, запущена ли служба. Установите для этого свойства значение **Stopped** , чтобы служба не выполнялась. Установите для этого свойства значение **Running** , чтобы служба выполнялась. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |

## <a name="additional-information"></a>Дополнительные сведения

Ресурс **nxService** не создает определение или сценарий службы, если они не существуют. Ресурс **nxFile** настройки требуемого состояния PowerShell можно использовать для управления существованием или содержанием сценария или файла определения службы.

## <a name="example"></a>Пример

В следующем примере показана конфигурация службы httpd (для HTTP-сервера Apache), зарегистрированной с использованием контроллера службы **SystemD** .

```powershell
Import-DSCResource -Module nx

Node $node
{
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```
