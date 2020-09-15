---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack
ms.openlocfilehash: 301b8926d2ebf1ebe524f52a67928d34e26d860e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464338"
---
# <a name="rollback-method"></a><span data-ttu-id="4fa51-103">Метод RollBack</span><span class="sxs-lookup"><span data-stu-id="4fa51-103">RollBack method</span></span>

<span data-ttu-id="4fa51-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="4fa51-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="4fa51-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fa51-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="4fa51-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fa51-106">Parameters</span></span>

<span data-ttu-id="4fa51-107">**configurationNumber** \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="4fa51-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4fa51-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4fa51-108">Return value</span></span>

<span data-ttu-id="4fa51-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4fa51-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fa51-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fa51-110">Remarks</span></span>

<span data-ttu-id="4fa51-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="4fa51-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4fa51-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4fa51-112">Requirements</span></span>

<span data-ttu-id="4fa51-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4fa51-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4fa51-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4fa51-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4fa51-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4fa51-115">See also</span></span>

[<span data-ttu-id="4fa51-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4fa51-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
