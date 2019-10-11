---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953391"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="ab926-103">Метод SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab926-103">SendConfiguration method</span></span>

<span data-ttu-id="ab926-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="ab926-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab926-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab926-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="ab926-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab926-106">Parameters</span></span>

<span data-ttu-id="ab926-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ab926-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="ab926-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ab926-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="ab926-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab926-109">Return value</span></span>

<span data-ttu-id="ab926-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ab926-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab926-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="ab926-111">Remarks</span></span>

<span data-ttu-id="ab926-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="ab926-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab926-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ab926-113">Requirements</span></span>

<span data-ttu-id="ab926-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ab926-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ab926-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab926-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ab926-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab926-116">See also</span></span>

[<span data-ttu-id="ab926-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="ab926-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
