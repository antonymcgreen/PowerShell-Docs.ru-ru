---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration
ms.openlocfilehash: 0425b9a7db37e421830ba37da8f5c0a4877a1b72
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727183"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="57801-103">Метод ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="57801-103">ApplyConfiguration method</span></span>

<span data-ttu-id="57801-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="57801-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="57801-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="57801-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="57801-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57801-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="57801-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="57801-107">Parameters</span></span>

<span data-ttu-id="57801-108">*force* \[in\] Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="57801-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="57801-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57801-109">Return value</span></span>

<span data-ttu-id="57801-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="57801-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="57801-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="57801-111">Remarks</span></span>

<span data-ttu-id="57801-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="57801-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="57801-113">Требования</span><span class="sxs-lookup"><span data-stu-id="57801-113">Requirements</span></span>

<span data-ttu-id="57801-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="57801-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="57801-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="57801-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="57801-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="57801-116">See also</span></span>

[<span data-ttu-id="57801-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="57801-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
