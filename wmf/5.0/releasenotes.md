---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 07ebcfd37cc3e1f38a9434ffa8d86f479b89ee0f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085224"
---
# <a name="windows-management-framework-wmf-50-rtm-release-notes-overview"></a><span data-ttu-id="e6be3-102">Обзор заметок о выпуске Windows Management Framework (WMF) 5.0 RTM</span><span class="sxs-lookup"><span data-stu-id="e6be3-102">Windows Management Framework (WMF) 5.0 RTM Release Notes Overview</span></span>

<span data-ttu-id="e6be3-103">**WMF 5.0 заменяется выпуском WMF 5.1. Для получения поддержки пользователям WMF 5.0 необходимо выполнить обновление до WMF 5.1. Следуйте [инструкциям по установке WMF 5.1](../5.1/install-configure.md)**</span><span class="sxs-lookup"><span data-stu-id="e6be3-103">**WMF 5.0 is superseded by WMF 5.1. Users with WMF 5.0 must upgrade to WMF 5.1 to receive support. Please follow the [installation intructions of WMF 5.1](../5.1/install-configure.md)**</span></span>

<span data-ttu-id="e6be3-104">Windows Management Framework (WMF) 5.0 RTM предоставляет обновленные функциональные возможности версии 4.0.</span><span class="sxs-lookup"><span data-stu-id="e6be3-104">Windows Management Framework (WMF) 5.0 RTM brings functionality that has been updated from WMF 4.0.</span></span> <span data-ttu-id="e6be3-105">WMF 5.0 RTM можно установить только в **Windows Server 2012 R2**, **Windows Server 2012**, **Windows Server 2008 R2**, **Windows 8.1** и **Windows 7 с пакетом обновления 1 (SP1)** и содержит приведенные ниже новые или обновленные функции:</span><span class="sxs-lookup"><span data-stu-id="e6be3-105">WMF 5.0 RTM is available for installation only on **Windows Server 2012 R2**, **Windows Server 2012**, **Windows Server 2008 R2**, **Windows 8.1**, and **Windows 7 SP1** and contains updated versions or introduction of the following features:</span></span>

- <span data-ttu-id="e6be3-106">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6be3-106">Windows PowerShell</span></span>
- <span data-ttu-id="e6be3-107">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="e6be3-107">Just Enough Administration (JEA)</span></span>
- <span data-ttu-id="e6be3-108">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="e6be3-108">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="e6be3-109">Интегрированная среда сценариев (ISE) Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6be3-109">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>
- <span data-ttu-id="e6be3-110">Веб-службы Windows PowerShell (расширение IIS OData для управления)</span><span class="sxs-lookup"><span data-stu-id="e6be3-110">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="e6be3-111">Удаленное управление Windows (WinRM)</span><span class="sxs-lookup"><span data-stu-id="e6be3-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="e6be3-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="e6be3-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="e6be3-113">WMF 5.0 RTM заменяет [WMF 5.0 Production Preview](http://blogs.msdn.com/b/powershell/archive/2015/08/31/windows-management-framework-5-0-production-preview-is-now-available.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6be3-113">WMF 5.0 RTM replaces the [WMF 5.0 Production Preview](http://blogs.msdn.com/b/powershell/archive/2015/08/31/windows-management-framework-5-0-production-preview-is-now-available.aspx).</span></span> <span data-ttu-id="e6be3-114">Можно установить WMF 5.0 RTM без удаления WMF 5.0 Production Preview, однако перед установкой WMF 5.0 RTM следует удалить другие более старые предварительные версии этого продукта.</span><span class="sxs-lookup"><span data-stu-id="e6be3-114">You can install WMF 5.0 RTM without uninstalling WMF 5.0 Production Preview, but you must uninstall all other older releases of WMF 5.0 previews before installing the WMF 5.0 RTM.</span></span>

<span data-ttu-id="e6be3-115">*Примечание*. При использовании Windows 10 можно получить тот же набор функций, который доступен в WMF 5.0 RTM, путем установки ноябрьского обновления для Windows 10 (версия 1511).</span><span class="sxs-lookup"><span data-stu-id="e6be3-115">*Note:* If you are running Windows 10, you can get the same set of functionality available in WMF 5.0 RTM by updating to the November update of Windows 10 (Version 1511).</span></span> <span data-ttu-id="e6be3-116">Если вы еще не обновили систему Windows 10, нажмите кнопку "Пуск", а затем выберите "Параметры" > "Обновление и безопасность" > "Центр обновления Windows" > "Проверить наличие обновлений".</span><span class="sxs-lookup"><span data-stu-id="e6be3-116">If you have not already updated your Windows 10 system, select the Start button, then select Settings > Update & security > Windows Update > Check for updates.</span></span>
