---
ms.date: 06/12/2017
title: Запрос на принятие условий лицензии
description: Как просмотреть лицензию пакета на странице сведений об элементах
ms.openlocfilehash: 0d8a9ed671f7993726bc3fa41d11159b366e5a28
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662302"
---
# <a name="require-license-acceptance"></a><span data-ttu-id="46353-103">Запрос на принятие условий лицензии</span><span class="sxs-lookup"><span data-stu-id="46353-103">Require license acceptance</span></span>

<span data-ttu-id="46353-104">На странице сведений об элементах модулей, для использования которых требуется принять условия лицензии, отображается соответствующий текст.</span><span class="sxs-lookup"><span data-stu-id="46353-104">Require License Acceptance text shows up on item details page for modules that require license acceptance.</span></span> <span data-ttu-id="46353-105">Лицензию для модуля можно просмотреть, щелкнув ссылку **View License.txt**.</span><span class="sxs-lookup"><span data-stu-id="46353-105">License for module can be viewed by clicking on **View License.txt** link.</span></span>

![Запрос на принятие условий лицензии](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

<span data-ttu-id="46353-107">При установке, сохранении и обновлении модуля с помощью PowerShellGet или при развертывании в службе автоматизации Azure пользователям будет предложено принять условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="46353-107">Users will be prompted to accept the license when installing, saving or updating the module through PowerShellGet or when deploying to Azure Automation.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="46353-108">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="46353-108">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="46353-109">Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии.</span><span class="sxs-lookup"><span data-stu-id="46353-109">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="46353-110">Нажав кнопку "ОК", вы принимаете условия лицензии".</span><span class="sxs-lookup"><span data-stu-id="46353-110">By clicking OK, you are accepting license terms.'</span></span>

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="46353-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="46353-112">More details</span></span>

<span data-ttu-id="46353-113">[Запрос на принятие условий лицензии в PowerShellGet](../../concepts/module-license-acceptance.md)
[Веб-сайт службы автоматизации Azure](/azure/automation)</span><span class="sxs-lookup"><span data-stu-id="46353-113">[Require License Acceptance in PowerShellGet](../../concepts/module-license-acceptance.md)
[Azure Automation website](/azure/automation)</span></span>
