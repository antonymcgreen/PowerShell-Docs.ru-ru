---
ms.date: 07/14/2020
ms.topic: reference
title: Метод ApplyConfiguration
description: Метод ApplyConfiguration
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664268"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="49294-103">Метод ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="49294-103">ApplyConfiguration method</span></span>

<span data-ttu-id="49294-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="49294-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="49294-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="49294-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="49294-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49294-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="49294-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="49294-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="49294-108">force</span><span class="sxs-lookup"><span data-stu-id="49294-108">force</span></span>

<span data-ttu-id="49294-109">Если параметр имеет значение **true** , текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="49294-109">If this is **true** , the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="49294-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49294-110">Return value</span></span>

<span data-ttu-id="49294-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="49294-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="49294-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="49294-112">Remarks</span></span>

<span data-ttu-id="49294-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="49294-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="49294-114">Требования</span><span class="sxs-lookup"><span data-stu-id="49294-114">Requirements</span></span>

<span data-ttu-id="49294-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="49294-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="49294-116">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="49294-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="49294-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="49294-117">See also</span></span>

[<span data-ttu-id="49294-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="49294-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
