---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxSshAuthorizedKeys в DSC для Linux
ms.openlocfilehash: 3a62bb7a3dbdebae4f0ca6084db1624c1b76ab1f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464474"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a>Ресурс nxSshAuthorizedKeys в DSC для Linux

Ресурс **NxAuthorizedKeys** в DSC PowerShell обеспечивает механизм управления авторизованными SSH-ключами для указанного пользователя.

## <a name="syntax"></a>Синтаксис

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|KeyComment |Уникальный комментарий к ключу. Используется для уникальной идентификации ключей. |
|Имя пользователя |Указывает, для какого пользователя осуществляется управление авторизованными SSH-ключами. Если свойство не определено, пользователь по умолчанию — **root**. |
|Клавиши |Указывает содержимое ключа Требуется, если свойство **Ensure** имеет значение **Present**.|

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, определен ли ключ. Если это свойство имеет значение **Absent**, обеспечивается отсутствие ключа в файле авторизованных ключей пользователя. Если это свойство имеет значение **Present**, обеспечивается наличие определения ключа в файле авторизованных ключей пользователя. |

## <a name="example"></a>Пример

В следующем примере определяется общедоступный авторизованный SSH-ключ для пользователя monuser.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```
