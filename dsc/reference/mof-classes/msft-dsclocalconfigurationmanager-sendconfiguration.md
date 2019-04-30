---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 3529bc56ecba19ed0fbbf070a4e86d0692824d39
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078390"
---
# <a name="sendconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="224af-103">Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="224af-103">SendConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="224af-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="224af-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="224af-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="224af-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="224af-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="224af-106">Parameters</span></span>

<span data-ttu-id="224af-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="224af-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="224af-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="224af-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="224af-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="224af-109">Return value</span></span>

<span data-ttu-id="224af-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="224af-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="224af-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="224af-111">Remarks</span></span>

<span data-ttu-id="224af-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="224af-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="224af-113">Требования</span><span class="sxs-lookup"><span data-stu-id="224af-113">Requirements</span></span>

<span data-ttu-id="224af-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="224af-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="224af-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="224af-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="224af-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="224af-116">See also</span></span>

[<span data-ttu-id="224af-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="224af-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)