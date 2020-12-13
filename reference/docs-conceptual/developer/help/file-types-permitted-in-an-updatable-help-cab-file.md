---
ms.date: 03/22/2012
ms.topic: reference
title: Типы файлов, которые могут использоваться в CAB-файле обновляемой справки
description: Типы файлов, которые могут использоваться в CAB-файле обновляемой справки
ms.openlocfilehash: bb69b8b89a9a3a5c8c00059ec404a4d41a5db9a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654738"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="462c0-103">Типы файлов, которые могут использоваться в CAB-файле обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="462c0-103">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="462c0-104">Несжатое содержимое CAB-файла по умолчанию ограничено 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="462c0-104">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="462c0-105">Чтобы обойти это ограничение, пользователям необходимо использовать параметр **Force** командлетов [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="462c0-105">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="462c0-106">Для обеспечения безопасности файлов справки, загружаемых из Интернета, обновляемый CAB-файл справки может включать только перечисленные ниже типы файлов.</span><span class="sxs-lookup"><span data-stu-id="462c0-106">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="462c0-107">Командлет [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет все файлы по схемам разделов справки.</span><span class="sxs-lookup"><span data-stu-id="462c0-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="462c0-108">Если `Update-Help` командлет встречает файл, который является недопустимым или не является разрешенным типом, он не устанавливает недопустимый файл и прекращает установку файлов из CAB-файла на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="462c0-108">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="462c0-109">Разделы справки на основе XML для командлетов.</span><span class="sxs-lookup"><span data-stu-id="462c0-109">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="462c0-110">Разделы справки на основе XML для скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="462c0-110">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="462c0-111">Разделы справки на основе XML для поставщиков PowerShell.</span><span class="sxs-lookup"><span data-stu-id="462c0-111">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="462c0-112">Разделы справки на основе текста, например о разделах.</span><span class="sxs-lookup"><span data-stu-id="462c0-112">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="462c0-113">[Обновление — Справка](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла при его распаковке.</span><span class="sxs-lookup"><span data-stu-id="462c0-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="462c0-114">Если `Update-Help` находит несовместимые типы файлов в обновляемом CAB-файле справки, он создает завершающую ошибку и останавливает операцию.</span><span class="sxs-lookup"><span data-stu-id="462c0-114">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="462c0-115">Он не устанавливает файлы справки из CAB-файла, даже для соответствующих типов файлов.</span><span class="sxs-lookup"><span data-stu-id="462c0-115">It does not install any help files from the CAB, even those of compliant file types.</span></span>
