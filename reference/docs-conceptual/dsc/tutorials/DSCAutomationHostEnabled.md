---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Раздел реестра DSCAutomationHostEnabled
description: В этой статье определены значения, которые можно задать в разделе реестра DSCAutomationHostEnabled.
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656178"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="d8c15-104">Раздел реестра DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="d8c15-104">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="d8c15-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d8c15-105">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="d8c15-106">DSC использует раздел реестра **DSCAutomationHostEnabled** в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** для включения конфигурации компьютера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="d8c15-106">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span> <span data-ttu-id="d8c15-107">**DSCAutomationHostEnabled** поддерживает три режима:</span><span class="sxs-lookup"><span data-stu-id="d8c15-107">**DSCAutomationHostEnabled** supports three modes:</span></span>

| <span data-ttu-id="d8c15-108">Значение DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="d8c15-108">DSCAutomationHostEnabled Value</span></span> |                                              <span data-ttu-id="d8c15-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8c15-109">Description</span></span>                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d8c15-110">0</span><span class="sxs-lookup"><span data-stu-id="d8c15-110">0</span></span>                              | <span data-ttu-id="d8c15-111">Отключение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="d8c15-111">Disable configuring the machine at boot-up.</span></span>                                                           |
| <span data-ttu-id="d8c15-112">1</span><span class="sxs-lookup"><span data-stu-id="d8c15-112">1</span></span>                              | <span data-ttu-id="d8c15-113">Включение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="d8c15-113">Enable configuring the machine at boot-up.</span></span>                                                            |
| <span data-ttu-id="d8c15-114">2</span><span class="sxs-lookup"><span data-stu-id="d8c15-114">2</span></span>                              | <span data-ttu-id="d8c15-115">Включение настройки компьютера, только если DSC находится в состоянии ожидания или в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="d8c15-115">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="d8c15-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8c15-116">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d8c15-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8c15-117">See Also</span></span>

<span data-ttu-id="d8c15-118">Пример использования этой функции для запуска конфигураций при начальной загрузке системы см. в разделе [Настройка виртуальных машин при начальной загрузке с помощью DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="d8c15-118">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
