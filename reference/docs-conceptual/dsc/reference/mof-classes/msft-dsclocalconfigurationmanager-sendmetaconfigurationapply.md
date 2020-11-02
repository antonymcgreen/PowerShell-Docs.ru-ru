---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendMetaConfigurationApply
description: Метод SendMetaConfigurationApply
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648966"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="4e12c-103">Метод SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="4e12c-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="4e12c-104">Задает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e12c-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e12c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e12c-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="4e12c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e12c-106">Parameters</span></span>

<span data-ttu-id="4e12c-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e12c-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="4e12c-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e12c-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="4e12c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e12c-109">Return value</span></span>

<span data-ttu-id="4e12c-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4e12c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e12c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e12c-111">Remarks</span></span>

<span data-ttu-id="4e12c-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="4e12c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e12c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4e12c-113">Requirements</span></span>

<span data-ttu-id="4e12c-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4e12c-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4e12c-115">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e12c-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4e12c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e12c-116">See also</span></span>

[<span data-ttu-id="4e12c-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4e12c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
