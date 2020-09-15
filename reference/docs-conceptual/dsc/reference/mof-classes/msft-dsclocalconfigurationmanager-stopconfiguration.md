---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration
ms.openlocfilehash: 76e50c98b09dca86983320918c6899082580672a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463709"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="dc938-103">Метод StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="dc938-103">StopConfiguration method</span></span>

<span data-ttu-id="dc938-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dc938-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc938-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc938-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="dc938-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc938-106">Parameters</span></span>

<span data-ttu-id="dc938-107">**force** \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dc938-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="dc938-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc938-108">Return value</span></span>

<span data-ttu-id="dc938-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dc938-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc938-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc938-110">Remarks</span></span>

<span data-ttu-id="dc938-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="dc938-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc938-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dc938-112">Requirements</span></span>

<span data-ttu-id="dc938-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="dc938-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="dc938-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="dc938-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="dc938-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dc938-115">See also</span></span>

[<span data-ttu-id="dc938-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="dc938-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
