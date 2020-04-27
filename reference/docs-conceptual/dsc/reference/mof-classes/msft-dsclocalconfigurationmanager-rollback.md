---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954941"
---
# <a name="rollback-method"></a><span data-ttu-id="6ef10-103">Метод RollBack</span><span class="sxs-lookup"><span data-stu-id="6ef10-103">RollBack method</span></span>

<span data-ttu-id="6ef10-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="6ef10-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ef10-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ef10-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="6ef10-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ef10-106">Parameters</span></span>

<span data-ttu-id="6ef10-107">*configurationNumber* \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6ef10-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="6ef10-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ef10-108">Return value</span></span>

<span data-ttu-id="6ef10-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ef10-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ef10-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ef10-110">Remarks</span></span>

<span data-ttu-id="6ef10-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="6ef10-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ef10-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6ef10-112">Requirements</span></span>

<span data-ttu-id="6ef10-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6ef10-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="6ef10-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef10-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef10-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ef10-115">See also</span></span>

[<span data-ttu-id="6ef10-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="6ef10-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
