---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: ef8488246b2c8614452d32009e45535f0ff2e184
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222145"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="0a513-103">Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0a513-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="0a513-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="0a513-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="0a513-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0a513-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>


## <a name="syntax"></a><span data-ttu-id="0a513-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a513-106">Syntax</span></span>
------

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0a513-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a513-107">Parameters</span></span>
----------

<span data-ttu-id="0a513-108">*force* \[in\] Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="0a513-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="0a513-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a513-109">Return value</span></span>
------------

<span data-ttu-id="0a513-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a513-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a513-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="0a513-111">Remarks</span></span>

<span data-ttu-id="0a513-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="0a513-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a513-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0a513-113">Requirements</span></span>
------------
><span data-ttu-id="0a513-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0a513-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="0a513-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a513-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="0a513-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a513-116">See also</span></span>


[<span data-ttu-id="0a513-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0a513-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)