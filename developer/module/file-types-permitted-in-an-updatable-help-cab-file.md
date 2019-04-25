---
title: Типы файлов, допустимые в обновляемый файл CAB-файла справки | Документация Майкрософт
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082453"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="a42ed-102">Типы файлов, которые могут использоваться в CAB-файле обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="a42ed-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="a42ed-103">В этом разделе перечислены и описаны требований к содержимому для обновляемой справки CAB-файлов.</span><span class="sxs-lookup"><span data-stu-id="a42ed-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="a42ed-104">Требования к CAB-файл обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="a42ed-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="a42ed-105">По умолчанию несжатого содержимого файла CAB-файлов ограничен 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a42ed-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="a42ed-106">Чтобы обойти это ограничение, пользователи должны использовать **Force** параметр [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлетов.</span><span class="sxs-lookup"><span data-stu-id="a42ed-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="a42ed-107">Чтобы обеспечить безопасность файлов справки, загруженных из Интернета, обновляемой справки CAB-файл можно включить только типы файлов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="a42ed-107">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="a42ed-108">[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) командлет проверяет все файлы по схемам раздела справки.</span><span class="sxs-lookup"><span data-stu-id="a42ed-108">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="a42ed-109">Если `Update-Help` командлет обнаружил файл, который является недопустимым или не является типом разрешенных, он не устанавливает недопустимый файл и останавливает установке файлов из CAB-файла на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="a42ed-109">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="a42ed-110">Основанный на XML разделы справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="a42ed-110">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="a42ed-111">Основанный на XML разделы справки по сценариям и функциям.</span><span class="sxs-lookup"><span data-stu-id="a42ed-111">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="a42ed-112">Основанный на XML разделы справки по поставщикам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a42ed-112">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="a42ed-113">Текстовый разделы справки, таких как разделы справки по модулю.</span><span class="sxs-lookup"><span data-stu-id="a42ed-113">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="a42ed-114">[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) проверяет содержимое CAB-файла, когда он распаковывает CAB.</span><span class="sxs-lookup"><span data-stu-id="a42ed-114">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="a42ed-115">Если `Update-Help` находит файл несовместимые типы в обновляемой справки CAB-файл, он создает неустранимую ошибку и останавливает операцию.</span><span class="sxs-lookup"><span data-stu-id="a42ed-115">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="a42ed-116">Он не устанавливает файлы справки из CAB-файла, даже те файл, совместимый типов.</span><span class="sxs-lookup"><span data-stu-id="a42ed-116">It does not install any help files from the CAB, even those of compliant file types.</span></span>