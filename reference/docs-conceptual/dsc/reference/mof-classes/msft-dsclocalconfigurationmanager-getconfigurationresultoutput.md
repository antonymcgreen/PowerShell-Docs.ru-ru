---
ms.date: 07/17/2020
ms.topic: reference
title: Метод GetConfigurationResultOutput
description: Метод GetConfigurationResultOutput
ms.openlocfilehash: 7c885109b3078189b7ac653733a5fb24db66312e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644695"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="a41c8-103">Метод GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="a41c8-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="a41c8-104">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="a41c8-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="a41c8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a41c8-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="a41c8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a41c8-106">Parameters</span></span>

<span data-ttu-id="a41c8-107">**jobId** \[in\] Идентификатор задания, для которого необходимо получить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a41c8-107">**jobId** \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="a41c8-108">**resumeOutputBookmark** \[in\] Указывает, что выходные данные должны быть продолжением предыдущей закладки.</span><span class="sxs-lookup"><span data-stu-id="a41c8-108">**resumeOutputBookmark** \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="a41c8-109">**output** \[out\] Выходные данные для указанного задания.</span><span class="sxs-lookup"><span data-stu-id="a41c8-109">**output** \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="a41c8-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a41c8-110">Return value</span></span>

<span data-ttu-id="a41c8-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a41c8-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a41c8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="a41c8-112">Remarks</span></span>

<span data-ttu-id="a41c8-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="a41c8-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a41c8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a41c8-114">Requirements</span></span>

<span data-ttu-id="a41c8-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a41c8-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a41c8-116">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a41c8-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a41c8-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a41c8-117">See also</span></span>

[<span data-ttu-id="a41c8-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a41c8-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
