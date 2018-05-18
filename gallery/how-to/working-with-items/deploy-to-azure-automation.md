---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery
title: Развертывание в службу автоматизации Azure
ms.openlocfilehash: 1efdc289228d3a6962302d12ccf44143ce63a806
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-to-azure-automation"></a><span data-ttu-id="5ec4d-103">Развертывание в службу автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="5ec4d-103">Deploy to Azure Automation</span></span>

<span data-ttu-id="5ec4d-104">Кнопкой "Развернуть в службе автоматизации Azure" на странице подробностей об элементе можно развернуть элемент из коллекции PowerShell в службу автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-104">The Deploy to Azure Automation button on the item details page will deploy the item from the PowerShell Gallery to Azure Automation.</span></span>

![Кнопка "Развернуть в службе автоматизации Azure"](../../Images/DeployToAzureAutomationButton.png)

<span data-ttu-id="5ec4d-106">При нажатии этой кнопки вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span>
<span data-ttu-id="5ec4d-107">Если элемент имеет зависимости, все они будут также развернуты в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-107">If the item includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

> [!WARNING]
> <span data-ttu-id="5ec4d-108">Если в вашей учетной записи службы автоматизации уже существует такой элемент с той же версией, его повторное развертывание из коллекции PowerShell приведет к перезаписи существующего элемента в учетной записи службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-108">If the same item and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the item in your Automation account.</span></span>

<span data-ttu-id="5ec4d-109">При развертывании модуля он будет отображаться в разделе модулей службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span>  <span data-ttu-id="5ec4d-110">При развертывании скрипта он будет отображаться в разделе модулей Runbook службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="5ec4d-111">Кнопку "Развернуть в службу автоматизации Azure" можно отключить, добавив тег AzureAutomationNotSupported в метаданные элемента.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the item metadata.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="5ec4d-112">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="5ec4d-112">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="5ec4d-113">Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии.</span><span class="sxs-lookup"><span data-stu-id="5ec4d-113">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="5ec4d-114">Нажав кнопку "ОК", вы принимаете условия лицензии".</span><span class="sxs-lookup"><span data-stu-id="5ec4d-114">By clicking OK, you are accepting license terms.'</span></span>

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="5ec4d-116">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="5ec4d-116">More details</span></span>

- [<span data-ttu-id="5ec4d-117">Запрос на принятие условий лицензии в PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5ec4d-117">Require License Acceptance in PowerShellGet</span></span>](../../concepts/module-license-acceptance.md)
- [<span data-ttu-id="5ec4d-118">Запрос на принятие условий лицензии в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ec4d-118">Require License Acceptance in PowerShell Gallery</span></span>](items-that-require-license-acceptance.md)
- [<span data-ttu-id="5ec4d-119">Веб-сайт службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="5ec4d-119">Azure Automation website</span></span>](http://azure.microsoft.com/services/automation/)
