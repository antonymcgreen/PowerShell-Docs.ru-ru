---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Развертывание в службу автоматизации Azure
ms.openlocfilehash: dc382b1cf3ceaa787f54c555d01e6bd9ba70e680
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003891"
---
# <a name="deploy-to-azure-automation"></a><span data-ttu-id="c52b3-103">Развертывание в службу автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="c52b3-103">Deploy to Azure Automation</span></span>

<span data-ttu-id="c52b3-104">Кнопкой "Развернуть в службе автоматизации Azure" на странице сведений о пакете можно развернуть пакет из коллекции PowerShell в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="c52b3-104">The Deploy to Azure Automation button on the package details page will deploy the package from the PowerShell Gallery to Azure Automation.</span></span>

![Кнопка "Развернуть в службе автоматизации Azure"](../../Images/DeployToAzureAutomationButton.png)

<span data-ttu-id="c52b3-106">При нажатии этой кнопки вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="c52b3-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span>
<span data-ttu-id="c52b3-107">Если пакет имеет зависимости, все они будут также развернуты в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="c52b3-107">If the package includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

> [!WARNING]
> <span data-ttu-id="c52b3-108">Если в вашей учетной записи службы автоматизации уже существует такой пакет с той же версией, его повторное развертывание из коллекции PowerShell приведет к перезаписи существующего пакета в учетной записи службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="c52b3-108">If the same package and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the package in your Automation account.</span></span>

<span data-ttu-id="c52b3-109">При развертывании модуля он будет отображаться в разделе модулей службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="c52b3-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span>  <span data-ttu-id="c52b3-110">При развертывании скрипта он будет отображаться в разделе модулей Runbook службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="c52b3-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="c52b3-111">Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег AzureAutomationNotSupported в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="c52b3-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the package metadata.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="c52b3-112">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="c52b3-112">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="c52b3-113">Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии.</span><span class="sxs-lookup"><span data-stu-id="c52b3-113">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="c52b3-114">Нажав кнопку "ОК", вы принимаете условия лицензии".</span><span class="sxs-lookup"><span data-stu-id="c52b3-114">By clicking OK, you are accepting license terms.'</span></span>

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="c52b3-116">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="c52b3-116">More details</span></span>

- [<span data-ttu-id="c52b3-117">Запрос на принятие условий лицензии в PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c52b3-117">Require License Acceptance in PowerShellGet</span></span>](../../concepts/module-license-acceptance.md)
- [<span data-ttu-id="c52b3-118">Запрос на принятие условий лицензии в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="c52b3-118">Require License Acceptance in PowerShell Gallery</span></span>](packages-that-require-license-acceptance.md)
- [<span data-ttu-id="c52b3-119">Веб-сайт службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="c52b3-119">Azure Automation website</span></span>](http://azure.microsoft.com/services/automation/)
