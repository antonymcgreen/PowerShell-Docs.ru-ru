---
ms.date: 03/15/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование DSC в Microsoft Azure
ms.openlocfilehash: 6d71b69eea78e775a3e5aaac64bccfa10092b8e6
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "75870835"
---
# <a name="using-dsc-on-microsoft-azure"></a><span data-ttu-id="f2c2c-103">Использование DSC в Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-103">Using DSC on Microsoft Azure</span></span>

<span data-ttu-id="f2c2c-104">Настройка требуемого состояния (DSC) поддерживается в Microsoft Azure при помощи [обработчика расширений настройки требуемого состояния Azure](/azure/virtual-machines/extensions/dsc-overview) и [DSC в службе автоматизации Azure](/azure/automation/automation-dsc-overview).</span><span class="sxs-lookup"><span data-stu-id="f2c2c-104">Desired State Configuration (DSC) is supported in Microsoft Azure through the [Azure Desired State Configuration extension handler](/azure/virtual-machines/extensions/dsc-overview) and through [Azure Automation DSC](/azure/automation/automation-dsc-overview).</span></span>

## <a name="azure-desired-state-configuration-extension-handler"></a><span data-ttu-id="f2c2c-105">Обработчик расширения настройки требуемого состояния Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-105">Azure Desired State Configuration extension handler</span></span>

<span data-ttu-id="f2c2c-106">Расширение Azure DSC позволяет управлять виртуальными машинами, размещенным в Microsoft Azure, при помощи DSC.</span><span class="sxs-lookup"><span data-stu-id="f2c2c-106">The Azure DSC extension allows VMs hosted in Microsoft Azure to be managed with DSC.</span></span> <span data-ttu-id="f2c2c-107">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f2c2c-107">For more information, see the following topics:</span></span>

- [<span data-ttu-id="f2c2c-108">Обработчик расширения настройки требуемого состояния Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-108">Azure Desired State Configuration extension handler</span></span>](/azure/virtual-machines/extensions/dsc-overview)
- [<span data-ttu-id="f2c2c-109">Windows VMSS и настройка требуемого состояния при помощи шаблонов Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="f2c2c-109">Windows VMSS and Desired State Configuration with Azure Resource Manager templates</span></span>](/azure/virtual-machines/extensions/dsc-template)
- [<span data-ttu-id="f2c2c-110">Передача учетных данных в обработчик расширения настройки требуемого состояния Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-110">Passing credentials to the Azure DSC extension handler</span></span>](/azure/virtual-machines/extensions/dsc-credentials)
- [<span data-ttu-id="f2c2c-111">Журнал расширения Azure Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="f2c2c-111">Azure Desired State Configuration extension history</span></span>](azureDscexthistory.md)

## <a name="azure-automation-dsc"></a><span data-ttu-id="f2c2c-112">DSC службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-112">Azure Automation DSC</span></span>

<span data-ttu-id="f2c2c-113">[Служба автоматизации Azure](https://azure.microsoft.com/services/automation/) позволяет управлять конфигурациями DSC, ресурсами и управляемыми узлами из Azure.</span><span class="sxs-lookup"><span data-stu-id="f2c2c-113">The [Azure Automation service](https://azure.microsoft.com/services/automation/) allows you to manage DSC configurations, resources, and managed nodes from within Azure.</span></span> <span data-ttu-id="f2c2c-114">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f2c2c-114">For more information, see the following topics:</span></span>

- [<span data-ttu-id="f2c2c-115">DSC в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-115">Azure Automation DSC</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="f2c2c-116">Начало работы с DSC в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-116">Getting started with Azure Automation DSC</span></span>](/azure/automation/automation-dsc-getting-started)
- [<span data-ttu-id="f2c2c-117">Подключение компьютеров для управления при помощи DSC в службе автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="f2c2c-117">Onboarding machines for management by Azure Automation DSC</span></span>](/azure/automation/automation-dsc-onboarding)