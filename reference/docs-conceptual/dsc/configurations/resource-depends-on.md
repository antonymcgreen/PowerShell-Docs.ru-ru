---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование зависимостей ресурсов с DependsOn
description: По мере роста вашей конфигурации можно использовать ключ `DependsOn`, чтобы изменить порядок применения ресурсов, указав, что ресурс зависит от другого ресурса.
ms.openlocfilehash: 18f19a3606834ede0737213930e6af0e251225ab
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645105"
---
# <a name="resource-dependencies-using-dependson"></a><span data-ttu-id="b15a6-104">Использование зависимостей ресурсов с DependsOn</span><span class="sxs-lookup"><span data-stu-id="b15a6-104">Resource dependencies using DependsOn</span></span>

<span data-ttu-id="b15a6-105">При написании [конфигураций](configurations.md) добавляйте [блоки ресурсов](../resources/resources.md) для настройки аспектов целевого узла.</span><span class="sxs-lookup"><span data-stu-id="b15a6-105">When you write [Configurations](configurations.md), you add [Resource blocks](../resources/resources.md) to configure aspects of a target Node.</span></span> <span data-ttu-id="b15a6-106">По мере добавления блоков ресурсов конфигурация может стать довольно большой и сложной для управления.</span><span class="sxs-lookup"><span data-stu-id="b15a6-106">As you continue to add Resource blocks, your Configurations can grow quite large and cumbersome to manage.</span></span> <span data-ttu-id="b15a6-107">Одной из проблем является порядок применения ваших блоков ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b15a6-107">One such challenge is the applied order of your resource blocks.</span></span> <span data-ttu-id="b15a6-108">Обычно ресурсы применяются в порядке, в котором они определены в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b15a6-108">Typically resources are applied in the order they are defined within the Configuration.</span></span> <span data-ttu-id="b15a6-109">По мере роста вашей конфигурации можно использовать ключ `DependsOn`, чтобы изменить порядок применения ресурсов, указав, что ресурс зависит от другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="b15a6-109">As your Configuration grows larger and more complex, you can use the `DependsOn` key to change the applied order of your resources by specifying that a resource depends on another resource.</span></span>

<span data-ttu-id="b15a6-110">Ключ `DependsOn` может использоваться в любом блоке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b15a6-110">The `DependsOn` key can be used in any Resource block.</span></span> <span data-ttu-id="b15a6-111">Он определяется с помощью того же механизма "ключ-значение", что и другие ключи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b15a6-111">It is defined with the same key/value mechanism as other Resource keys.</span></span> <span data-ttu-id="b15a6-112">Ключ `DependsOn` ожидает массив строк со следующим синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="b15a6-112">The `DependsOn` key expects an array of strings with the following syntax.</span></span>

```
DependsOn = '[<Resource Type>]<Resource Name>', '[<Resource Type>]<Resource Name'
```

<span data-ttu-id="b15a6-113">В следующем примере настраивается правило брандмауэра после включения и настройки открытого профиля.</span><span class="sxs-lookup"><span data-stu-id="b15a6-113">The following example configures a firewall rule after enabling and configuring the public profile.</span></span>

```powershell
# Install the NetworkingDSC module to configure firewall rules and profiles.
Install-Module -Name NetworkingDSC

Configuration ConfigureFirewall
{
    Import-DSCResource -Name Firewall, FirewallProfile
    Node localhost
    {
        Firewall Firewall
        {
            Name                  = 'IIS-WebServerRole-HTTP-In-TCP'
            Ensure                = 'Present'
            Enabled               = 'True'
            DependsOn             = '[FirewallProfile]FirewallProfilePublic'
        }

        FirewallProfile FirewallProfilePublic
        {
            Name = 'Public'
            Enabled = 'True'
            DefaultInboundAction = 'Block'
            DefaultOutboundAction = 'Allow'
            AllowInboundRules = 'True'
            AllowLocalFirewallRules = 'False'
            AllowLocalIPsecRules = 'False'
            NotifyOnListen = 'True'
            LogFileName = '%systemroot%\system32\LogFiles\Firewall\pfirewall.log'
            LogMaxSizeKilobytes = 16384
            LogAllowed = 'False'
            LogBlocked = 'True'
            LogIgnored = 'NotConfigured'
        }
    }
}

ConfigureFirewall -OutputPath C:\Temp\
```

<span data-ttu-id="b15a6-114">При применении конфигурации профиль брандмауэра будет всегда задаваться сначала, независимо от порядка определений в блоках ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b15a6-114">When you apply the Configuration, the firewall profile will always be configured first regardless of which order the Resource blocks are defined.</span></span> <span data-ttu-id="b15a6-115">Если вы применяете конфигурацию, сохраните существующие конфигурации на целевых узлах, чтобы иметь возможность вернуть их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b15a6-115">If you apply the Configuration, be sure to note your target Nodes existing Configuration so you can revert if desired.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -Path C:\Temp\ -ComputerName localhost

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-181338-0189125723-1543119021-1282804.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module C:\Program Files\WindowsPowerShell\Modules\NetworkingDsc\6.1.0.0\DscResources\MSFT_Firewall\MSFT_Firewall.psm1 in force mode.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module C:\Program Files\WindowsPowerShell\Modules\NetworkingDsc\6.1.0.0\DscResources\MSFT_FirewallProfile\MSFT_FirewallProfile.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Importing the module MSFT_FirewallProfile in force mode.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Testing Firewall Public Profile.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowInboundRules" is "NotConfigured" but should be "True". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowLocalFirewallRules" is "NotConfigured" but should be "False". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "AllowLocalIPsecRules" is "NotConfigured" but should be "False". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "DefaultOutboundAction" is "NotConfigured" but should be "Allow". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "LogBlocked" is "False" but should be "True". Change required.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Test-TargetResource: Firewall Public Profile "LogMaxSizeKilobytes" is "4096" but should be "16384". Change required.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[FirewallProfile]FirewallProfilePublic]  in 1.6890 seconds.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Importing the module MSFT_FirewallProfile in force mode.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile.
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowInboundRules to "AllowInboundRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowLocalFirewallRules to "AllowLocalFirewallRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter AllowLocalIPsecRules to "AllowLocalIPsecRules".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter DefaultOutboundAction to "DefaultOutboundAction".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter LogBlocked to "LogBlocked".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile parameter LogMaxSizeKilobytes to "LogMaxSizeKilobytes".
VERBOSE: [SERVER01]:                            [[FirewallProfile]FirewallProfilePublic] Set-TargetResource: Setting Firewall Public Profile updated.
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]  [[FirewallProfile]FirewallProfilePublic]  in 10.0360 seconds.
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[FirewallProfile]FirewallProfilePublic]
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Importing the module MSFT_Firewall in force mode.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Checking settings for firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Find firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Get-FirewallRule: No Firewall Rule found with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' does not exist.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Test-TargetResource: Check Firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' returning False.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Firewall]Firewall]  in 1.1780 seconds.
VERBOSE: [SERVER01]: LCM:  [ Start  Set      ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Importing the module MSFT_Firewall in force mode.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: Applying settings for firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: Find firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Get-FirewallRule: No Firewall Rule found with Name 'IIS-WebServerRole-HTTP-In-TCP'.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: We want the firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' to exist since Ensure is set to Present.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] Set-TargetResource: We want the firewall rule with Name 'IIS-WebServerRole-HTTP-In-TCP' to exist, but it does not.
VERBOSE: [SERVER01]:                            [[Firewall]Firewall] New-NetFirewallRule DisplayName: IIS-WebServerRole-HTTP-In-TCP
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]  [[Firewall]Firewall]  in 1.0850 seconds.
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Firewall]Firewall]
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]
VERBOSE: [SERVER01]: LCM:  [ End    Set      ]    in  15.2880 seconds.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 15.385 seconds
```

<span data-ttu-id="b15a6-116">Это также гарантирует, что если ресурс **FirewallProfile** по какой-либо причине терпит сбой, то блок **Firewall** не будет выполняться, хотя он был определен сначала.</span><span class="sxs-lookup"><span data-stu-id="b15a6-116">This also ensures that if the **FirewallProfile** resource fails for any reason, the **Firewall** block will not execute even though it was defined first.</span></span> <span data-ttu-id="b15a6-117">Ключ `DependsOn` позволяет более гибко группировать блоки ресурсов и гарантировать, что зависимости можно будет разрешить до выполнения ресурса.</span><span class="sxs-lookup"><span data-stu-id="b15a6-117">The `DependsOn` key allows more flexibility in grouping resource blocks and ensuring that dependencies are resolved before a Resource executes.</span></span>

<span data-ttu-id="b15a6-118">В более сложных конфигурациях можно также использовать [механизм межузловых зависимостей](crossNodeDependencies.md), обеспечивающий более широкие возможности управления (например, он позволяет настроить контроллер домена перед присоединением клиента к домену).</span><span class="sxs-lookup"><span data-stu-id="b15a6-118">In more advanced Configurations, you can also use [Cross Node Dependency](crossNodeDependencies.md) to allow even more granular control (For example, ensuring a domain controller is configured before joining a client to the domain).</span></span>

## <a name="cleaning-up"></a><span data-ttu-id="b15a6-119">Очистка</span><span class="sxs-lookup"><span data-stu-id="b15a6-119">Cleaning Up</span></span>

<span data-ttu-id="b15a6-120">Если вы применили приведенную выше конфигурацию, можно вернуть ключи в исходное состояние для отмены всех изменений.</span><span class="sxs-lookup"><span data-stu-id="b15a6-120">If you applied the Configuration above, you can reverse keys to undo any changes.</span></span> <span data-ttu-id="b15a6-121">В приведенном выше примере установка ключа **Enabled** равным false отключает правило брандмауэра и профиль.</span><span class="sxs-lookup"><span data-stu-id="b15a6-121">In the above example, setting the **Enabled** key to false will disable the firewall rule and profile.</span></span> <span data-ttu-id="b15a6-122">Следует изменить пример при необходимости в соответствии с предыдущим настроенным состоянием целевого узла.</span><span class="sxs-lookup"><span data-stu-id="b15a6-122">You should modify the example as needed to match your target Node's previous configured state.</span></span>

```powershell
        Firewall Firewall
        {
            Name                  = 'IIS-WebServerRole-HTTP-In-TCP'
            Enabled               = 'False'
            DependsOn             = '[FirewallProfile]FirewallProfilePublic'
        }

        FirewallProfile FirewallProfilePublic
        {
            Name = 'Public'
            Enabled = 'False'
        }
```

## <a name="see-also"></a><span data-ttu-id="b15a6-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b15a6-123">See also</span></span>

- [<span data-ttu-id="b15a6-124">Использование межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="b15a6-124">Use Cross Node Dependencies</span></span>](./crossNodeDependencies.md)
