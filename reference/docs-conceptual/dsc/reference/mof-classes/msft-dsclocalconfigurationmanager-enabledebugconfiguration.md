---
ms.date: 07/17/2020
ms.topic: reference
title: Метод EnableDebugConfiguration
description: Метод EnableDebugConfiguration
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644777"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="2a724-103">Метод EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a724-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="2a724-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="2a724-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a724-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a724-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="2a724-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a724-106">Parameters</span></span>

<span data-ttu-id="2a724-107">**BreakAll** \[in\] Устанавливает точку останова в каждой строке в скрипте ресурса.</span><span class="sxs-lookup"><span data-stu-id="2a724-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="2a724-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a724-108">Return value</span></span>

<span data-ttu-id="2a724-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a724-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a724-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a724-110">Remarks</span></span>

<span data-ttu-id="2a724-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2a724-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a724-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2a724-112">Requirements</span></span>

<span data-ttu-id="2a724-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2a724-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2a724-114">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a724-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2a724-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a724-115">See also</span></span>

[<span data-ttu-id="2a724-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2a724-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
