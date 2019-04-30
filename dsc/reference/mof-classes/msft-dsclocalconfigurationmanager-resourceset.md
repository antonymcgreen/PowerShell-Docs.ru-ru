---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceSet класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 2712b7ff0a19e643c1f343d436c084f8970c9dd4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078407"
---
# <a name="resourceset-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="983ca-103">Метод ResourceSet класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="983ca-103">ResourceSet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="983ca-104">Напрямую вызывает метод **Set** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="983ca-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="983ca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="983ca-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="983ca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="983ca-106">Parameters</span></span>

<span data-ttu-id="983ca-107">*ResourceType* \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="983ca-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="983ca-108">*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="983ca-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="983ca-109">*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="983ca-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="983ca-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="983ca-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="983ca-111">*RebootRequired* \[out\] В выходных данных это свойство имеет значение **true**, если целевой узел необходимо перезагрузить.</span><span class="sxs-lookup"><span data-stu-id="983ca-111">*RebootRequired* \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="983ca-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="983ca-112">Return value</span></span>

<span data-ttu-id="983ca-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="983ca-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="983ca-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="983ca-114">Remarks</span></span>

<span data-ttu-id="983ca-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="983ca-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="983ca-116">Требования</span><span class="sxs-lookup"><span data-stu-id="983ca-116">Requirements</span></span>

<span data-ttu-id="983ca-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="983ca-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="983ca-118">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="983ca-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="983ca-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="983ca-119">See also</span></span>

[<span data-ttu-id="983ca-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="983ca-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)