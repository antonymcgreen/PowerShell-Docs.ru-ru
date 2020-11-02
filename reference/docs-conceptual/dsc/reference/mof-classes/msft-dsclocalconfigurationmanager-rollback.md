---
ms.date: 07/17/2020
ms.topic: reference
title: Метод RollBack
description: Метод RollBack
ms.openlocfilehash: 82ca54ed23a3a892b785f603be3b423def5ee636
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650624"
---
# <a name="rollback-method"></a><span data-ttu-id="d915e-103">Метод RollBack</span><span class="sxs-lookup"><span data-stu-id="d915e-103">RollBack method</span></span>

<span data-ttu-id="d915e-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="d915e-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="d915e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d915e-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="d915e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d915e-106">Parameters</span></span>

<span data-ttu-id="d915e-107">**configurationNumber** \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d915e-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="d915e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d915e-108">Return value</span></span>

<span data-ttu-id="d915e-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d915e-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d915e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d915e-110">Remarks</span></span>

<span data-ttu-id="d915e-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="d915e-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d915e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d915e-112">Requirements</span></span>

<span data-ttu-id="d915e-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d915e-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="d915e-114">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d915e-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="d915e-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d915e-115">See also</span></span>

[<span data-ttu-id="d915e-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="d915e-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
