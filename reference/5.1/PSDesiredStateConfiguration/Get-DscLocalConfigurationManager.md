---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228322"
---
# <span data-ttu-id="0d57b-103">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0d57b-103">Get-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="0d57b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0d57b-104">SYNOPSIS</span></span>

<span data-ttu-id="0d57b-105">Возвращает параметры и состояния локального Configuration Manager (LCM) для узла.</span><span class="sxs-lookup"><span data-stu-id="0d57b-105">Gets Local Configuration Manager (LCM) settings and states for the node.</span></span>

## <span data-ttu-id="0d57b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d57b-106">SYNTAX</span></span>

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="0d57b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d57b-107">DESCRIPTION</span></span>

<span data-ttu-id="0d57b-108">`Get-DscLocalConfigurationManager`Командлет возвращает параметры LCM, мета-конфигурацию и состояния LCM для узла.</span><span class="sxs-lookup"><span data-stu-id="0d57b-108">The `Get-DscLocalConfigurationManager` cmdlet gets LCM settings, or meta-configuration, and the states of LCM for the node.</span></span> <span data-ttu-id="0d57b-109">Укажите компьютеры, используя сеансы модели CIM.</span><span class="sxs-lookup"><span data-stu-id="0d57b-109">Specify computers by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="0d57b-110">Если целевой компьютер не указан, командлет возвращает параметры конфигураций с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="0d57b-110">If you do not specify a target computer, the cmdlet gets the configuration settings from the local computer.</span></span>

## <span data-ttu-id="0d57b-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="0d57b-111">EXAMPLES</span></span>

### <span data-ttu-id="0d57b-112">Пример 1. получение параметров LCM для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="0d57b-112">Example 1: Get LCM settings for the local computer</span></span>

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

<span data-ttu-id="0d57b-113">Эта команда возвращает параметры LCM для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="0d57b-113">This command gets LCM settings for the local computer.</span></span>

<span data-ttu-id="0d57b-114">Дополнительные сведения об индивидуальных атрибутах выходных данных см. в разделе [Настройка локальной](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) документации по Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0d57b-114">For more information on the individual attributes of the output, see the [Configuring the Local Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) documentation.</span></span>

### <span data-ttu-id="0d57b-115">Пример 2. получение параметров LCM для указанного компьютера</span><span class="sxs-lookup"><span data-stu-id="0d57b-115">Example 2: Get LCM settings for a specified computer</span></span>

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

<span data-ttu-id="0d57b-116">Этот пример возвращает параметры LCM для компьютера, указанного в сеансе CIM.</span><span class="sxs-lookup"><span data-stu-id="0d57b-116">This example gets LCM settings for a computer specified by a CIM session.</span></span>
<span data-ttu-id="0d57b-117">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="0d57b-117">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="0d57b-118">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="0d57b-118">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0d57b-119">Первая команда создает сеанс CIM с помощью `New-CimSession` командлета, а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="0d57b-119">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span> <span data-ttu-id="0d57b-120">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="0d57b-120">The command prompts you for a password.</span></span> <span data-ttu-id="0d57b-121">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="0d57b-121">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="0d57b-122">Вторая команда получает локальные параметры Configuration Manager для компьютеров, идентифицируемых объектами **CimSession** , хранящимися в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="0d57b-122">The second command gets Local Configuration Manager settings for the computers identified by the **CimSession** objects stored in the $Session variable.</span></span> <span data-ttu-id="0d57b-123">В данном случае это компьютер с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="0d57b-123">In this case, the computer named Server01.</span></span>

## <span data-ttu-id="0d57b-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d57b-124">PARAMETERS</span></span>

### <span data-ttu-id="0d57b-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="0d57b-125">-AsJob</span></span>

<span data-ttu-id="0d57b-126">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="0d57b-126">Indicates that this cmdlet runs the command as a background job.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d57b-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d57b-127">-CimSession</span></span>

<span data-ttu-id="0d57b-128">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d57b-128">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="0d57b-129">Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или.</span><span class="sxs-lookup"><span data-stu-id="0d57b-129">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d57b-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0d57b-130">-ThrottleLimit</span></span>

<span data-ttu-id="0d57b-131">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="0d57b-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d57b-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0d57b-132">CommonParameters</span></span>

<span data-ttu-id="0d57b-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d57b-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d57b-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d57b-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d57b-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0d57b-135">INPUTS</span></span>

## <span data-ttu-id="0d57b-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0d57b-136">OUTPUTS</span></span>

## <span data-ttu-id="0d57b-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0d57b-137">NOTES</span></span>

## <span data-ttu-id="0d57b-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0d57b-138">RELATED LINKS</span></span>

[<span data-ttu-id="0d57b-139">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0d57b-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="0d57b-140">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0d57b-140">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)
