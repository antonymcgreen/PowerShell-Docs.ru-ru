---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 559ff1793a18e28dad2f176bdb20eb53bc08630d
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047511"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b68c7-103">Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="b68c7-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b68c7-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="b68c7-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="b68c7-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b68c7-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="b68c7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b68c7-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="b68c7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b68c7-107">Parameters</span></span>

<span data-ttu-id="b68c7-108">*force* \[in\] Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="b68c7-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="b68c7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b68c7-109">Return value</span></span>

<span data-ttu-id="b68c7-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b68c7-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b68c7-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="b68c7-111">Remarks</span></span>

<span data-ttu-id="b68c7-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="b68c7-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b68c7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b68c7-113">Requirements</span></span>

<span data-ttu-id="b68c7-114">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b68c7-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b68c7-115">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b68c7-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b68c7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b68c7-116">See also</span></span>

[<span data-ttu-id="b68c7-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b68c7-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)