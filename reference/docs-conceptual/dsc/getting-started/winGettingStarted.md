---
ms.date: 08/15/2019
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с Desired State Configuration (DSC) для Windows
ms.openlocfilehash: 2add2c936e60c0c9446bf4b398fbf7b4bd6407f7
ms.sourcegitcommit: 1b88c280dd0799f225242608f0cbdab485357633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75416163"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a>Начало работы с Desired State Configuration (DSC) для Windows

В этом разделе объясняется, как приступить к работе с Desired State Configuration (DSC) в PowerShell для Windows.
Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](../overview/overview.md).

## <a name="supported-windows-operation-system-versions"></a>Поддерживаемые версии операционной системы Windows

Поддерживаются следующие версии:

- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2;
- Windows Server 2012
- Windows Server 2008 R2 с пакетом обновления 1 (SP1)
- Windows 10
- Windows 8.1
- Windows 7

Номер SKU автономного продукта [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) не содержит реализацию Desired State Configuration, поэтому управлять им с помощью DSC PowerShell или настройки состояния службы автоматизации Azure невозможно.

## <a name="installing-dsc"></a>Установка DSC

Desired State Configuration в PowerShell входит в состав Windows и обновляется с помощью Windows Management Framework. Последняя версия — [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).

> [!NOTE]
> Для управления компьютером с помощью DSC не нужно включать компонент Windows Server "DSC-Service".
> Этот компонент необходим только при создании экземпляра опрашиваемого сервера Windows.

## <a name="using-dsc-for-windows"></a>Использование DSC для Windows

В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Windows.

### <a name="creating-a-configuration-mof-document"></a>Создание MOF-документа конфигурации

Для создания конфигурации используется ключевое слово Windows PowerShell (`Configuration`).
В инструкциях ниже описывается создание документа конфигурации с использованием Windows PowerShell.

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a>Определите конфигурацию и создайте документ конфигурации:

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```

#### <a name="install-a-module-containing-dsc-resources"></a>Установка модуля, содержащего ресурсы DSC

Desired State Configuration в Windows PowerShell включает встроенные модули, содержащие ресурсы DSC.
Модули также можно загружать из внешних источников, таких как коллекция PowerShell, с помощью командлетов PowerShellGet.

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a>Применение конфигурации к компьютеру

> [!NOTE]
> Чтобы разрешить выполнение DSC, Windows необходимо настроить для получения удаленных команд PowerShell, даже когда вы запускаете конфигурацию `localhost`. Чтобы правильно настроить среду, запустите `Set-WsManQuickConfig -Force` в терминале PowerShell с повышенными привилегиями.

Документы конфигурации (MOF-файлы) можно применить к компьютеру с помощью командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a>Получение данных о текущем состоянии конфигурации

Командлет [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) запрашивает текущее состояние компьютера и возвращает текущие значения для конфигурации.

```powershell
Get-DscConfiguration
```

Командлет [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) возвращает текущую метаконфигурацию, примененную к компьютеру.

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a>Удаление текущей конфигурации с компьютера

Командлет [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument).

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a>Настройка параметров в локальном диспетчере конфигураций

Примените MOF-файл метаконфигурации к компьютеру с помощью командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).
При этом потребуется указать путь к соответствующему MOF-файлу метаконфигурации.

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a>Файлы журнала Desired State Configuration в Windows PowerShell

Журналы DSC записываются в журнал событий Windows по пути `Microsoft-Windows-Dsc/Operational`.
Дополнительные журналы для отладки можно включить, выполнив действия, описанные в разделе [Где находятся журналы событий DSC?](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)
