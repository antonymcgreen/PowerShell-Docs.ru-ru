---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 559ff1793a18e28dad2f176bdb20eb53bc08630d
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892622"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="c0dc0-103">Метод ApplyConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="c0dc0-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="c0dc0-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="c0dc0-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="c0dc0-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="c0dc0-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0dc0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0dc0-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="c0dc0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0dc0-107">Parameters</span></span>

<span data-ttu-id="c0dc0-108">*force* \[in\] Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="c0dc0-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0dc0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0dc0-109">Return value</span></span>

<span data-ttu-id="c0dc0-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c0dc0-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0dc0-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="c0dc0-111">Remarks</span></span>

<span data-ttu-id="c0dc0-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="c0dc0-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0dc0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c0dc0-113">Requirements</span></span>

<span data-ttu-id="c0dc0-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c0dc0-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c0dc0-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0dc0-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c0dc0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0dc0-116">See also</span></span>

[<span data-ttu-id="c0dc0-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c0dc0-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)