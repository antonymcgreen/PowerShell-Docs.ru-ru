---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953391"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="af86f-103">Метод SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="af86f-103">SendConfiguration method</span></span>

<span data-ttu-id="af86f-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="af86f-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="af86f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af86f-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="af86f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="af86f-106">Parameters</span></span>

<span data-ttu-id="af86f-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af86f-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="af86f-108">*force* \[in\] **true** Принудительная остановка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af86f-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="af86f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af86f-109">Return value</span></span>

<span data-ttu-id="af86f-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="af86f-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af86f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="af86f-111">Remarks</span></span>

<span data-ttu-id="af86f-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="af86f-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="af86f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="af86f-113">Requirements</span></span>

<span data-ttu-id="af86f-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="af86f-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="af86f-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="af86f-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="af86f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af86f-116">See also</span></span>

[<span data-ttu-id="af86f-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="af86f-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
