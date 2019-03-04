---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
description: Предоставляет механизм для управления локальными группами на целевом узле.
title: Ресурс DSC GroupSet
ms.openlocfilehash: afe4c4d33ac5620c411481e93d76a1f90c26deb9
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047715"
---
# <a name="dsc-groupset-resource"></a>Ресурс DSC GroupSet

> Область применения. Windows PowerShell 5.0

Ресурс **GroupSet** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле. Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Group](groupResource.md) для каждой группы, указанной в параметре `GroupName`.

Используйте этот ресурс, если необходимо добавить один и тот же список участников в несколько групп или удалить его из нескольких групп, а также если необходимо удалить или добавить несколько групп с одинаковым списком участников.

## <a name="syntax"></a>Синтаксис

```
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Ensure = [string] { Absent | Present }  ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| GroupName| Имена групп, для которых требуется обеспечить определенное состояние.|
| MembersToExclude| Это свойство используется для удаления участников из существующего членства в группах. Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приведет к ошибке.|
| Учетные данные| Учетные данные, необходимые для доступа к удаленным ресурсам. **Примечание**. Учетная запись должна иметь соответствующие разрешения Active Directory для добавления в группу любых нелокальных учетных записей; в противном случае произойдет ошибка.
| Ensure| Указывает, существуют ли группы. Если группы не должны существовать, укажите для этого свойства значение Absent. Если группы должны существовать, укажите для этого свойства значение Present (используется по умолчанию).|
| Члены группы| Используйте это свойство для замены текущего членства в группе заданными участниками. Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*. Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**. Это приведет к ошибке.|
| MembersToInclude| Это свойство используется для добавления участников в существующее членство в группе. Значение этого свойства хранится в массиве строк в формате *домен*\\*имя_пользователя*. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приведет к ошибке.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".|

## <a name="example-1-ensuring-groups-are-present"></a>Пример 1: Обеспечение групп

В приведенном ниже примере показано, как обеспечить существование двух групп: myGroup и myOtherGroup.

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> Для простоты в этом примере используются учетные данные в виде обычного текста. Сведения о шифровании учетных данных в MOF-файле конфигурации см. в разделе [Защита MOF-файла](../../../pull-server/secureMOF.md).