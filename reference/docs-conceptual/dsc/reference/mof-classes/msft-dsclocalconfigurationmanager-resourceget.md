---
ms.date: 07/17/2020
ms.topic: reference
title: Метод ResourceGet
description: Метод ResourceGet
ms.openlocfilehash: bff737f04e02740fa09fd82d7b27c75b11303dad
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650764"
---
# <a name="resourceget-method"></a><span data-ttu-id="88c34-103">Метод ResourceGet</span><span class="sxs-lookup"><span data-stu-id="88c34-103">ResourceGet method</span></span>

<span data-ttu-id="88c34-104">Напрямую вызывает метод **Get** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="88c34-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="88c34-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88c34-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="88c34-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="88c34-106">Parameters</span></span>

<span data-ttu-id="88c34-107">**ResourceType** \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="88c34-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="88c34-108">**ModuleName** \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="88c34-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="88c34-109">**resourceProperty** \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="88c34-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="88c34-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="88c34-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="88c34-111">**configurations** \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="88c34-111">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="88c34-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88c34-112">Return value</span></span>

<span data-ttu-id="88c34-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="88c34-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="88c34-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="88c34-114">Remarks</span></span>

<span data-ttu-id="88c34-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="88c34-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="88c34-116">Требования</span><span class="sxs-lookup"><span data-stu-id="88c34-116">Requirements</span></span>

<span data-ttu-id="88c34-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="88c34-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="88c34-118">**Пространство имен** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="88c34-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="88c34-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="88c34-119">See also</span></span>

[<span data-ttu-id="88c34-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="88c34-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
