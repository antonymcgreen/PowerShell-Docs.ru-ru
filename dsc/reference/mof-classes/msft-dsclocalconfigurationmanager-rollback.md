---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727024"
---
# <a name="rollback-method"></a><span data-ttu-id="8c033-103">Метод RollBack</span><span class="sxs-lookup"><span data-stu-id="8c033-103">RollBack method</span></span>

<span data-ttu-id="8c033-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="8c033-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c033-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c033-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="8c033-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c033-106">Parameters</span></span>

<span data-ttu-id="8c033-107">*configurationNumber* \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8c033-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="8c033-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c033-108">Return value</span></span>

<span data-ttu-id="8c033-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c033-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c033-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="8c033-110">Remarks</span></span>

<span data-ttu-id="8c033-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="8c033-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c033-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c033-112">Requirements</span></span>

<span data-ttu-id="8c033-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8c033-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8c033-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c033-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8c033-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c033-115">See also</span></span>

[<span data-ttu-id="8c033-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8c033-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
