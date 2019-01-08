---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 1cd887d205967c3d282143df4e6199027639230e
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047521"
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="5e704-103">Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="5e704-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="5e704-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5e704-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e704-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e704-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="5e704-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e704-106">Parameters</span></span>

<span data-ttu-id="5e704-107">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5e704-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="5e704-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5e704-108">Return value</span></span>

<span data-ttu-id="5e704-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5e704-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e704-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="5e704-110">Remarks</span></span>

<span data-ttu-id="5e704-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="5e704-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e704-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5e704-112">Requirements</span></span>

<span data-ttu-id="5e704-113">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5e704-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5e704-114">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5e704-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5e704-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e704-115">See also</span></span>

[<span data-ttu-id="5e704-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5e704-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)