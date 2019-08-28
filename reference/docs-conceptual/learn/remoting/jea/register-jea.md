---
ms.date: 07/10/2019
keywords: jea,powershell,безопасность
title: Регистрация конфигураций JEA
ms.openlocfilehash: c85eddea2196e4db4bbeea54bde11074f3d1c927
ms.sourcegitcommit: e894ed833cef57967cdaf002f8c883f66864e836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2019
ms.locfileid: "70017715"
---
# <a name="registering-jea-configurations"></a><span data-ttu-id="8f44b-103">Регистрация конфигураций JEA</span><span class="sxs-lookup"><span data-stu-id="8f44b-103">Registering JEA Configurations</span></span>

<span data-ttu-id="8f44b-104">Последний шаг после создания [возможностей роли](role-capabilities.md) и [файла конфигурации сеанса](session-configurations.md) заключается в регистрации конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="8f44b-104">Once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created, the last step is to register the JEA endpoint.</span></span> <span data-ttu-id="8f44b-105">Регистрация конечной точки JEA в системе делает конечную точку доступной пользователям и модулям автоматизации.</span><span class="sxs-lookup"><span data-stu-id="8f44b-105">Registering the JEA endpoint with the system makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="8f44b-106">Конфигурация для отдельного компьютера</span><span class="sxs-lookup"><span data-stu-id="8f44b-106">Single machine configuration</span></span>

<span data-ttu-id="8f44b-107">Для небольших сред можно развернуть JEA, зарегистрировав файл конфигурации сеанса с помощью командлета [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration).</span><span class="sxs-lookup"><span data-stu-id="8f44b-107">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="8f44b-108">Прежде чем приступать к этой процедуре, убедитесь, что выполняются следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="8f44b-108">Before you begin, ensure that the following prerequisites have been met:</span></span>

- <span data-ttu-id="8f44b-109">Созданы роли, которые помещены в папку **RoleCapabilities** для допустимого модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f44b-109">One or more roles has been created and placed in the **RoleCapabilities** folder of a PowerShell module.</span></span>
- <span data-ttu-id="8f44b-110">Создан и проверен файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8f44b-110">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="8f44b-111">Пользователь, регистрирующий конфигурацию JEA, обладает правами администратора в соответствующих системах.</span><span class="sxs-lookup"><span data-stu-id="8f44b-111">The user registering the JEA configuration has administrator rights on the system.</span></span>
- <span data-ttu-id="8f44b-112">Вы выбрали имя конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="8f44b-112">You've selected a name for your JEA endpoint.</span></span>

<span data-ttu-id="8f44b-113">Это имя запрашивается при подключении пользователей к системе с помощью JEA.</span><span class="sxs-lookup"><span data-stu-id="8f44b-113">The name of the JEA endpoint is required when users connect to the system using JEA.</span></span> <span data-ttu-id="8f44b-114">Командлет [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) отображает имена конечных точек в системе.</span><span class="sxs-lookup"><span data-stu-id="8f44b-114">The [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet lists the names of the endpoints on a system.</span></span> <span data-ttu-id="8f44b-115">Конечные точки, начинающиеся со слова `microsoft`, обычно поставляются с Windows.</span><span class="sxs-lookup"><span data-stu-id="8f44b-115">Endpoints that start with `microsoft` are typically shipped with Windows.</span></span> <span data-ttu-id="8f44b-116">Конечная точка `microsoft.powershell` используется по умолчанию при подключении к удаленной конечной точке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f44b-116">The `microsoft.powershell` endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

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

<span data-ttu-id="8f44b-117">Выполните следующую команду, чтобы зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8f44b-117">Run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="8f44b-118">Приведенная выше команда перезапускает службу WinRM в системе.</span><span class="sxs-lookup"><span data-stu-id="8f44b-118">The previous command restarts the WinRM service on the system.</span></span> <span data-ttu-id="8f44b-119">При этом завершаются все сеансы удаленного взаимодействия PowerShell, а также любые текущие конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="8f44b-119">This terminates all PowerShell remoting sessions and any ongoing DSC configurations.</span></span> <span data-ttu-id="8f44b-120">Перед выполнением этой команды рекомендуется перевести рабочие компьютеры в автономный режим, чтобы избежать прерывания работы.</span><span class="sxs-lookup"><span data-stu-id="8f44b-120">We recommended you take production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="8f44b-121">После регистрации вы будете готовы к [использованию JEA](using-jea.md).</span><span class="sxs-lookup"><span data-stu-id="8f44b-121">After registration, you're ready to [use JEA](using-jea.md).</span></span> <span data-ttu-id="8f44b-122">Файл конфигурации сеанса можно удалить в любое время.</span><span class="sxs-lookup"><span data-stu-id="8f44b-122">You may delete the session configuration file at any time.</span></span> <span data-ttu-id="8f44b-123">Он не используется после регистрации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f44b-123">The configuration file isn't used after registration of the endpoint.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="8f44b-124">Конфигурация для нескольких компьютеров с помощью DSC</span><span class="sxs-lookup"><span data-stu-id="8f44b-124">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="8f44b-125">Если JEA развертывается на нескольких компьютерах, самая простая модель развертывания заключается в использовании ресурса [настройки требуемого состояния (DSC)](/powershell/dsc/overview) JEA, позволяющего быстро и согласованно развернуть JEA на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="8f44b-125">When deploying JEA on multiple machines, the simplest deployment model uses the JEA [Desired State Configuration (DSC)](/powershell/dsc/overview) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="8f44b-126">Чтобы развернуть JEA с помощью DSC, следует убедиться в выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="8f44b-126">To deploy JEA with DSC, ensure the following prerequisites are met:</span></span>

- <span data-ttu-id="8f44b-127">Созданы возможности ролей, которые были добавлены в допустимый модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f44b-127">One or more role capabilities have been authored and added to a PowerShell module.</span></span>
- <span data-ttu-id="8f44b-128">Модуль PowerShell, содержащий нужные роли, хранится в (доступной только для чтения) общей папке, видимой каждому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="8f44b-128">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="8f44b-129">Были определены параметры для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8f44b-129">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="8f44b-130">При использовании ресурса DSC JEA создавать файл конфигурации сеанса не требуется.</span><span class="sxs-lookup"><span data-stu-id="8f44b-130">You don't need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="8f44b-131">Вы имеете учетные данные, которые позволяют выполнять административные действия на каждом компьютере, или доступ к опрашивающему серверу DSC, используемому для управления компьютерами.</span><span class="sxs-lookup"><span data-stu-id="8f44b-131">You have credentials that allow administrative actions on each machine or access to the DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="8f44b-132">Вы скачали [ресурс DSC JEA](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource).</span><span class="sxs-lookup"><span data-stu-id="8f44b-132">You've downloaded the [JEA DSC resource](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource).</span></span>

<span data-ttu-id="8f44b-133">На целевом компьютере или опрашивающем сервере создайте конфигурацию DSC для конечной точки JEA.</span><span class="sxs-lookup"><span data-stu-id="8f44b-133">Create a DSC configuration for your JEA endpoint on a target machine or pull server.</span></span> <span data-ttu-id="8f44b-134">В этой конфигурации используйте ресурс DSC **JustEnoughAdministration** для настройки файла конфигурации сеанса и ресурс **File** для копирования возможностей ролей из общей папки.</span><span class="sxs-lookup"><span data-stu-id="8f44b-134">In this configuration, the **JustEnoughAdministration** DSC resource defines the session configuration file and the **File** resource copies the role capabilities from the file share.</span></span>

<span data-ttu-id="8f44b-135">С помощью ресурса DSC можно настраивать следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="8f44b-135">The following properties are configurable using the DSC resource:</span></span>

- <span data-ttu-id="8f44b-136">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="8f44b-136">Role Definitions</span></span>
- <span data-ttu-id="8f44b-137">Группы виртуальных учетных записей</span><span class="sxs-lookup"><span data-stu-id="8f44b-137">Virtual account groups</span></span>
- <span data-ttu-id="8f44b-138">Имя групповой управляемой учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="8f44b-138">Group-managed service account name</span></span>
- <span data-ttu-id="8f44b-139">Каталог записей</span><span class="sxs-lookup"><span data-stu-id="8f44b-139">Transcript directory</span></span>
- <span data-ttu-id="8f44b-140">Диск пользователя</span><span class="sxs-lookup"><span data-stu-id="8f44b-140">User drive</span></span>
- <span data-ttu-id="8f44b-141">Правила условного доступа</span><span class="sxs-lookup"><span data-stu-id="8f44b-141">Conditional access rules</span></span>
- <span data-ttu-id="8f44b-142">Сценарии запуска для сеанса JEA</span><span class="sxs-lookup"><span data-stu-id="8f44b-142">Startup scripts for the JEA session</span></span>

<span data-ttu-id="8f44b-143">Синтаксис для каждого из этих свойств в конфигурации DSC согласуется с файлом конфигурации сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f44b-143">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="8f44b-144">Ниже приведен пример конфигурации DSC для модуля общего обслуживания сервера.</span><span class="sxs-lookup"><span data-stu-id="8f44b-144">Below is a sample DSC configuration for a general server maintenance module.</span></span> <span data-ttu-id="8f44b-145">Предполагается, что допустимый модуль PowerShell, содержащий возможности ролей, находится в общей папке `\\myfileshare\JEA`.</span><span class="sxs-lookup"><span data-stu-id="8f44b-145">It assumes that a valid PowerShell module containing role capabilities is located on the `\\myfileshare\JEA` file share.</span></span>

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

<span data-ttu-id="8f44b-146">Затем эту конфигурацию можно применить в системе, [напрямую вызвав локальный диспетчер конфигураций](/powershell/dsc/managing-nodes/metaConfig) или обновив [конфигурацию опрашивающего сервера](/powershell/dsc/pull-server/pullServer).</span><span class="sxs-lookup"><span data-stu-id="8f44b-146">Next, the configuration is applied on a system by directly invoking the [Local Configuration Manager](/powershell/dsc/managing-nodes/metaConfig) or updating the [pull server configuration](/powershell/dsc/pull-server/pullServer).</span></span>

<span data-ttu-id="8f44b-147">Ресурс DSC также позволяет заменить конечную точку удаленного взаимодействия по умолчанию **Microsoft.PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8f44b-147">The DSC resource also allows you to replace the default **Microsoft.PowerShell** endpoint.</span></span> <span data-ttu-id="8f44b-148">При замене ресурс автоматически регистрирует резервную конечную точку с именем **Microsoft.PowerShell.Restricted**.</span><span class="sxs-lookup"><span data-stu-id="8f44b-148">When replaced, the resource automatically registers a backup endpoint named **Microsoft.PowerShell.Restricted**.</span></span> <span data-ttu-id="8f44b-149">Резервная конечная точка имеет ACL WinRM по умолчанию, который дает к ней доступ пользователям удаленного управления и локальным администраторам.</span><span class="sxs-lookup"><span data-stu-id="8f44b-149">The backup endpoint has the default WinRM ACL that allows Remote Management Users and local Administrators group members to access it.</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="8f44b-150">Отмена регистрации конфигураций JEA</span><span class="sxs-lookup"><span data-stu-id="8f44b-150">Unregistering JEA configurations</span></span>

<span data-ttu-id="8f44b-151">Чтобы удалить конечную точку JEA, используйте командлет [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8f44b-151">The [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet removes a JEA endpoint.</span></span> <span data-ttu-id="8f44b-152">Отмена регистрации конечной точки JEA не позволяет новым пользователям создавать новые сеансы JEA в системе.</span><span class="sxs-lookup"><span data-stu-id="8f44b-152">Unregistering a JEA endpoint prevents new users from creating new JEA sessions on the system.</span></span> <span data-ttu-id="8f44b-153">Кроме того, вы можете обновить конфигурацию JEA, повторно зарегистрировав измененный файл конфигурации сеанса с использованием такого же имени конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8f44b-153">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="8f44b-154">Отмена регистрации конечной точки JEA вызывает перезапуск службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="8f44b-154">Unregistering a JEA endpoint causes the WinRM service to restart.</span></span> <span data-ttu-id="8f44b-155">Это приводит к прерыванию большинства выполняемых операций удаленного управления, включая другие сеансы PowerShell, вызовы WMI и некоторые средства управления.</span><span class="sxs-lookup"><span data-stu-id="8f44b-155">This interrupts most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span> <span data-ttu-id="8f44b-156">Отменяйте регистрацию конечных точек PowerShell только во время запланированных периодов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="8f44b-156">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f44b-157">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8f44b-157">Next steps</span></span>

[<span data-ttu-id="8f44b-158">Тестирование конечной точки JEA</span><span class="sxs-lookup"><span data-stu-id="8f44b-158">Test the JEA endpoint</span></span>](using-jea.md)
