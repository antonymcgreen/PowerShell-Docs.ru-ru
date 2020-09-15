---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод SendMetaConfigurationApply
ms.openlocfilehash: 896afe2f3370e108b48583aafb33ee7b0eb1301b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463726"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="7c526-103">Метод SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="7c526-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="7c526-104">Задает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c526-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c526-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c526-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="7c526-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c526-106">Parameters</span></span>

<span data-ttu-id="7c526-107">**ConfigurationData** \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c526-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="7c526-108">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c526-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="7c526-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7c526-109">Return value</span></span>

<span data-ttu-id="7c526-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7c526-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c526-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c526-111">Remarks</span></span>

<span data-ttu-id="7c526-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="7c526-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c526-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7c526-113">Requirements</span></span>

<span data-ttu-id="7c526-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7c526-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="7c526-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c526-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="7c526-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7c526-116">See also</span></span>

[<span data-ttu-id="7c526-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7c526-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
