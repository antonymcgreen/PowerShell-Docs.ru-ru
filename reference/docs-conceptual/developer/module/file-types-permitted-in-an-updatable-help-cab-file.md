---
title: Типы файлов, разрешенные в обновляемом CAB-файле справки | Документация Майкрософт
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 3562804157ebdfca561445a8671d726b55cc4efd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367263"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="5fcf3-102">Типы файлов, которые могут использоваться в CAB-файле обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="5fcf3-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="5fcf3-103">В этом разделе перечислены и описаны требования к содержимому для обновляемых CAB-файлов справки.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="5fcf3-104">Требования к обновляемому CAB-файлу справки</span><span class="sxs-lookup"><span data-stu-id="5fcf3-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="5fcf3-105">Несжатое содержимое CAB-файла по умолчанию ограничено 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="5fcf3-106">Чтобы обойти это ограничение, пользователям необходимо использовать параметр **Force** командлетов [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="5fcf3-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="5fcf3-107">Для обеспечения безопасности файлов справки, загружаемых из Интернета, обновляемый CAB-файл справки может включать только перечисленные ниже типы файлов.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-107">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="5fcf3-108">Командлет [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет все файлы по схемам разделов справки.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-108">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="5fcf3-109">Если командлет `Update-Help` встречает файл, который является недопустимым или не является разрешенным типом, он не устанавливает недопустимый файл и прекращает установку файлов из CAB-файла на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-109">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="5fcf3-110">Разделы справки на основе XML для командлетов.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-110">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="5fcf3-111">Разделы справки на основе XML для скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-111">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="5fcf3-112">Разделы справки на основе XML для поставщиков Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-112">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="5fcf3-113">Разделы справки на основе текста, например о разделах.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-113">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="5fcf3-114">[Обновление — Справка](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла при его распаковке.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-114">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="5fcf3-115">Если `Update-Help` находит несовместимые типы файлов в обновляемом CAB-файле справки, он создает завершающую ошибку и останавливает операцию.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-115">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="5fcf3-116">Он не устанавливает файлы справки из CAB-файла, даже для соответствующих типов файлов.</span><span class="sxs-lookup"><span data-stu-id="5fcf3-116">It does not install any help files from the CAB, even those of compliant file types.</span></span>