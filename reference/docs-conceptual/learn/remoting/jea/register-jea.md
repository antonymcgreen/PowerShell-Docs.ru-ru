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
# <a name="registering-jea-configurations"></a><span data-ttu-id="e7d9f-104">Регистрация конфигураций JEA</span><span class="sxs-lookup"><span data-stu-id="e7d9f-104">Registering JEA Configurations</span></span>

<span data-ttu-id="e7d9f-105">Последний шаг после создания [возможностей роли](role-capabilities.md) и [файла конфигурации сеанса](session-configurations.md) заключается в регистрации конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-105">Once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created, the last step is to register the JEA endpoint.</span></span> <span data-ttu-id="e7d9f-106">Регистрация конечной точки JEA в системе делает конечную точку доступной пользователям и модулям автоматизации.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-106">Registering the JEA endpoint with the system makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="e7d9f-107">Конфигурация для отдельного компьютера</span><span class="sxs-lookup"><span data-stu-id="e7d9f-107">Single machine configuration</span></span>

<span data-ttu-id="e7d9f-108">Для небольших сред можно развернуть JEA, зарегистрировав файл конфигурации сеанса с помощью командлета [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration).</span><span class="sxs-lookup"><span data-stu-id="e7d9f-108">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="e7d9f-109">Прежде чем приступать к этой процедуре, убедитесь, что выполняются следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="e7d9f-109">Before you begin, ensure that the following prerequisites have been met:</span></span>

- <span data-ttu-id="e7d9f-110">Созданы роли, которые помещены в папку **RoleCapabilities** для допустимого модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-110">One or more roles has been created and placed in the **RoleCapabilities** folder of a PowerShell module.</span></span>
- <span data-ttu-id="e7d9f-111">Создан и проверен файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-111">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="e7d9f-112">Пользователь, регистрирующий конфигурацию JEA, обладает правами администратора в соответствующих системах.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-112">The user registering the JEA configuration has administrator rights on the system.</span></span>
- <span data-ttu-id="e7d9f-113">Вы выбрали имя конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-113">You've selected a name for your JEA endpoint.</span></span>

<span data-ttu-id="e7d9f-114">Это имя запрашивается при подключении пользователей к системе с помощью JEA.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-114">The name of the JEA endpoint is required when users connect to the system using JEA.</span></span> <span data-ttu-id="e7d9f-115">Командлет [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) отображает имена конечных точек в системе.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-115">The [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet lists the names of the endpoints on a system.</span></span> <span data-ttu-id="e7d9f-116">Конечные точки, начинающиеся со слова `microsoft`, обычно поставляются с Windows.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-116">Endpoints that start with `microsoft` are typically shipped with Windows.</span></span> <span data-ttu-id="e7d9f-117">Конечная точка `microsoft.powershell` используется по умолчанию при подключении к удаленной конечной точке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-117">The `microsoft.powershell` endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

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

<span data-ttu-id="e7d9f-118">Выполните следующую команду, чтобы зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-118">Run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="e7d9f-119">Приведенная выше команда перезапускает службу WinRM в системе.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-119">The previous command restarts the WinRM service on the system.</span></span> <span data-ttu-id="e7d9f-120">При этом завершаются все сеансы удаленного взаимодействия PowerShell, а также любые текущие конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-120">This terminates all PowerShell remoting sessions and any ongoing DSC configurations.</span></span> <span data-ttu-id="e7d9f-121">Перед выполнением этой команды рекомендуется перевести рабочие компьютеры в автономный режим, чтобы избежать прерывания работы.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-121">We recommended you take production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="e7d9f-122">После регистрации вы будете готовы к [использованию JEA](using-jea.md).</span><span class="sxs-lookup"><span data-stu-id="e7d9f-122">After registration, you're ready to [use JEA](using-jea.md).</span></span> <span data-ttu-id="e7d9f-123">Файл конфигурации сеанса можно удалить в любое время.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-123">You may delete the session configuration file at any time.</span></span> <span data-ttu-id="e7d9f-124">Он не используется после регистрации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-124">The configuration file isn't used after registration of the endpoint.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="e7d9f-125">Конфигурация для нескольких компьютеров с помощью DSC</span><span class="sxs-lookup"><span data-stu-id="e7d9f-125">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="e7d9f-126">Если JEA развертывается на нескольких компьютерах, самая простая модель развертывания заключается в использовании ресурса [настройки требуемого состояния (DSC)](../../../dsc/overview/overview.md) JEA, позволяющего быстро и согласованно развернуть JEA на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-126">When deploying JEA on multiple machines, the simplest deployment model uses the JEA [Desired State Configuration (DSC)](../../../dsc/overview/overview.md) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="e7d9f-127">Чтобы развернуть JEA с помощью DSC, следует убедиться в выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-127">To deploy JEA with DSC, ensure the following prerequisites are met:</span></span>

- <span data-ttu-id="e7d9f-128">Созданы возможности ролей, которые были добавлены в допустимый модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-128">One or more role capabilities have been authored and added to a PowerShell module.</span></span>
- <span data-ttu-id="e7d9f-129">Модуль PowerShell, содержащий нужные роли, хранится в (доступной только для чтения) общей папке, видимой каждому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-129">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="e7d9f-130">Были определены параметры для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-130">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="e7d9f-131">При использовании ресурса DSC JEA создавать файл конфигурации сеанса не требуется.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-131">You don't need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="e7d9f-132">Вы имеете учетные данные, которые позволяют выполнять административные действия на каждом компьютере, или доступ к опрашивающему серверу DSC, используемому для управления компьютерами.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-132">You have credentials that allow administrative actions on each machine or access to the DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="e7d9f-133">Вы скачали [ресурс DSC JEA](https://github.com/powershell/JEA/tree/master/DSC%20Resource).</span><span class="sxs-lookup"><span data-stu-id="e7d9f-133">You've downloaded the [JEA DSC resource](https://github.com/powershell/JEA/tree/master/DSC%20Resource).</span></span>

<span data-ttu-id="e7d9f-134">На целевом компьютере или опрашивающем сервере создайте конфигурацию DSC для конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-134">Create a DSC configuration for your JEA endpoint on a target machine or pull server.</span></span> <span data-ttu-id="e7d9f-135">В этой конфигурации используйте ресурс DSC **JustEnoughAdministration** для настройки файла конфигурации сеанса и ресурс **File** для копирования возможностей ролей из общей папки.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-135">In this configuration, the **JustEnoughAdministration** DSC resource defines the session configuration file and the **File** resource copies the role capabilities from the file share.</span></span>

<span data-ttu-id="e7d9f-136">С помощью ресурса DSC можно настраивать следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="e7d9f-136">The following properties are configurable using the DSC resource:</span></span>

- <span data-ttu-id="e7d9f-137">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="e7d9f-137">Role Definitions</span></span>
- <span data-ttu-id="e7d9f-138">Группы виртуальных учетных записей</span><span class="sxs-lookup"><span data-stu-id="e7d9f-138">Virtual account groups</span></span>
- <span data-ttu-id="e7d9f-139">Имя групповой управляемой учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="e7d9f-139">Group-managed service account name</span></span>
- <span data-ttu-id="e7d9f-140">Каталог записей</span><span class="sxs-lookup"><span data-stu-id="e7d9f-140">Transcript directory</span></span>
- <span data-ttu-id="e7d9f-141">Диск пользователя</span><span class="sxs-lookup"><span data-stu-id="e7d9f-141">User drive</span></span>
- <span data-ttu-id="e7d9f-142">Правила условного доступа</span><span class="sxs-lookup"><span data-stu-id="e7d9f-142">Conditional access rules</span></span>
- <span data-ttu-id="e7d9f-143">Сценарии запуска для сеанса JEA</span><span class="sxs-lookup"><span data-stu-id="e7d9f-143">Startup scripts for the JEA session</span></span>

<span data-ttu-id="e7d9f-144">Синтаксис для каждого из этих свойств в конфигурации DSC согласуется с файлом конфигурации сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-144">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="e7d9f-145">Ниже приведен пример конфигурации DSC для модуля общего обслуживания сервера.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-145">Below is a sample DSC configuration for a general server maintenance module.</span></span> <span data-ttu-id="e7d9f-146">Предполагается, что допустимый модуль PowerShell, содержащий возможности ролей, находится в общей папке `\\myfileshare\JEA`.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-146">It assumes that a valid PowerShell module containing role capabilities is located on the `\\myfileshare\JEA` file share.</span></span>

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

<span data-ttu-id="e7d9f-147">Затем эту конфигурацию можно применить в системе, [напрямую вызвав локальный диспетчер конфигураций](/powershell/scripting/dsc/managing-nodes/metaConfig) или обновив [конфигурацию опрашивающего сервера](/powershell/scripting/dsc/pull-server/pullServer).</span><span class="sxs-lookup"><span data-stu-id="e7d9f-147">Next, the configuration is applied on a system by directly invoking the [Local Configuration Manager](/powershell/scripting/dsc/managing-nodes/metaConfig) or updating the [pull server configuration](/powershell/scripting/dsc/pull-server/pullServer).</span></span>

<span data-ttu-id="e7d9f-148">Ресурс DSC также позволяет заменить конечную точку удаленного взаимодействия по умолчанию **Microsoft.PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="e7d9f-148">The DSC resource also allows you to replace the default **Microsoft.PowerShell** endpoint.</span></span> <span data-ttu-id="e7d9f-149">При замене ресурс автоматически регистрирует резервную конечную точку с именем **Microsoft.PowerShell.Restricted** .</span><span class="sxs-lookup"><span data-stu-id="e7d9f-149">When replaced, the resource automatically registers a backup endpoint named **Microsoft.PowerShell.Restricted** .</span></span> <span data-ttu-id="e7d9f-150">Резервная конечная точка имеет ACL WinRM по умолчанию, который дает к ней доступ пользователям удаленного управления и локальным администраторам.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-150">The backup endpoint has the default WinRM ACL that allows Remote Management Users and local Administrators group members to access it.</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="e7d9f-151">Отмена регистрации конфигураций JEA</span><span class="sxs-lookup"><span data-stu-id="e7d9f-151">Unregistering JEA configurations</span></span>

<span data-ttu-id="e7d9f-152">Чтобы удалить конечную точку JEA, используйте командлет [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration).</span><span class="sxs-lookup"><span data-stu-id="e7d9f-152">The [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet removes a JEA endpoint.</span></span> <span data-ttu-id="e7d9f-153">Отмена регистрации конечной точки JEA не позволяет новым пользователям создавать новые сеансы JEA в системе.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-153">Unregistering a JEA endpoint prevents new users from creating new JEA sessions on the system.</span></span> <span data-ttu-id="e7d9f-154">Кроме того, вы можете обновить конфигурацию JEA, повторно зарегистрировав измененный файл конфигурации сеанса с использованием такого же имени конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-154">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="e7d9f-155">Отмена регистрации конечной точки JEA вызывает перезапуск службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-155">Unregistering a JEA endpoint causes the WinRM service to restart.</span></span> <span data-ttu-id="e7d9f-156">Это приводит к прерыванию большинства выполняемых операций удаленного управления, включая другие сеансы PowerShell, вызовы WMI и некоторые средства управления.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-156">This interrupts most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span> <span data-ttu-id="e7d9f-157">Отменяйте регистрацию конечных точек PowerShell только во время запланированных периодов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e7d9f-157">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7d9f-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e7d9f-158">Next steps</span></span>

[<span data-ttu-id="e7d9f-159">Тестирование конечной точки JEA</span><span class="sxs-lookup"><span data-stu-id="e7d9f-159">Test the JEA endpoint</span></span>](using-jea.md)
