---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: cd3338ae305896e282056a871974e5f899ef6ff5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085267"
---
# <a name="reporting-on-jea"></a><span data-ttu-id="bf6ae-102">Отчеты о JEA</span><span class="sxs-lookup"><span data-stu-id="bf6ae-102">Reporting on JEA</span></span>

<span data-ttu-id="bf6ae-103">Чтобы отправить отчета о состоянии конфигурации JEA, можно использовать следующее.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-103">In order to report on the state of your JEA configuration, you can use:</span></span>

1. <span data-ttu-id="bf6ae-104">**Get-PSSessionConfiguration** для получения списка всех зарегистрированных конечных точек на заданном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-104">**Get-PSSessionConfiguration** to return a list of all registered endpoints on a given machine.</span></span>
2. <span data-ttu-id="bf6ae-105">**Get-PSSessionCapability** для получения отчета о возможности любого пользователя на заданной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-105">**Get-PSSessionCapability** to report on the capabilities any given user has on a specific endpoint.</span></span>

<span data-ttu-id="bf6ae-106">Ниже приведен пример использования **Get-PSSessionCapability**:</span><span class="sxs-lookup"><span data-stu-id="bf6ae-106">Here's an example of **Get-PSSessionCapability**:</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Maintenance -Username "CONTOSO\JohnDoe"

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           clear -> Clear-Host
Alias           cls -> Clear-Host
Alias           exsn -> Exit-PSSession
Alias           gcm -> Get-Command
Alias           measure -> Measure-Object
Alias           select -> Select-Object
Function        Clear-Host
Function        Exit-PSSession
Function        Get-Command
Function        Get-FormatData
Function        Get-Help
Function        Get-UserInfo
Function        Measure-Object
Function        Out-Default
Function        Select-Object
Cmdlet          Restart-Service                                    3.0.0.0 Microsof...
```

<span data-ttu-id="bf6ae-107">Чтобы отправить отчет о _действиях_, выполненных пользователем во время сеанса JEA, можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="bf6ae-107">To report on the _actions_ users took during a JEA session, you can:</span></span>

1. <span data-ttu-id="bf6ae-108">Включить записи с запросом на повышение прав для этой конечной точки JEA и обратиться к каталогу записей получения полного журнала действий каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-108">Enable the "over-the-shoulder" transcripts for that JEA endpoint and consult the transcript directory for a full log of each user's actions</span></span>
2. <span data-ttu-id="bf6ae-109">Включить ведение журнала модуля PowerShell и просмотреть журналы событий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf6ae-109">Turn on PowerShell module logging and inspect the PowerShell event logs.</span></span>