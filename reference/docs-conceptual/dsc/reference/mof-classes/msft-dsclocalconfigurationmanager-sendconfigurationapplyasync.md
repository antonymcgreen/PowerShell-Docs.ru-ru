---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfigurationApplyAsync
ms.openlocfilehash: 4cfac5edb5fed94ee69deb98d7aa6be56b51c5b3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463743"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="56849-103">Метод SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="56849-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="56849-104">Асинхронно отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56849-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="56849-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56849-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="56849-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="56849-106">Parameters</span></span>

<span data-ttu-id="56849-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56849-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="56849-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56849-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="56849-109">**jobId** \[in\] Идентификатор задания, для которого отправляется конфигурация.</span><span class="sxs-lookup"><span data-stu-id="56849-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="56849-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56849-110">Return value</span></span>

<span data-ttu-id="56849-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="56849-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="56849-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="56849-112">Remarks</span></span>

<span data-ttu-id="56849-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="56849-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="56849-114">Требования</span><span class="sxs-lookup"><span data-stu-id="56849-114">Requirements</span></span>

<span data-ttu-id="56849-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="56849-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="56849-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="56849-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="56849-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="56849-117">See also</span></span>

[<span data-ttu-id="56849-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="56849-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
