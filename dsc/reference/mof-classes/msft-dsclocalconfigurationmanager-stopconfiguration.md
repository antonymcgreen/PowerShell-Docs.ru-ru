---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 1cd887d205967c3d282143df4e6199027639230e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078251"
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a05c7-103">Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="a05c7-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a05c7-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a05c7-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="a05c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a05c7-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="a05c7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a05c7-106">Parameters</span></span>

<span data-ttu-id="a05c7-107">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a05c7-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="a05c7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a05c7-108">Return value</span></span>

<span data-ttu-id="a05c7-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a05c7-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a05c7-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="a05c7-110">Remarks</span></span>

<span data-ttu-id="a05c7-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="a05c7-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a05c7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a05c7-112">Requirements</span></span>

<span data-ttu-id="a05c7-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a05c7-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a05c7-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a05c7-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a05c7-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a05c7-115">See also</span></span>

[<span data-ttu-id="a05c7-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a05c7-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)