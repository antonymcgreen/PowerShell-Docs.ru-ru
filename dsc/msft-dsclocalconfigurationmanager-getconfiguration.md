---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 46eec896df643996bea5f2c371a9294034caae6b
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218422"
---
# <a name="getconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="e7a4c-103">Метод GetConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="e7a4c-103">GetConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="e7a4c-104">Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="e7a4c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7a4c-105">Syntax</span></span>
------

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

<a name="parameters"></a><span data-ttu-id="e7a4c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7a4c-106">Parameters</span></span>
----------

<span data-ttu-id="e7a4c-107">*configurationData* \[in\] Указывает передаваемые данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-107">*configurationData* \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="e7a4c-108">*configurations* \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-108">*configurations* \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="e7a4c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7a4c-109">Return value</span></span>
------------

<span data-ttu-id="e7a4c-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7a4c-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="e7a4c-111">Remarks</span></span>

<span data-ttu-id="e7a4c-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="e7a4c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e7a4c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e7a4c-113">Requirements</span></span>
------------
><span data-ttu-id="e7a4c-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e7a4c-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="e7a4c-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a4c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="e7a4c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7a4c-116">See also</span></span>


[<span data-ttu-id="e7a4c-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e7a4c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)