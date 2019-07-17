---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод TestConfiguration
ms.openlocfilehash: 384134212e3b29b63dc045aee4b708c87c970302
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726956"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="4dae3-103">Метод TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dae3-103">TestConfiguration method</span></span>

<span data-ttu-id="4dae3-104">Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.</span><span class="sxs-lookup"><span data-stu-id="4dae3-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="4dae3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dae3-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="4dae3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4dae3-106">Parameters</span></span>

<span data-ttu-id="4dae3-107">*configurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4dae3-107">*configurationData* \[in\] Environment data for the confuguration.</span></span>

<span data-ttu-id="4dae3-108">*InDesiredState* \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4dae3-108">*InDesiredState* \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="4dae3-109">*ResourcesInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState**, указывающий ресурсы, которые находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="4dae3-109">*ResourcesInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="4dae3-110">*ResourcesNotInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState**, указывающий ресурсы, которые не находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="4dae3-110">*ResourcesNotInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="4dae3-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4dae3-111">Return value</span></span>

<span data-ttu-id="4dae3-112">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4dae3-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4dae3-113">Замечания</span><span class="sxs-lookup"><span data-stu-id="4dae3-113">Remarks</span></span>

<span data-ttu-id="4dae3-114">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="4dae3-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4dae3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="4dae3-115">Requirements</span></span>

<span data-ttu-id="4dae3-116">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4dae3-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4dae3-117">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dae3-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4dae3-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="4dae3-118">See also</span></span>

[<span data-ttu-id="4dae3-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4dae3-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
