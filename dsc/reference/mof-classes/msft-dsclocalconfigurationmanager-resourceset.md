---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceSet класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 2712b7ff0a19e643c1f343d436c084f8970c9dd4
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047667"
---
# <a name="resourceset-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="74448-103">Метод ResourceSet класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="74448-103">ResourceSet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="74448-104">Напрямую вызывает метод **Set** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="74448-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="74448-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74448-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="74448-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="74448-106">Parameters</span></span>

<span data-ttu-id="74448-107">*ResourceType* \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="74448-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="74448-108">*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="74448-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="74448-109">*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="74448-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="74448-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="74448-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="74448-111">*RebootRequired* \[out\] В выходных данных это свойство имеет значение **true**, если целевой узел необходимо перезагрузить.</span><span class="sxs-lookup"><span data-stu-id="74448-111">*RebootRequired* \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="74448-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="74448-112">Return value</span></span>

<span data-ttu-id="74448-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="74448-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="74448-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="74448-114">Remarks</span></span>

<span data-ttu-id="74448-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="74448-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="74448-116">Требования</span><span class="sxs-lookup"><span data-stu-id="74448-116">Requirements</span></span>

<span data-ttu-id="74448-117">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="74448-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="74448-118">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="74448-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="74448-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="74448-119">See also</span></span>

[<span data-ttu-id="74448-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="74448-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)