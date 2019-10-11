---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953361"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="f0719-103">Метод StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="f0719-103">StopConfiguration method</span></span>

<span data-ttu-id="f0719-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f0719-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0719-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0719-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="f0719-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0719-106">Parameters</span></span>

<span data-ttu-id="f0719-107">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f0719-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0719-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0719-108">Return value</span></span>

<span data-ttu-id="f0719-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f0719-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0719-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="f0719-110">Remarks</span></span>

<span data-ttu-id="f0719-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="f0719-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0719-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f0719-112">Requirements</span></span>

<span data-ttu-id="f0719-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f0719-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f0719-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f0719-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f0719-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0719-115">See also</span></span>

[<span data-ttu-id="f0719-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f0719-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
