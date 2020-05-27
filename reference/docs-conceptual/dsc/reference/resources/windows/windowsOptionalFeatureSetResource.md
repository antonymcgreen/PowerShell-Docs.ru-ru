---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeatureSet
ms.openlocfilehash: 0930bd0c6d1955005ea607b610e004818c0ad06f
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560157"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a>Ресурс DSC WindowsOptionalFeatureSet

> Область применения: Windows PowerShell 5.x

Ресурс **WindowsOptionalFeatureSet** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле. Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс WindowsOptionalFeature](windowsOptionalFeatureResource.md) для каждого компонента, указанного в свойстве **Name**.

Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких дополнительных компонентов Windows.

## <a name="syntax"></a>Синтаксис

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имена компонентов, которые необходимо включить или отключить. |
|Источник |Не реализовано. |
|NoWindowsUpdateCheck |Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонентов. Если задано значение `$true`, система DISM не обращается к Центру обновления Windows. |
|RemoveFilesOnDisable |Задайте значение `$true`, чтобы удалить все файлы, связанные с компонентами, когда свойству **Ensure** присваивается значение **Absent**. |
|LogLevel |Максимальный уровень результатов, показываемый в журналах. Допустимые значения: **ErrorsOnly**, **ErrorsAndWarning** и **ErrorsAndWarningAndInformation**. |
|LogPath |Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, включены ли компоненты. Чтобы гарантировать, что компоненты включены, присвойте этому свойству значение **Enable**. Чтобы гарантировать, что компоненты отключены, присвойте этому свойству значение **Disable**. По умолчанию используется значение **Enable**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).
