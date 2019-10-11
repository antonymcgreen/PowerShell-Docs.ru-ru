---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс User в DSC
ms.openlocfilehash: dec432c2ff1b4e4408165fef391e77cbf1d85ac4
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953011"
---
# <a name="dsc-user-resource"></a>Ресурс User в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **User** в DSC Windows PowerShell предоставляет механизм управления локальными учетными записями на целевом узле.

## <a name="syntax"></a>Синтаксис

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|UserName |Указывает имя учетной записи, для которой требуется обеспечить определенное состояние. |
|Описание |Указывает описание учетной записи пользователя. |
|Отключен |Указывает, включена ли учетная запись. Присвойте этому свойству значение `$true`, чтобы отключить учетную запись, и `$false`, чтобы включить ее. |
|FullName |Представляет строку с полным именем для учетной записи пользователя. |
|Пароль |Указывает пароль для этой учетной записи. |
|PasswordChangeNotAllowed |Указывает, может ли пользователь изменить пароль. Присвойте этому свойству значение `$true`, чтобы пользователь не мог изменить пароль, и `$false`, чтобы мог. Значение по умолчанию: `$false`. |
|PasswordChangeRequired |Указывает, требуется ли смена пароля при следующем входе пользователя в систему. Присвойте этому свойству значение `$true`, если пользователь должен изменить пароль. Значение по умолчанию: `$true`. |
|PasswordNeverExpires |Указывает, может ли истечь срок действия пароля. Присвойте этому свойству значение `$true`, чтобы срок действия пароля никогда не истекал. Задайте значение `$false`, чтобы ограничить срок действия пароля. Значение по умолчанию: `$false`. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли учетная запись. Присвойте этому свойству значение **Present**, чтобы гарантировать, что учетная запись существует, и **Absent** в противном случае. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

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