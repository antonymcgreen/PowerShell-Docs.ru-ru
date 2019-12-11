---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953391"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="485f0-103">Метод SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="485f0-103">SendConfiguration method</span></span>

<span data-ttu-id="485f0-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="485f0-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="485f0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="485f0-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="485f0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="485f0-106">Parameters</span></span>

<span data-ttu-id="485f0-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="485f0-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="485f0-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="485f0-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="485f0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="485f0-109">Return value</span></span>

<span data-ttu-id="485f0-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="485f0-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="485f0-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="485f0-111">Remarks</span></span>

<span data-ttu-id="485f0-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="485f0-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="485f0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="485f0-113">Requirements</span></span>

<span data-ttu-id="485f0-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="485f0-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="485f0-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="485f0-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="485f0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="485f0-116">See also</span></span>

[<span data-ttu-id="485f0-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="485f0-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
