---
ms.date: 07/17/2020
ms.topic: reference
title: Метод SendConfiguration
description: Метод SendConfiguration
ms.openlocfilehash: 3939a76ab6672b49559847b0ef1408f1c7be6d0c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650561"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="14130-103">Метод SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="14130-103">SendConfiguration method</span></span>

<span data-ttu-id="14130-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="14130-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="14130-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14130-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="14130-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="14130-106">Parameters</span></span>

<span data-ttu-id="14130-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="14130-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="14130-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="14130-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="14130-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14130-109">Return value</span></span>

<span data-ttu-id="14130-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="14130-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="14130-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="14130-111">Remarks</span></span>

<span data-ttu-id="14130-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="14130-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="14130-113">Требования</span><span class="sxs-lookup"><span data-stu-id="14130-113">Requirements</span></span>

<span data-ttu-id="14130-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="14130-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="14130-115">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="14130-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="14130-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14130-116">See also</span></span>

[<span data-ttu-id="14130-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="14130-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
