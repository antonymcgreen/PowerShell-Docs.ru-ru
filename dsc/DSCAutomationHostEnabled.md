---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Раздел реестра DSCAutomationHostEnabled
ms.openlocfilehash: 0cecbadc6802938cadb4ffb9745a23e6b98544be
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
><span data-ttu-id="a2a25-103">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a2a25-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="a2a25-104">Раздел реестра DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="a2a25-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="a2a25-105">DSC использует раздел реестра **DSCAutomationHostEnabled** в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** для включения конфигурации компьютера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="a2a25-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="a2a25-106">DSCAutomationHostEnabled поддерживает три режима:</span><span class="sxs-lookup"><span data-stu-id="a2a25-106">DSCAutomationHostEnabled supports three modes:</span></span>

|  <span data-ttu-id="a2a25-107">Значение DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="a2a25-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="a2a25-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a2a25-108">Description</span></span>   |
|---|---|
<span data-ttu-id="a2a25-109">0</span><span class="sxs-lookup"><span data-stu-id="a2a25-109">0</span></span> | <span data-ttu-id="a2a25-110">Отключение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="a2a25-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="a2a25-111">1</span><span class="sxs-lookup"><span data-stu-id="a2a25-111">1</span></span> | <span data-ttu-id="a2a25-112">Включение настройки компьютера при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="a2a25-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="a2a25-113">2</span><span class="sxs-lookup"><span data-stu-id="a2a25-113">2</span></span> | <span data-ttu-id="a2a25-114">Включение настройки компьютера, только если DSC находится в состоянии ожидания или в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="a2a25-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="a2a25-115">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a2a25-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a2a25-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a2a25-116">See Also</span></span>

<span data-ttu-id="a2a25-117">Пример использования этой функции для запуска конфигураций при начальной загрузке системы см. в разделе [Настройка виртуальных машин при начальной загрузке с помощью DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="a2a25-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>