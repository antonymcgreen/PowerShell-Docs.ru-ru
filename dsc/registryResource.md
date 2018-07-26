---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Registry в DSC
ms.openlocfilehash: b77710d7a6fc599949e78c17af309ad88a1a0872
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093591"
---
# <a name="dsc-registry-resource"></a>Ресурс Registry в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс **Registry** в DSC Windows PowerShell предоставляет механизм управления разделами и значениями реестра на целевом узле.

## <a name="syntax"></a>Синтаксис

```
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Ensure = [string] { Present | Absent }  ]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ DependsOn = [string[]] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Клавиши| Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние. Этот путь должен включать куст.|
| ValueName| Указывает имя значения реестра. Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая ValueType или ValueData. Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав ValueType или ValueData.|
| Ensure| Указывает, существует ли ключ и значение. Для этого укажите для этого свойства значение Present. Чтобы они не существовали, укажите для этого свойства значение Absent. Значение по умолчанию — Present.|
| Force| Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением. При удалении раздела реестра с подразделами необходимо выбрать **$true** |
| Hex| Указывает, будут ли данные выражены в шестнадцатеричном формате. Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате. Недопустимо для других типов. Значение по умолчанию — **$false**.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|
| ValueData| Данные для значения реестра.|
| ValueType| Указывает тип значения. Поддерживаемые типы параметров: строковый (REG_SZ), двоичный (REG-BINARY), Dword — 32-битный (REG_DWORD), Qword — 64-битный (REG_QWORD), многостроковый (REG_MULTI_SZ), расширяемый строковый (REG_EXPAND_SZ). |

## <a name="example"></a>Пример

В этом примере гарантируется, что ключ с именем ExampleKey присутствует в кусте **HKEY\_LOCAL\_MACHINE**.

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> Для изменения настройки реестра в кусте **HKEY\_CURRENT\_USER** требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных. Вы можете использовать свойство **PsDscRunAsCredential**, чтобы указать учетные данные пользователя для конфигурации. Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](runAsUser.md).