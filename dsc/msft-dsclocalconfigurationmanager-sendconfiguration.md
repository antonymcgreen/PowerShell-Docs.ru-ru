---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b4d4c901268344ba67d77e4dc982042bfc2abd78
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222213"
---
# <a name="sendconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="7e5d3-103">Метод SendConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="7e5d3-103">SendConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="7e5d3-104">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="7e5d3-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

<a name="syntax"></a><span data-ttu-id="7e5d3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e5d3-105">Syntax</span></span>
------

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="7e5d3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e5d3-106">Parameters</span></span>
----------

<span data-ttu-id="7e5d3-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7e5d3-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="7e5d3-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7e5d3-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="7e5d3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e5d3-109">Return value</span></span>
------------

<span data-ttu-id="7e5d3-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7e5d3-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e5d3-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="7e5d3-111">Remarks</span></span>

<span data-ttu-id="7e5d3-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="7e5d3-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e5d3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7e5d3-113">Requirements</span></span>
------------
><span data-ttu-id="7e5d3-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7e5d3-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="7e5d3-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e5d3-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="7e5d3-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e5d3-116">See also</span></span>


[<span data-ttu-id="7e5d3-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7e5d3-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)