---
ms.date: 07/14/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод ApplyConfiguration
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463845"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="3cbdd-103">Метод ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cbdd-103">ApplyConfiguration method</span></span>

<span data-ttu-id="3cbdd-104">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="3cbdd-105">Если нет ожидающих конфигураций, этот метод повторно применяет текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cbdd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cbdd-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="3cbdd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cbdd-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="3cbdd-108">force</span><span class="sxs-lookup"><span data-stu-id="3cbdd-108">force</span></span>

<span data-ttu-id="3cbdd-109">Если параметр имеет значение **true**, текущая конфигурация применяется повторно даже при наличии конфигурации в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="3cbdd-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3cbdd-110">Return value</span></span>

<span data-ttu-id="3cbdd-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cbdd-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3cbdd-112">Remarks</span></span>

<span data-ttu-id="3cbdd-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3cbdd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3cbdd-114">Requirements</span></span>

<span data-ttu-id="3cbdd-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3cbdd-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3cbdd-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cbdd-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3cbdd-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cbdd-117">See also</span></span>

[<span data-ttu-id="3cbdd-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3cbdd-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
