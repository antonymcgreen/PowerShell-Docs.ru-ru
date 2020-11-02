---
ms.date: 07/17/2020
ms.topic: reference
title: Метод GetConfiguration
description: Метод GetConfiguration
ms.openlocfilehash: a49f810bd227142c8c3ae4de45f69450400e4e8c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650878"
---
# <a name="getconfiguration-method"></a><span data-ttu-id="2baf8-103">Метод GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="2baf8-103">GetConfiguration method</span></span>

<span data-ttu-id="2baf8-104">Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2baf8-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="2baf8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2baf8-105">Syntax</span></span>

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a><span data-ttu-id="2baf8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2baf8-106">Parameters</span></span>

<span data-ttu-id="2baf8-107">**configurationData** \[in\] Указывает передаваемые данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2baf8-107">**configurationData** \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="2baf8-108">**configurations** \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="2baf8-108">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="2baf8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2baf8-109">Return value</span></span>

<span data-ttu-id="2baf8-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2baf8-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2baf8-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2baf8-111">Remarks</span></span>

<span data-ttu-id="2baf8-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2baf8-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2baf8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2baf8-113">Requirements</span></span>

<span data-ttu-id="2baf8-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2baf8-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2baf8-115">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2baf8-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2baf8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2baf8-116">See also</span></span>

[<span data-ttu-id="2baf8-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2baf8-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
