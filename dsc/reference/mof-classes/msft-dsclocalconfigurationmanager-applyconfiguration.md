---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 559ff1793a18e28dad2f176bdb20eb53bc08630d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55679695"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="933ae-103">Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="933ae-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="933ae-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="933ae-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="933ae-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="933ae-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="933ae-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="933ae-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="933ae-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="933ae-107">Parameters</span></span>

<span data-ttu-id="933ae-108">*force* \[in\] Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="933ae-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="933ae-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="933ae-109">Return value</span></span>

<span data-ttu-id="933ae-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="933ae-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="933ae-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="933ae-111">Remarks</span></span>

<span data-ttu-id="933ae-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="933ae-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="933ae-113">Требования</span><span class="sxs-lookup"><span data-stu-id="933ae-113">Requirements</span></span>

<span data-ttu-id="933ae-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="933ae-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="933ae-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="933ae-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="933ae-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="933ae-116">See also</span></span>

[<span data-ttu-id="933ae-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="933ae-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)