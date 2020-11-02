---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendConfigurationApplyAsync
description: Метод SendConfigurationApplyAsync
ms.openlocfilehash: 92c9d03a7653e72b1ff04084caea4a8b5aadb0e5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644789"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="2dc36-103">Метод SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="2dc36-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="2dc36-104">Асинхронно отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2dc36-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="2dc36-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dc36-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="2dc36-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dc36-106">Parameters</span></span>

<span data-ttu-id="2dc36-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2dc36-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="2dc36-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2dc36-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="2dc36-109">**jobId** \[in\] Идентификатор задания, для которого отправляется конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2dc36-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="2dc36-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2dc36-110">Return value</span></span>

<span data-ttu-id="2dc36-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2dc36-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dc36-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dc36-112">Remarks</span></span>

<span data-ttu-id="2dc36-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2dc36-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2dc36-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2dc36-114">Requirements</span></span>

<span data-ttu-id="2dc36-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2dc36-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2dc36-116">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2dc36-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2dc36-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2dc36-117">See also</span></span>

[<span data-ttu-id="2dc36-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2dc36-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
