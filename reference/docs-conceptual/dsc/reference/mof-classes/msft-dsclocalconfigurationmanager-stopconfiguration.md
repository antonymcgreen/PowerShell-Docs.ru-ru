---
ms.date: 07/17/2020
ms.topic: reference
title: Метод StopConfiguration
description: Метод StopConfiguration
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644622"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="a473b-103">Метод StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="a473b-103">StopConfiguration method</span></span>

<span data-ttu-id="a473b-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a473b-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="a473b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a473b-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="a473b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a473b-106">Parameters</span></span>

<span data-ttu-id="a473b-107">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a473b-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="a473b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a473b-108">Return value</span></span>

<span data-ttu-id="a473b-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a473b-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a473b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a473b-110">Remarks</span></span>

<span data-ttu-id="a473b-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="a473b-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a473b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a473b-112">Requirements</span></span>

<span data-ttu-id="a473b-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a473b-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a473b-114">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a473b-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a473b-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a473b-115">See also</span></span>

[<span data-ttu-id="a473b-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a473b-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
