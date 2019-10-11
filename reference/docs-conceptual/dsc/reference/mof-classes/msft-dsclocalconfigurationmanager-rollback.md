---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954941"
---
# <a name="rollback-method"></a><span data-ttu-id="bb112-103">Метод RollBack</span><span class="sxs-lookup"><span data-stu-id="bb112-103">RollBack method</span></span>

<span data-ttu-id="bb112-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="bb112-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb112-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb112-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="bb112-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb112-106">Parameters</span></span>

<span data-ttu-id="bb112-107">*configurationNumber* \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bb112-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb112-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb112-108">Return value</span></span>

<span data-ttu-id="bb112-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bb112-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb112-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="bb112-110">Remarks</span></span>

<span data-ttu-id="bb112-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="bb112-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb112-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bb112-112">Requirements</span></span>

<span data-ttu-id="bb112-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bb112-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="bb112-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bb112-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="bb112-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb112-115">See also</span></span>

[<span data-ttu-id="bb112-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="bb112-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
