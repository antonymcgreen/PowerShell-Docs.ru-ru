---
ms.date: 06/12/2018
keywords: wmf,powershell,установка
title: Windows Management Framework (WMF)
ms.openlocfilehash: 17011f88c364cb56a0c87f092873ccd99db450bc
ms.sourcegitcommit: 68093cc12a7a22c53d11ce7d33c18622921a0dd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36943614"
---
# <a name="windows-management-framework"></a><span data-ttu-id="1a89c-103">Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="1a89c-103">Windows Management Framework</span></span>

<span data-ttu-id="1a89c-104">Windows Management Framework (WMF) — это согласованный интерфейс управления для Windows.</span><span class="sxs-lookup"><span data-stu-id="1a89c-104">Windows Management Framework (WMF) provides a consistent management interface for Windows.</span></span> <span data-ttu-id="1a89c-105">WMF обеспечивает удобный способ управления несколькими версиями клиента Windows и Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1a89c-105">WMF provides a seamless way to manage various versions of Windows client and Windows Server.</span></span> <span data-ttu-id="1a89c-106">Пакеты установщика WMF содержат обновления для функций управления и доступны для более старых версий Windows.</span><span class="sxs-lookup"><span data-stu-id="1a89c-106">WMF installer packages contain updates to management functionality and are available for older versions of Windows.</span></span>

<span data-ttu-id="1a89c-107">При установке WMF добавляются или обновляются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="1a89c-107">WMF installation adds and/or updates the following features:</span></span>

- <span data-ttu-id="1a89c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a89c-108">Windows PowerShell</span></span>
- <span data-ttu-id="1a89c-109">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="1a89c-109">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="1a89c-110">Интегрированная среда сценариев Windows PowerShell (ISE)</span><span class="sxs-lookup"><span data-stu-id="1a89c-110">Windows PowerShell Integrated Script Environment (ISE)</span></span>
- <span data-ttu-id="1a89c-111">Удаленное управление Windows (WinRM)</span><span class="sxs-lookup"><span data-stu-id="1a89c-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="1a89c-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="1a89c-112">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="1a89c-113">Веб-службы Windows PowerShell (расширение IIS OData для управления)</span><span class="sxs-lookup"><span data-stu-id="1a89c-113">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="1a89c-114">Инвентаризация программного обеспечения (SIL)</span><span class="sxs-lookup"><span data-stu-id="1a89c-114">Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="1a89c-115">Поставщик CIM диспетчера сервера</span><span class="sxs-lookup"><span data-stu-id="1a89c-115">Server Manager CIM Provider</span></span>

## <a name="wmf-release-notes"></a><span data-ttu-id="1a89c-116">Заметки о выпуске WMF</span><span class="sxs-lookup"><span data-stu-id="1a89c-116">WMF Release Notes</span></span>

<span data-ttu-id="1a89c-117">Сведения о различных улучшениях в PowerShell и других компонентах определенной версии WMF см. по следующим ссылкам на заметки о выпусках:</span><span class="sxs-lookup"><span data-stu-id="1a89c-117">To learn about various enhancements in PowerShell and other components of a given WMF, please refer to the links below to review the release notes:</span></span>

- [<span data-ttu-id="1a89c-118">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="1a89c-118">WMF 5.1</span></span>](5.1/release-notes.md)
- [<span data-ttu-id="1a89c-119">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="1a89c-119">WMF 5.0</span></span>](5.0/releasenotes.md)
- [<span data-ttu-id="1a89c-120">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="1a89c-120">WMF 4.0</span></span>](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [<span data-ttu-id="1a89c-121">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="1a89c-121">WMF 3.0</span></span>](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a><span data-ttu-id="1a89c-122">Доступность WMF в различных операционных системах Windows</span><span class="sxs-lookup"><span data-stu-id="1a89c-122">WMF Availability Across Windows Operating Systems</span></span>

|<span data-ttu-id="1a89c-123">Версия операционной системы</span><span class="sxs-lookup"><span data-stu-id="1a89c-123">Operating System Version</span></span>  |<span data-ttu-id="1a89c-124">[WMF 5.1][]</span><span class="sxs-lookup"><span data-stu-id="1a89c-124">[WMF 5.1][]</span></span> |<span data-ttu-id="1a89c-125">[WMF 5.0][]</span><span class="sxs-lookup"><span data-stu-id="1a89c-125">[WMF 5.0][]</span></span> |<span data-ttu-id="1a89c-126">[WMF 4.0][]</span><span class="sxs-lookup"><span data-stu-id="1a89c-126">[WMF 4.0][]</span></span> |<span data-ttu-id="1a89c-127">[WMF 3.0][]</span><span class="sxs-lookup"><span data-stu-id="1a89c-127">[WMF 3.0][]</span></span>  |<span data-ttu-id="1a89c-128">[WMF 2.0][]</span><span class="sxs-lookup"><span data-stu-id="1a89c-128">[WMF 2.0][]</span></span> |
|--------------------------|------------|------------|------------|-------------|------------|
|<span data-ttu-id="1a89c-129">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1a89c-129">Windows Server 2016</span></span>       |<span data-ttu-id="1a89c-130">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-130">Ships in-box</span></span>|            |            |             |            |
|<span data-ttu-id="1a89c-131">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1a89c-131">Windows 10</span></span>                |<span data-ttu-id="1a89c-132">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-132">Ships in-box</span></span>|<span data-ttu-id="1a89c-133">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-133">Ships in-box</span></span>|            |             |            |
|<span data-ttu-id="1a89c-134">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1a89c-134">Windows Server 2012 R2</span></span>    |<span data-ttu-id="1a89c-135">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-135">Yes</span></span>         |<span data-ttu-id="1a89c-136">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-136">Yes</span></span>         |<span data-ttu-id="1a89c-137">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-137">Ships in-box</span></span>|             |            |
|<span data-ttu-id="1a89c-138">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1a89c-138">Windows 8.1</span></span>               |<span data-ttu-id="1a89c-139">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-139">Yes</span></span>         |<span data-ttu-id="1a89c-140">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-140">Yes</span></span>         |<span data-ttu-id="1a89c-141">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-141">Ships in-box</span></span>|             |            |
|<span data-ttu-id="1a89c-142">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1a89c-142">Windows Server 2012</span></span>       |<span data-ttu-id="1a89c-143">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-143">Yes</span></span>         |<span data-ttu-id="1a89c-144">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-144">Yes</span></span>         |<span data-ttu-id="1a89c-145">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-145">Yes</span></span>         |<span data-ttu-id="1a89c-146">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-146">Ships in-box</span></span> |            |
|<span data-ttu-id="1a89c-147">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1a89c-147">Windows 8</span></span>                 |            |            |            |<span data-ttu-id="1a89c-148">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-148">Ships in-box</span></span> |            |
|<span data-ttu-id="1a89c-149">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1a89c-149">Windows Server 2008 R2 SP1</span></span>|<span data-ttu-id="1a89c-150">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-150">Yes</span></span>         |<span data-ttu-id="1a89c-151">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-151">Yes</span></span>         |<span data-ttu-id="1a89c-152">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-152">Yes</span></span>         |<span data-ttu-id="1a89c-153">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-153">Yes</span></span>          |<span data-ttu-id="1a89c-154">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-154">Ships in-box</span></span>|
|<span data-ttu-id="1a89c-155">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1a89c-155">Windows 7 SP1</span></span>             |<span data-ttu-id="1a89c-156">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-156">Yes</span></span>         |<span data-ttu-id="1a89c-157">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-157">Yes</span></span>         |<span data-ttu-id="1a89c-158">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-158">Yes</span></span>         |<span data-ttu-id="1a89c-159">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-159">Yes</span></span>          |<span data-ttu-id="1a89c-160">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="1a89c-160">Ships in-box</span></span>|
|<span data-ttu-id="1a89c-161">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="1a89c-161">Windows Server 2008 SP2</span></span>   |            |            |            |<span data-ttu-id="1a89c-162">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-162">Yes</span></span>          |<span data-ttu-id="1a89c-163">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-163">Yes</span></span>         |
|<span data-ttu-id="1a89c-164">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="1a89c-164">Windows Vista</span></span>             |            |            |            |             |<span data-ttu-id="1a89c-165">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-165">Yes</span></span>         |
|<span data-ttu-id="1a89c-166">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="1a89c-166">Windows Server 2003</span></span>       |            |            |            |             |<span data-ttu-id="1a89c-167">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-167">Yes</span></span>         |
|<span data-ttu-id="1a89c-168">Windows XP</span><span class="sxs-lookup"><span data-stu-id="1a89c-168">Windows XP</span></span>                |            |            |            |<span data-ttu-id="1a89c-169">Да</span><span class="sxs-lookup"><span data-stu-id="1a89c-169">Yes</span></span>          |            |

<span data-ttu-id="1a89c-170">**Входит в комплект поставки**: функции указанной версии WMF были включены в указанную версию клиента Windows или Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1a89c-170">**Ships in-box**: The features of the specified version of WMF were shipped in the indicated version of Windows client or Windows Server.</span></span>

[WMF 5.1]: https://aka.ms/wmf51download
[WMF 5.1]: https://aka.ms/wmf51download
[WMF 5.0]: https://aka.ms/wmf5download
[WMF 5.0]: https://aka.ms/wmf5download
[WMF 4.0]: https://aka.ms/wmf4download
[WMF 4.0]: https://aka.ms/wmf4download
[WMF 3.0]: https://aka.ms/wmf3download
[WMF 3.0]: https://aka.ms/wmf3download
[WMF 2.0]: https://aka.ms/wmf2download
[WMF 2.0]: https://aka.ms/wmf2download
