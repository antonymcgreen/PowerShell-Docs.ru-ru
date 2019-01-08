---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс User в DSC
ms.openlocfilehash: 04543351df19160a2da05ccea96e5d392d8c55bf
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047886"
---
# <a name="dsc-user-resource"></a>Ресурс User в DSC

Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс **User** в DSC Windows PowerShell предоставляет механизм управления локальными учетными записями на целевом узле.

## <a name="syntax"></a>Синтаксис

```
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| UserName| Указывает имя учетной записи, для которой требуется обеспечить определенное состояние.|
| Описание| Указывает описание учетной записи пользователя.|
| Отключен| Указывает, включена ли учетная запись. Присвойте этому свойству значение `$true`, чтобы отключить учетную запись, и `$false`, чтобы включить ее.|
| Ensure| Указывает, существует ли учетная запись. Присвойте этому свойству значение Present, если учетная запись существует, и Absent, если не существует.|
| FullName| Представляет строку с полным именем для учетной записи пользователя.|
| Пароль| Указывает пароль для этой учетной записи. |
| PasswordChangeNotAllowed| Указывает, может ли пользователь изменить пароль. Присвойте этому свойству значение `$true`, чтобы пользователь не мог изменить пароль, и `$false`, чтобы мог. Значение по умолчанию: `$false`.|
| PasswordChangeRequired| Указывает, требуется ли смена пароля при следующем входе пользователя в систему. Присвойте этому свойству значение `$true`, если пользователь должен изменить пароль. Значение по умолчанию: `$true`.|
| PasswordNeverExpires| Указывает, может ли истечь срок действия пароля. Присвойте этому свойству значение `$true`, чтобы срок действия пароля никогда не истекал, а в противном случае — значение `$false`. Значение по умолчанию: `$false`.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|

## <a name="example"></a>Пример

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```