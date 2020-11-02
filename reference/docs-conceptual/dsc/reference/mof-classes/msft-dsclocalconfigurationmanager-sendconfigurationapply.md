---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendConfigurationApply
description: Метод SendConfigurationApply
ms.openlocfilehash: 9bd63220644e096b348f71ee9d4ac216af6a7ccc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648968"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="5a1ff-103">Метод SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="5a1ff-103">SendConfigurationApply method</span></span>

<span data-ttu-id="5a1ff-104">Отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a1ff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a1ff-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="5a1ff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a1ff-106">Parameters</span></span>

<span data-ttu-id="5a1ff-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="5a1ff-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="5a1ff-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a1ff-109">Return value</span></span>

<span data-ttu-id="5a1ff-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a1ff-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a1ff-111">Remarks</span></span>

<span data-ttu-id="5a1ff-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a1ff-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5a1ff-113">Requirements</span></span>

<span data-ttu-id="5a1ff-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5a1ff-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5a1ff-115">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a1ff-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5a1ff-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5a1ff-116">See also</span></span>

[<span data-ttu-id="5a1ff-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5a1ff-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
