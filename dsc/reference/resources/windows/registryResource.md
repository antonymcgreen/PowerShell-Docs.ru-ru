---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Registry в DSC
ms.openlocfilehash: e0ae1a4a27edc08c4e6ccd47786426917eb1ccb4
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047724"
---
# <a name="dsc-registry-resource"></a>Ресурс Registry в DSC

Применяется к: Windows PowerShell 4.0, Windows PowerShell 5.0_

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

| Свойство | Описание |
| --- | --- |
| Клавиши| Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние. Этот путь должен включать куст.|
| ValueName| Указывает имя значения реестра. Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая ValueType или ValueData. Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав ValueType или ValueData.|
| Ensure| Указывает, существует ли ключ и значение. Для этого укажите для этого свойства значение Present. Чтобы они не существовали, укажите для этого свойства значение Absent. Значение по умолчанию — Present.|
| Force| Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением. При удалении раздела реестра с подразделами необходимо выбрать **$true** |
| Hex| Указывает, будут ли данные выражены в шестнадцатеричном формате. Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате. Недопустимо для других типов. Значение по умолчанию — **$false**.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|
| ValueData| Данные для значения реестра.|
| ValueType| Указывает тип значения. Поддерживаемые типы: Строка (REG_SZ), двоичный файл (REG-BINARY), Dword 32-разрядный (REG_DWORD), Qword 64-разрядный (REG_QWORD), несколько строк (REG_MULTI_SZ), Расширяемая строка (REG_EXPAND_SZ) |

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
> Для изменения настройки реестра в кусте `HKEY\CURRENT\USER` требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных. Вы можете использовать свойство **PsDscRunAsCredential**, чтобы указать учетные данные пользователя для конфигурации. Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](../../../configurations/runAsUser.md).
