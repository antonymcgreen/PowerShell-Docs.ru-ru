---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfigurationApplyAsync класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b028079cf826719967858f50e357b441ba8f9d79
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078283"
---
# <a name="sendconfigurationapplyasync-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="49b89-103">Метод SendConfigurationApplyAsync класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="49b89-103">SendConfigurationApplyAsync method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="49b89-104">Асинхронно отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="49b89-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="49b89-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49b89-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="49b89-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="49b89-106">Parameters</span></span>

<span data-ttu-id="49b89-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="49b89-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="49b89-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="49b89-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="49b89-109">*jobId* \[in\] Идентификатор задания, для которого отправляется конфигурация.</span><span class="sxs-lookup"><span data-stu-id="49b89-109">*jobId* \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="49b89-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49b89-110">Return value</span></span>

<span data-ttu-id="49b89-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="49b89-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="49b89-112">Замечания</span><span class="sxs-lookup"><span data-stu-id="49b89-112">Remarks</span></span>

<span data-ttu-id="49b89-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="49b89-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="49b89-114">Требования</span><span class="sxs-lookup"><span data-stu-id="49b89-114">Requirements</span></span>

<span data-ttu-id="49b89-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="49b89-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="49b89-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="49b89-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="49b89-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="49b89-117">See also</span></span>

[<span data-ttu-id="49b89-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="49b89-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)