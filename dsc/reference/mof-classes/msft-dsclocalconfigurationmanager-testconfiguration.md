---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод TestConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: d746832b01310f43a7aae33dd0fa70c0928bb3e0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078084"
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="9c4c9-103">Метод TestConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="9c4c9-103">TestConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="9c4c9-104">Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c4c9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c4c9-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="9c4c9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c4c9-106">Parameters</span></span>

<span data-ttu-id="9c4c9-107">*configurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-107">*configurationData* \[in\] Environment data for the confuguration.</span></span>

<span data-ttu-id="9c4c9-108">*InDesiredState* \[out\] В выходных данных указывает, находится ли управляемый узел в состоянии, указанном в документе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-108">*InDesiredState* \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="9c4c9-109">*ResourcesInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceInDesiredState**, указывающий ресурсы, которые находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-109">*ResourcesInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="9c4c9-110">*ResourcesNotInDesiredState* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_ResourceNotInDesiredState**, указывающий ресурсы, которые не находятся в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-110">*ResourcesNotInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="9c4c9-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c4c9-111">Return value</span></span>

<span data-ttu-id="9c4c9-112">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c4c9-113">Замечания</span><span class="sxs-lookup"><span data-stu-id="9c4c9-113">Remarks</span></span>

<span data-ttu-id="9c4c9-114">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c4c9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9c4c9-115">Requirements</span></span>

<span data-ttu-id="9c4c9-116">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="9c4c9-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="9c4c9-117">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c4c9-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="9c4c9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c4c9-118">See also</span></span>

[<span data-ttu-id="9c4c9-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="9c4c9-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)