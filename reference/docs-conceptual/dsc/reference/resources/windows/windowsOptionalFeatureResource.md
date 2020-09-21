---
ms.date: 08/28/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093256"
---
# <a name="dsc-windowsoptionalfeature-resource"></a>Ресурс DSC WindowsOptionalFeature

> Область применения: Windows PowerShell 5.x

Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.

> [!NOTE]
> **WindowsOptionalFeature** работает только на клиентских компьютерах Windows, таких как Windows 10.

## <a name="syntax"></a>Синтаксис

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя компонента, который необходимо включить или отключить. |
|NoWindowsUpdateCheck |Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента. Если задано значение `$true`, система DISM не обращается к Центру обновления Windows. |
|RemoveFilesOnDisable |Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение **Absent**). |
|LogLevel |Максимальный уровень результатов, показываемый в журналах. Допустимые значения: **ErrorsOnly**, **ErrorsAndWarning** и **ErrorsAndWarningAndInformation**. |
|LogPath |Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, включена ли функция. Чтобы гарантировать, что эта функция включена, присвойте этому свойству значение _Enable_. Чтобы гарантировать, что эта функция отключена, присвойте этому свойству значение _Disable_. По умолчанию используется значение _Enable_. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).
