---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Registry в DSC
ms.openlocfilehash: 3acd79fa81bc731f344d810371b961dc3af3a11d
ms.sourcegitcommit: 1ab59991c18e1b9692333d5e58ce649eaa75594f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84203653"
---
# <a name="dsc-registry-resource"></a>Ресурс Registry в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **Registry** в DSC Windows PowerShell предоставляет механизм управления разделами и значениями реестра на целевом узле.

## <a name="syntax"></a>Синтаксис

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Клавиши |Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние. Этот путь должен включать куст. |
|ValueName |Указывает имя значения реестра. Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая **ValueType** или **ValueData**. Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав **ValueType** или **ValueData**. |
|Force |Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением. При удалении раздела реестра с подразделами необходимо выбрать `$true`. |
|Hex |Указывает, будут ли данные выражены в шестнадцатеричном формате. Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате. Недопустимо для других типов. Значение по умолчанию — `$false`. |
|ValueData |Данные для значения реестра. |
|ValueType |Указывает тип значения. Поддерживаемые типы: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-разрядный REG_DWORD), **Qword** (64-разрядный REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ). |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли ключ и значение. Чтобы гарантировать их существование, укажите для этого свойства значение **Present**. Чтобы они не существовали, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="examples"></a>Примеры

### <a name="example-1-ensure-specified-value-and-data-under-specified-registry-key"></a>Пример 1: Проверка того, что текущие значение и данные указаны в соответствующем разделе реестра

В этом примере значение реестра TestValue в разделе с именем ExampleKey1 содержится в кусте `HKEY\_LOCAL\_MACHINE` и содержит данные TestData.

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey1"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

### <a name="example-2-ensure-specified-registry-key-exists"></a>Пример 2. Проверка того, что указанный раздел реестра существует

В этом примере ключ с именем ExampleKey2 содержится в кусте **HKEY\_LOCAL\_MACHINE**.

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey2"
        ValueName   = ""
    }
}
```

> [!NOTE]
> Для изменения настройки реестра в кусте `HKEY_CURRENT_USER` требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных. Вы можете использовать свойство **PsDscRunAsCredential**, чтобы указать учетные данные пользователя для конфигурации. Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](../../../configurations/runAsUser.md).
