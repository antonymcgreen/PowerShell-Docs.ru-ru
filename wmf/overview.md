---
ms.date: 06/12/2018
keywords: wmf,powershell,установка
title: Windows Management Framework (WMF)
ms.openlocfilehash: f279f975527dc198dd9b47ca1dc4258f54fafef5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55679994"
---
# <a name="windows-management-framework"></a><span data-ttu-id="4805b-103">Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="4805b-103">Windows Management Framework</span></span>

<span data-ttu-id="4805b-104">Windows Management Framework (WMF) — это согласованный интерфейс управления для Windows.</span><span class="sxs-lookup"><span data-stu-id="4805b-104">Windows Management Framework (WMF) provides a consistent management interface for Windows.</span></span> <span data-ttu-id="4805b-105">WMF обеспечивает удобный способ управления несколькими версиями клиента Windows и Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4805b-105">WMF provides a seamless way to manage various versions of Windows client and Windows Server.</span></span> <span data-ttu-id="4805b-106">Пакеты установщика WMF содержат обновления для функций управления и доступны для более старых версий Windows.</span><span class="sxs-lookup"><span data-stu-id="4805b-106">WMF installer packages contain updates to management functionality and are available for older versions of Windows.</span></span>

<span data-ttu-id="4805b-107">При установке WMF добавляются или обновляются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4805b-107">WMF installation adds and/or updates the following features:</span></span>

- <span data-ttu-id="4805b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4805b-108">Windows PowerShell</span></span>
- <span data-ttu-id="4805b-109">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="4805b-109">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="4805b-110">Интегрированная среда сценариев Windows PowerShell (ISE)</span><span class="sxs-lookup"><span data-stu-id="4805b-110">Windows PowerShell Integrated Script Environment (ISE)</span></span>
- <span data-ttu-id="4805b-111">Удаленное управление Windows (WinRM)</span><span class="sxs-lookup"><span data-stu-id="4805b-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="4805b-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="4805b-112">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="4805b-113">Веб-службы Windows PowerShell (расширение IIS OData для управления)</span><span class="sxs-lookup"><span data-stu-id="4805b-113">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="4805b-114">Инвентаризация программного обеспечения (SIL)</span><span class="sxs-lookup"><span data-stu-id="4805b-114">Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="4805b-115">Поставщик CIM диспетчера сервера</span><span class="sxs-lookup"><span data-stu-id="4805b-115">Server Manager CIM Provider</span></span>

## <a name="wmf-release-notes"></a><span data-ttu-id="4805b-116">Заметки о выпуске WMF</span><span class="sxs-lookup"><span data-stu-id="4805b-116">WMF Release Notes</span></span>

<span data-ttu-id="4805b-117">Сведения о различных улучшениях в PowerShell и других компонентах определенной версии WMF см. по следующим ссылкам на заметки о выпусках:</span><span class="sxs-lookup"><span data-stu-id="4805b-117">To learn about various enhancements in PowerShell and other components of a given WMF, please refer to the links below to review the release notes:</span></span>

- [<span data-ttu-id="4805b-118">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="4805b-118">WMF 5.1</span></span>](5.1/release-notes.md)
- [<span data-ttu-id="4805b-119">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="4805b-119">WMF 5.0</span></span>](5.0/releasenotes.md)
- [<span data-ttu-id="4805b-120">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="4805b-120">WMF 4.0</span></span>](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [<span data-ttu-id="4805b-121">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="4805b-121">WMF 3.0</span></span>](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a><span data-ttu-id="4805b-122">Доступность WMF в различных операционных системах Windows</span><span class="sxs-lookup"><span data-stu-id="4805b-122">WMF Availability Across Windows Operating Systems</span></span>

|<span data-ttu-id="4805b-123">Версия операционной системы</span><span class="sxs-lookup"><span data-stu-id="4805b-123">Operating System Version</span></span>  |<span data-ttu-id="4805b-124">[WMF 5.1][]</span><span class="sxs-lookup"><span data-stu-id="4805b-124">[WMF 5.1][]</span></span> |<span data-ttu-id="4805b-125">[WMF 5.0][]</span><span class="sxs-lookup"><span data-stu-id="4805b-125">[WMF 5.0][]</span></span> |<span data-ttu-id="4805b-126">[WMF 4.0][]</span><span class="sxs-lookup"><span data-stu-id="4805b-126">[WMF 4.0][]</span></span> |<span data-ttu-id="4805b-127">[WMF 3.0][]</span><span class="sxs-lookup"><span data-stu-id="4805b-127">[WMF 3.0][]</span></span>  |<span data-ttu-id="4805b-128">[WMF 2.0][]</span><span class="sxs-lookup"><span data-stu-id="4805b-128">[WMF 2.0][]</span></span> |
|--------------------------|------------|------------|------------|-------------|------------|
|<span data-ttu-id="4805b-129">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4805b-129">Windows Server 2019</span></span>       |<span data-ttu-id="4805b-130">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-130">Ships in-box</span></span>|            |            |             |            |
|<span data-ttu-id="4805b-131">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4805b-131">Windows Server 2016</span></span>       |<span data-ttu-id="4805b-132">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-132">Ships in-box</span></span>|            |            |             |            |
|<span data-ttu-id="4805b-133">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4805b-133">Windows 10</span></span>                |<span data-ttu-id="4805b-134">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-134">Ships in-box</span></span>|<span data-ttu-id="4805b-135">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-135">Ships in-box</span></span>|            |             |            |
|<span data-ttu-id="4805b-136">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4805b-136">Windows Server 2012 R2</span></span>    |<span data-ttu-id="4805b-137">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-137">Yes</span></span>         |<span data-ttu-id="4805b-138">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-138">Yes</span></span>         |<span data-ttu-id="4805b-139">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-139">Ships in-box</span></span>|             |            |
|<span data-ttu-id="4805b-140">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4805b-140">Windows 8.1</span></span>               |<span data-ttu-id="4805b-141">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-141">Yes</span></span>         |<span data-ttu-id="4805b-142">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-142">Yes</span></span>         |<span data-ttu-id="4805b-143">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-143">Ships in-box</span></span>|             |            |
|<span data-ttu-id="4805b-144">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4805b-144">Windows Server 2012</span></span>       |<span data-ttu-id="4805b-145">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-145">Yes</span></span>         |<span data-ttu-id="4805b-146">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-146">Yes</span></span>         |<span data-ttu-id="4805b-147">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-147">Yes</span></span>         |<span data-ttu-id="4805b-148">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-148">Ships in-box</span></span> |            |
|<span data-ttu-id="4805b-149">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4805b-149">Windows 8</span></span>                 |            |            |            |<span data-ttu-id="4805b-150">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-150">Ships in-box</span></span> |            |
|<span data-ttu-id="4805b-151">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4805b-151">Windows Server 2008 R2 SP1</span></span>|<span data-ttu-id="4805b-152">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-152">Yes</span></span>         |<span data-ttu-id="4805b-153">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-153">Yes</span></span>         |<span data-ttu-id="4805b-154">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-154">Yes</span></span>         |<span data-ttu-id="4805b-155">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-155">Yes</span></span>          |<span data-ttu-id="4805b-156">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-156">Ships in-box</span></span>|
|<span data-ttu-id="4805b-157">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4805b-157">Windows 7 SP1</span></span>             |<span data-ttu-id="4805b-158">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-158">Yes</span></span>         |<span data-ttu-id="4805b-159">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-159">Yes</span></span>         |<span data-ttu-id="4805b-160">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-160">Yes</span></span>         |<span data-ttu-id="4805b-161">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-161">Yes</span></span>          |<span data-ttu-id="4805b-162">Входит в комплект поставки</span><span class="sxs-lookup"><span data-stu-id="4805b-162">Ships in-box</span></span>|
|<span data-ttu-id="4805b-163">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="4805b-163">Windows Server 2008 SP2</span></span>   |            |            |            |<span data-ttu-id="4805b-164">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-164">Yes</span></span>          |<span data-ttu-id="4805b-165">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-165">Yes</span></span>         |
|<span data-ttu-id="4805b-166">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="4805b-166">Windows Vista</span></span>             |            |            |            |             |<span data-ttu-id="4805b-167">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-167">Yes</span></span>         |
|<span data-ttu-id="4805b-168">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="4805b-168">Windows Server 2003</span></span>       |            |            |            |             |<span data-ttu-id="4805b-169">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-169">Yes</span></span>         |
|<span data-ttu-id="4805b-170">Windows XP</span><span class="sxs-lookup"><span data-stu-id="4805b-170">Windows XP</span></span>                |            |            |            |<span data-ttu-id="4805b-171">Да</span><span class="sxs-lookup"><span data-stu-id="4805b-171">Yes</span></span>          |            |

<span data-ttu-id="4805b-172">**Входит в комплект поставки**: функции указанной версии WMF были включены в указанную версию клиента Windows или Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4805b-172">**Ships in-box**: The features of the specified version of WMF were shipped in the indicated version of Windows client or Windows Server.</span></span>

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
