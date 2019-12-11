---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента DSC
ms.openlocfilehash: 54c68ac26e5388260e252ce01418170e26ddecde
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71955171"
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="3e054-103">Настройка опрашивающего клиента DSC</span><span class="sxs-lookup"><span data-stu-id="3e054-103">Setting up a DSC pull client</span></span>

> <span data-ttu-id="3e054-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3e054-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e054-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="3e054-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="3e054-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="3e054-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="3e054-107">Для каждого целевого узла нужно включить опрашивающий режим и указать URL-адрес или расположение файла для подключения к опрашивающему серверу, чтобы получать конфигурации и ресурсы, а также отправлять данные отчетов.</span><span class="sxs-lookup"><span data-stu-id="3e054-107">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>

<span data-ttu-id="3e054-108">В следующих разделах показано, как настроить опрашивающие клиенты.</span><span class="sxs-lookup"><span data-stu-id="3e054-108">The following topics explain how to set up pull clients:</span></span>

* [<span data-ttu-id="3e054-109">Настройка опрашивающего клиента с помощью имени конфигурации</span><span class="sxs-lookup"><span data-stu-id="3e054-109">Setting up a pull client using configuration names</span></span>](pullClientConfigNames.md)
* [<span data-ttu-id="3e054-110">Настройка опрашивающего клиента с помощью идентификатора конфигурации</span><span class="sxs-lookup"><span data-stu-id="3e054-110">Setting up a pull client using configuration ID</span></span>](pullClientConfigID.md)

> [!NOTE]
> <span data-ttu-id="3e054-111">Эти разделы относятся к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="3e054-111">These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="3e054-112">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md).</span><span class="sxs-lookup"><span data-stu-id="3e054-112">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>