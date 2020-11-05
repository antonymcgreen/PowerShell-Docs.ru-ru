---
ms.date: 07/17/2020
ms.topic: reference
title: Метод ResourceTest
description: Метод ResourceTest
ms.openlocfilehash: cbac53ea96a59ec92fa840f75cd264a3125b965a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650678"
---
# <a name="resourcetest-method"></a><span data-ttu-id="ca027-103">Метод ResourceTest</span><span class="sxs-lookup"><span data-stu-id="ca027-103">ResourceTest method</span></span>

<span data-ttu-id="ca027-104">Напрямую вызывает метод **Test** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="ca027-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca027-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca027-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="ca027-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca027-106">Parameters</span></span>

<span data-ttu-id="ca027-107">**ResourceType** \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ca027-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="ca027-108">**ModuleName** \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="ca027-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="ca027-109">\**_resourceProperty_* \[in\]. Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="ca027-109">\**_resourceProperty_* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="ca027-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="ca027-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="ca027-111">*InDesiredState*\* \[out\]. В выходных данных это свойство имеет значение **true** , если целевой узел находится в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="ca027-111">*InDesiredState*\* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="ca027-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ca027-112">Return value</span></span>

<span data-ttu-id="ca027-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ca027-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca027-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca027-114">Remarks</span></span>

<span data-ttu-id="ca027-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="ca027-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca027-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ca027-116">Requirements</span></span>

<span data-ttu-id="ca027-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ca027-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ca027-118">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca027-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ca027-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca027-119">See also</span></span>

[<span data-ttu-id="ca027-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="ca027-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
