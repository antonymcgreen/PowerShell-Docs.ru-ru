---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Group в DSC
ms.openlocfilehash: 695a914683c6daff44dd2a6c94b6353acf881030
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954661"
---
# <a name="dsc-group-resource"></a>Ресурс Group в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Group** в DSC Windows PowerShell предоставляет механизм управления локальными группами на целевом узле.

## <a name="syntax"></a>Синтаксис

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|GroupName |Имя группы, для которой требуется обеспечить определенное состояние. |
|Учетные данные |Учетные данные, необходимые для доступа к удаленным ресурсам. Учетная запись должна иметь соответствующие разрешения Active Directory на добавление в группу любых нелокальных учетных записей. Иначе во время выполнения конфигурации на целевом узле произойдет ошибка.
|Описание |Описание группы. |
|Члены |Используйте это свойство для замены текущего членства в группе заданными участниками. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **MembersToExclude** или **MembersToInclude**. Это приводит к ошибке. |
|MembersToExclude |Это свойство используется для удаления участников из существующего членства в группе. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приводит к ошибке. |
|MembersToInclude |Это свойство используется для добавления участников в существующее членство в группе. Значение этого свойства хранится в массиве строк в формате `Domain\UserName`. Если вы задали это свойство в конфигурации, не используйте свойство **Members**. Это приведет к ошибке. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли группа. Чтобы убедиться, что группа не существует, укажите для этого свойства значение **Absent**. Если группа должна существовать, укажите для этого свойства значение **Present**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example-1-ensure-group-is-not-present"></a>Пример 1: Убедитесь, что группа отсутствует

Следующий пример показывает, как проверить, что группа с именем TestGroup не существует.

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a>Пример 2. Добавление пользователя домена в локальную группу

Следующий пример демонстрирует добавление пользователя Active Directory в группу локальных администраторов в лабораторной сборке с несколькими компьютерами, в которой уже используется объект PSCredential для учетной записи локального администратора. Так как этот объект также используется для учетной записи администратора домена (после повышения роли домена), нам потребуется преобразовать этот существующий объект PSCredential в понятные учетные данные домена. Затем мы сможем добавить пользователя домена в группу локальных администраторов на рядовом сервере.

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a>Пример 3

В примере ниже показано, как настроить локальную группу TigerTeamAdmins на сервере TigerTeamSource.Contoso.Com, чтобы она не содержала определенную учетную запись домена Contoso\JerryG.

```powershell
Configuration SecureTigerTeamSource {
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node TigerTeamSource.Contoso.Com {
        Group TigerTeamAdmins {
            GroupName        = 'TigerTeamAdmins'
            Ensure           = 'Present'
            MembersToExclude = "Contoso\JerryG"
        }
    }
}
```