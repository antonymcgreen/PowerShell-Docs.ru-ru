---
ms.date: 07/17/2020
ms.topic: reference
title: Метод TestConfiguration
description: Метод TestConfiguration
ms.openlocfilehash: ed26fcad2286ca753fb4b1845b8c6ad0741d491b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648930"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="3c6d2-103">Метод TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="3c6d2-103">TestConfiguration method</span></span>

<span data-ttu-id="3c6d2-104">Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c6d2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c6d2-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="3c6d2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c6d2-106">Parameters</span></span>

<span data-ttu-id="3c6d2-107">**configurationData** \[in\]. Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="3c6d2-108">**InDesiredState** \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="3c6d2-109">**ResourcesInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState** , определяющий ресурсы, которые находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="3c6d2-110">**ResourcesNotInDesiredState** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState** , определяющий ресурсы, которые не находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="3c6d2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c6d2-111">Return value</span></span>

<span data-ttu-id="3c6d2-112">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c6d2-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c6d2-113">Remarks</span></span>

<span data-ttu-id="3c6d2-114">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="3c6d2-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c6d2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3c6d2-115">Requirements</span></span>

<span data-ttu-id="3c6d2-116">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3c6d2-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3c6d2-117">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3c6d2-117">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3c6d2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c6d2-118">See also</span></span>

[<span data-ttu-id="3c6d2-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3c6d2-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
