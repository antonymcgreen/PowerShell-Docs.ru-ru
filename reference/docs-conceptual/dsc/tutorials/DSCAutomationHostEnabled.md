---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Раздел реестра DSCAutomationHostEnabled
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954271"
---
><span data-ttu-id="f4c28-103">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f4c28-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="f4c28-104">Раздел реестра DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="f4c28-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="f4c28-105">DSC использует раздел реестра **DSCAutomationHostEnabled** в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** для включения конфигурации компьютера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="f4c28-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="f4c28-106">**DSCAutomationHostEnabled** поддерживает три режима:</span><span class="sxs-lookup"><span data-stu-id="f4c28-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="f4c28-107">Значение DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="f4c28-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="f4c28-108">Description</span><span class="sxs-lookup"><span data-stu-id="f4c28-108">Description</span></span>   |
|---|---|
<span data-ttu-id="f4c28-109">0</span><span class="sxs-lookup"><span data-stu-id="f4c28-109">0</span></span> | <span data-ttu-id="f4c28-110">Отключение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="f4c28-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="f4c28-111">1</span><span class="sxs-lookup"><span data-stu-id="f4c28-111">1</span></span> | <span data-ttu-id="f4c28-112">Включение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="f4c28-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="f4c28-113">2</span><span class="sxs-lookup"><span data-stu-id="f4c28-113">2</span></span> | <span data-ttu-id="f4c28-114">Включение настройки компьютера, только если DSC находится в состоянии ожидания или в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="f4c28-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="f4c28-115">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4c28-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f4c28-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4c28-116">See Also</span></span>

<span data-ttu-id="f4c28-117">Пример использования этой функции для запуска конфигураций при начальной загрузке системы см. в разделе [Настройка виртуальных машин при начальной загрузке с помощью DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="f4c28-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
