---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Регистрация конфигураций JEA
description: Регистрация конечной точки JEA в системе делает конечную точку доступной пользователям и модулям автоматизации.
ms.openlocfilehash: 6e7f8cdc1e7a666bddaa42034d70fcbcf55c1972
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499915"
---
# <a name="registering-jea-configurations"></a>Регистрация конфигураций JEA

Последний шаг после создания [возможностей роли](role-capabilities.md) и [файла конфигурации сеанса](session-configurations.md) заключается в регистрации конечной точки JEA. Регистрация конечной точки JEA в системе делает конечную точку доступной пользователям и модулям автоматизации.

## <a name="single-machine-configuration"></a>Конфигурация для отдельного компьютера

Для небольших сред можно развернуть JEA, зарегистрировав файл конфигурации сеанса с помощью командлета [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration).

Прежде чем приступать к этой процедуре, убедитесь, что выполняются следующие необходимые условия:

- Созданы роли, которые помещены в папку **RoleCapabilities** для допустимого модуля PowerShell.
- Создан и проверен файл конфигурации сеанса.
- Пользователь, регистрирующий конфигурацию JEA, обладает правами администратора в соответствующих системах.
- Вы выбрали имя конечной точки JEA.

Это имя запрашивается при подключении пользователей к системе с помощью JEA. Командлет [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) отображает имена конечных точек в системе. Конечные точки, начинающиеся со слова `microsoft`, обычно поставляются с Windows. Конечная точка `microsoft.powershell` используется по умолчанию при подключении к удаленной конечной точке PowerShell.

```powershell
Get-PSSessionConfiguration | Select-Object Name
```

```Output
Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

Выполните следующую команду, чтобы зарегистрировать конечную точку.

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> Приведенная выше команда перезапускает службу WinRM в системе. При этом завершаются все сеансы удаленного взаимодействия PowerShell, а также любые текущие конфигурации DSC. Перед выполнением этой команды рекомендуется перевести рабочие компьютеры в автономный режим, чтобы избежать прерывания работы.

После регистрации вы будете готовы к [использованию JEA](using-jea.md). Файл конфигурации сеанса можно удалить в любое время. Он не используется после регистрации конечной точки.

## <a name="multi-machine-configuration-with-dsc"></a>Конфигурация для нескольких компьютеров с помощью DSC

Если JEA развертывается на нескольких компьютерах, самая простая модель развертывания заключается в использовании ресурса [настройки требуемого состояния (DSC)](../../../dsc/overview/overview.md) JEA, позволяющего быстро и согласованно развернуть JEA на каждом компьютере.

Чтобы развернуть JEA с помощью DSC, следует убедиться в выполнении следующих условий.

- Созданы возможности ролей, которые были добавлены в допустимый модуль PowerShell.
- Модуль PowerShell, содержащий нужные роли, хранится в (доступной только для чтения) общей папке, видимой каждому компьютеру.
- Были определены параметры для конфигурации сеанса. При использовании ресурса DSC JEA создавать файл конфигурации сеанса не требуется.
- Вы имеете учетные данные, которые позволяют выполнять административные действия на каждом компьютере, или доступ к опрашивающему серверу DSC, используемому для управления компьютерами.
- Вы скачали [ресурс DSC JEA](https://github.com/powershell/JEA/tree/master/DSC%20Resource).

На целевом компьютере или опрашивающем сервере создайте конфигурацию DSC для конечной точки JEA. В этой конфигурации используйте ресурс DSC **JustEnoughAdministration** для настройки файла конфигурации сеанса и ресурс **File** для копирования возможностей ролей из общей папки.

С помощью ресурса DSC можно настраивать следующие свойства:

- Определения ролей
- Группы виртуальных учетных записей
- Имя групповой управляемой учетной записи службы
- Каталог записей
- Диск пользователя
- Правила условного доступа
- Сценарии запуска для сеанса JEA

Синтаксис для каждого из этих свойств в конфигурации DSC согласуется с файлом конфигурации сеанса PowerShell.

Ниже приведен пример конфигурации DSC для модуля общего обслуживания сервера. Предполагается, что допустимый модуль PowerShell, содержащий возможности ролей, находится в общей папке `\\myfileshare\JEA`.

```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

Затем эту конфигурацию можно применить в системе, [напрямую вызвав локальный диспетчер конфигураций](/powershell/scripting/dsc/managing-nodes/metaConfig) или обновив [конфигурацию опрашивающего сервера](/powershell/scripting/dsc/pull-server/pullServer).

Ресурс DSC также позволяет заменить конечную точку удаленного взаимодействия по умолчанию **Microsoft.PowerShell** . При замене ресурс автоматически регистрирует резервную конечную точку с именем **Microsoft.PowerShell.Restricted** . Резервная конечная точка имеет ACL WinRM по умолчанию, который дает к ней доступ пользователям удаленного управления и локальным администраторам.

## <a name="unregistering-jea-configurations"></a>Отмена регистрации конфигураций JEA

Чтобы удалить конечную точку JEA, используйте командлет [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration). Отмена регистрации конечной точки JEA не позволяет новым пользователям создавать новые сеансы JEA в системе. Кроме того, вы можете обновить конфигурацию JEA, повторно зарегистрировав измененный файл конфигурации сеанса с использованием такого же имени конечной точки.

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> Отмена регистрации конечной точки JEA вызывает перезапуск службы WinRM. Это приводит к прерыванию большинства выполняемых операций удаленного управления, включая другие сеансы PowerShell, вызовы WMI и некоторые средства управления. Отменяйте регистрацию конечных точек PowerShell только во время запланированных периодов обслуживания.

## <a name="next-steps"></a>Дальнейшие действия

[Тестирование конечной точки JEA](using-jea.md)
