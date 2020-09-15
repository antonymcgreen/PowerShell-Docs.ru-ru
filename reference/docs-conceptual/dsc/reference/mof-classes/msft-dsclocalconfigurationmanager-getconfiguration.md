---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfiguration
ms.openlocfilehash: 989aeef4cd9aa5d55741b48c8565c657c4b6512c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463828"
---
# <a name="getconfiguration-method"></a><span data-ttu-id="39535-103">Метод GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="39535-103">GetConfiguration method</span></span>

<span data-ttu-id="39535-104">Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="39535-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="39535-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39535-105">Syntax</span></span>

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a><span data-ttu-id="39535-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="39535-106">Parameters</span></span>

<span data-ttu-id="39535-107">**configurationData** \[in\] Указывает передаваемые данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="39535-107">**configurationData** \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="39535-108">**configurations** \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="39535-108">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="39535-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="39535-109">Return value</span></span>

<span data-ttu-id="39535-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="39535-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="39535-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="39535-111">Remarks</span></span>

<span data-ttu-id="39535-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="39535-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="39535-113">Требования</span><span class="sxs-lookup"><span data-stu-id="39535-113">Requirements</span></span>

<span data-ttu-id="39535-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="39535-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="39535-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="39535-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="39535-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="39535-116">See also</span></span>

[<span data-ttu-id="39535-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="39535-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
