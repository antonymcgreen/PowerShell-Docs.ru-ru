---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: ea572a4a66befd4e4b8d83e2957632b1b5ed7d93
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893949"
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a388d-103">Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="a388d-103">GetConfigurationResultOutput method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a388d-104">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="a388d-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="a388d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a388d-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="a388d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a388d-106">Parameters</span></span>

<span data-ttu-id="a388d-107">*jobId* \[in\] Идентификатор задания, для которого необходимо получить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a388d-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="a388d-108">*resumeOutputBookmark* \[in\] Указывает, что выходные данные должны быть продолжением от предыдущей закладки.</span><span class="sxs-lookup"><span data-stu-id="a388d-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="a388d-109">*output* \[out\] Выходные данные для указанного задания.</span><span class="sxs-lookup"><span data-stu-id="a388d-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="a388d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a388d-110">Return value</span></span>

<span data-ttu-id="a388d-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a388d-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a388d-112">Замечания</span><span class="sxs-lookup"><span data-stu-id="a388d-112">Remarks</span></span>

<span data-ttu-id="a388d-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="a388d-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a388d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a388d-114">Requirements</span></span>

<span data-ttu-id="a388d-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a388d-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a388d-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a388d-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a388d-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="a388d-117">See also</span></span>

[<span data-ttu-id="a388d-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a388d-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)