---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
description: Предоставляет механизм для управления локальными группами на целевом узле.
title: Ресурс DSC GroupSet
ms.openlocfilehash: d36274741b2c96a0852f384ccf5d187ac8d27131
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953181"
---
# <a name="dsc-groupset-resource"></a>Ресурс DSC GroupSet

> Область применения: Windows PowerShell 5.x

Ресурс **GroupSet** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле. Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс Group](groupResource.md) для каждой группы, указанной в параметре `GroupName`.

Используйте этот ресурс, если необходимо добавить один и тот же список участников в несколько групп или удалить его из нескольких групп, а также если необходимо удалить или добавить несколько групп с одинаковым списком участников.

## <a name="syntax"></a>Синтаксис

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Members = [string[]] ]
    [ Description = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|GroupName |Имена групп, для которых требуется обеспечить определенное состояние. |
|Члены |Используйте это свойство для замены текущего членства в группе заданными участниками. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**. Это приведет к ошибке. |
|Описание |Описание группы. |
|MembersToInclude |Это свойство используется для добавления участников в существующее членство в группе. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приведет к ошибке. |
|MembersToExclude |Это свойство используется для удаления участников из существующего членства в группах. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приведет к ошибке. |
|Учетные данные |Учетные данные, необходимые для доступа к удаленным ресурсам. Учетная запись должна иметь соответствующие разрешения Active Directory для добавления в группу любых нелокальных учетных записей; в противном случае произойдет ошибка. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существуют ли группы. Если группы не должны существовать, укажите для этого свойства значение **Absent**. Если группы должны существовать, укажите для этого свойства значение **Present** (используется по умолчанию). Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example-1-ensuring-groups-are-present"></a>Пример 1: проверка наличия групп

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