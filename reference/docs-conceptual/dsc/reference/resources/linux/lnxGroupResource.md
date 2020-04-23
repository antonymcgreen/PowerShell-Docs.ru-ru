---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxGroup в DSC для Linux
ms.openlocfilehash: 098ae2e8ab183934ec3c185c0fd237731b1353dc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953211"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>Ресурс nxGroup в DSC для Linux

Ресурс **nxGroup** в DSC PowerShell предоставляет механизм управления локальными группами на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|GroupName |Указывает имя группы, для которой требуется обеспечить определенное состояние. |
|Члены |Указывает членов группы. |
|MembersToInclude |Указывает пользователей, которых нужно добавить в группу. |
|MembersToExclude |Указывает пользователей, которых нужно исключить из группы. |
|PreferredGroupID |По возможности задает в качестве идентификатора группы указанное значение. Если этот идентификатор группы сейчас используется, выбирается следующий доступный идентификатор группы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, нужно ли проверять существование группы. Чтобы гарантировать, что группа существует, укажите для этого свойства значение **Present**. Чтобы гарантировать, что группа не существует, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |

## <a name="example"></a>Пример

В следующем примере удостоверяется, что пользователь monuser существует и является членом группы DBusers.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```