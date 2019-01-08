---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendMetaConfigurationApply класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b372a6c0ab9d4561dcf67026275e7d3ca6aa2584
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047853"
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="dd6f3-103">Метод SendMetaConfigurationApply класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="dd6f3-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="dd6f3-104">Задает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dd6f3-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd6f3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd6f3-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="dd6f3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd6f3-106">Parameters</span></span>

<span data-ttu-id="dd6f3-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dd6f3-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="dd6f3-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dd6f3-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="dd6f3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd6f3-109">Return value</span></span>

<span data-ttu-id="dd6f3-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dd6f3-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd6f3-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="dd6f3-111">Remarks</span></span>

<span data-ttu-id="dd6f3-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="dd6f3-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd6f3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dd6f3-113">Requirements</span></span>

<span data-ttu-id="dd6f3-114">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="dd6f3-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="dd6f3-115">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="dd6f3-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="dd6f3-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd6f3-116">See also</span></span>

[<span data-ttu-id="dd6f3-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="dd6f3-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)