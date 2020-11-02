---
ms.date: 07/17/2020
ms.topic: reference
title: Метод GetMetaConfiguration
description: Метод GetMetaConfiguration
ms.openlocfilehash: deca6b8ec342a34543bbe0e1fabbc2a740a88feb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644726"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="295d8-103">Метод GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="295d8-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="295d8-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="295d8-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="295d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="295d8-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="295d8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="295d8-106">Parameters</span></span>

<span data-ttu-id="295d8-107">**MetaConfiguration** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration** , который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="295d8-107">**MetaConfiguration** \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="295d8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="295d8-108">Return value</span></span>

<span data-ttu-id="295d8-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="295d8-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="295d8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="295d8-110">Remarks</span></span>

<span data-ttu-id="295d8-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="295d8-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="295d8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="295d8-112">Requirements</span></span>

<span data-ttu-id="295d8-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="295d8-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="295d8-114">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="295d8-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="295d8-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="295d8-115">See also</span></span>

[<span data-ttu-id="295d8-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="295d8-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
