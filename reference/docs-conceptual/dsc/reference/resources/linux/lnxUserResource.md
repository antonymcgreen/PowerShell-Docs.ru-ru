---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxUser в DSC для Linux
ms.openlocfilehash: 4cf8080fbfa58e082ed007d42d6aa2648d1cf58a
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557181"
---
# <a name="dsc-for-linux-nxuser-resource"></a>Ресурс nxUser в DSC для Linux

Ресурс **nxUser** в DSC PowerShell предоставляет механизм управления локальными пользователями на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxUser <string> #ResourceName
{
    UserName = <string>
    [ FullName = <string> ]
    [ Description = <string> ]
    [ Password = <string> ]
    [ Disabled = <bool> ]
    [ PasswordChangeRequired = <bool> ]
    [ HomeDirectory = <string> ]
    [ GroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Указывает имя учетной записи, для которой требуется обеспечить определенное состояние. |
|---|---|
|UserName |Указывает, в каком расположении нужно проверить состояние файла или каталога. |
|FullName |Строка, содержащая полное имя учетной записи пользователя. |
|Description |Описание учетной записи пользователя. |
|Пароль |Хэш пароля пользователя в соответствующей форме для компьютера с Linux. Обычно это защищенный хэш SHA-256 или SHA-512. В Debian и Ubuntu Linux это значение можно создать с помощью команды `mkpasswd`. В других дистрибутивах Linux для создания хеша можно использовать метод шифрования криптографической библиотеки Python. |
|Выключено |Указывает, включено ли правило. Присвойте этому свойству значение `$true`, чтобы отключить учетную запись, и `$false`, чтобы включить ее. |
|PasswordChangeRequired |Указывает, может ли пользователь изменить пароль. Присвойте этому свойству значение `$true`, чтобы пользователь не мог изменить пароль, и `$false`, чтобы мог. Значение по умолчанию — `$false`. Это свойство применяется только в том случае, если учетная запись пользователя ранее не существовала и находится в процессе создания. |
|HomeDirectory |Домашний каталог пользователя. |
|GroupID |ИД основной группы пользователя. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли учетная запись. Присвойте этому свойству значение **Present**, чтобы гарантировать, что учетная запись существует, и **Absent** в противном случае. |

## <a name="example"></a>Пример

В следующем примере проверяется, что пользователь monuser существует и является членом группы DBusers.

```powershell
Import-DSCResource -Module nx

Node $node
{
   nxUser UserExample{
      UserName = "monuser"
      Description = "Monitoring user"
      Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
      Ensure = "Present"
      HomeDirectory = "/home/monuser"
   }

   nxGroup GroupExample{
      GroupName = "DBusers"
      Ensure = "Present"
      MembersToInclude = "monuser"
      DependsOn = "[nxUser]UserExample"
   }
}
```
