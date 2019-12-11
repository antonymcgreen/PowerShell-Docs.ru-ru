---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Развертывание в службу автоматизации Azure
ms.openlocfilehash: 707691e24a77647064e60da0d9a31ad5eece1c59
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71327915"
---
# <a name="deploy-to-azure-automation"></a><span data-ttu-id="4f246-103">Развертывание в службу автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="4f246-103">Deploy to Azure Automation</span></span>

<span data-ttu-id="4f246-104">Кнопкой "Развернуть в службе автоматизации Azure" на странице сведений о пакете можно развернуть пакет из коллекции PowerShell в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="4f246-104">The Deploy to Azure Automation button on the package details page will deploy the package from the PowerShell Gallery to Azure Automation.</span></span>

![Кнопка "Развернуть в службе автоматизации Azure"](../../Images/DeployToAzureAutomationButton.png)

<span data-ttu-id="4f246-106">При нажатии этой кнопки вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="4f246-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span>
<span data-ttu-id="4f246-107">Если пакет имеет зависимости, все они будут также развернуты в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="4f246-107">If the package includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

> [!WARNING]
> <span data-ttu-id="4f246-108">Если в вашей учетной записи службы автоматизации уже существует такой пакет с той же версией, его повторное развертывание из коллекции PowerShell приведет к перезаписи существующего пакета в учетной записи службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="4f246-108">If the same package and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the package in your Automation account.</span></span>

<span data-ttu-id="4f246-109">При развертывании модуля он будет отображаться в разделе модулей службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="4f246-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span>  <span data-ttu-id="4f246-110">При развертывании скрипта он будет отображаться в разделе модулей Runbook службы автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="4f246-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="4f246-111">Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег AzureAutomationNotSupported в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="4f246-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the package metadata.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="4f246-112">Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="4f246-112">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="4f246-113">Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии.</span><span class="sxs-lookup"><span data-stu-id="4f246-113">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="4f246-114">Нажав кнопку "ОК", вы принимаете условия лицензии".</span><span class="sxs-lookup"><span data-stu-id="4f246-114">By clicking OK, you are accepting license terms.'</span></span>

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="4f246-116">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="4f246-116">More details</span></span>

- [<span data-ttu-id="4f246-117">Запрос на принятие условий лицензии в PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4f246-117">Require License Acceptance in PowerShellGet</span></span>](../../concepts/module-license-acceptance.md)
- [<span data-ttu-id="4f246-118">Запрос на принятие условий лицензии в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f246-118">Require License Acceptance in PowerShell Gallery</span></span>](packages-that-require-license-acceptance.md)
- [<span data-ttu-id="4f246-119">Веб-сайт службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="4f246-119">Azure Automation website</span></span>](https://azure.microsoft.com/services/automation/)
