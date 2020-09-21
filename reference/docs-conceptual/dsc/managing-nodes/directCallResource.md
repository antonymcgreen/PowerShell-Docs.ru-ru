---
ms.date: 08/11/2020
keywords: dsc,powershell,конфигурация,установка
title: Прямой вызов методов ресурсов DSC
ms.openlocfilehash: 029a278c938e414820e172b85fac3cb3ad4b4afa
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162500"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="83b6f-103">Прямой вызов методов ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="83b6f-103">Calling DSC resource methods directly</span></span>

><span data-ttu-id="83b6f-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="83b6f-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="83b6f-105">Командлет [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) можно использовать для прямого вызова функций или методов ресурса DSC (функций `Get-TargetResource`, `Set-TargetResource` и `Test-TargetResource` ресурса на основе MOF-файла или методов **Get**, **Set** и **Test** ресурса на основе класса).</span><span class="sxs-lookup"><span data-stu-id="83b6f-105">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get**, **Set**, and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="83b6f-106">Этот командлет могут использовать сторонние разработчики, которым требуется использовать ресурсы DSC, кроме того, он удобен для разработки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83b6f-106">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="83b6f-107">В PowerShell 7.0 и более поздних версий `Invoke-DscResource` больше не поддерживает вызов ресурсов DSC WMI.</span><span class="sxs-lookup"><span data-stu-id="83b6f-107">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="83b6f-108">Сюда входят ресурсы **файл** и **журнал** в **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="83b6f-108">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="83b6f-109">Командлет обычно используется в сочетании со свойством метаконфигурации `refreshMode = 'Disabled'`, однако он доступен независимо от значения **refreshMode**.</span><span class="sxs-lookup"><span data-stu-id="83b6f-109">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="83b6f-110">При вызове командлета `Invoke-DscResource` указать, какой метод или функцию необходимо вызвать, можно с помощью параметра **Method**.</span><span class="sxs-lookup"><span data-stu-id="83b6f-110">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="83b6f-111">Свойства ресурса указываются путем передачи хэш-таблицы в качестве значения параметра **Property**.</span><span class="sxs-lookup"><span data-stu-id="83b6f-111">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="83b6f-112">Ниже приведены примеры прямого вызова методов ресурсов:</span><span class="sxs-lookup"><span data-stu-id="83b6f-112">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="83b6f-113">Проверка наличия файла</span><span class="sxs-lookup"><span data-stu-id="83b6f-113">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="83b6f-114">Тестирование наличия файла</span><span class="sxs-lookup"><span data-stu-id="83b6f-114">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="83b6f-115">Получение содержимого файла</span><span class="sxs-lookup"><span data-stu-id="83b6f-115">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

>[!NOTE]
> <span data-ttu-id="83b6f-116">Прямой вызов методов составного ресурса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83b6f-116">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="83b6f-117">Вместо этого вызывайте методы базовых ресурсов, входящих в составной ресурс.</span><span class="sxs-lookup"><span data-stu-id="83b6f-117">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="83b6f-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="83b6f-118">See Also</span></span>

- [<span data-ttu-id="83b6f-119">Написание пользовательских ресурсов DSC с использованием MOF</span><span class="sxs-lookup"><span data-stu-id="83b6f-119">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="83b6f-120">Написание пользовательских ресурсов DSC с использованием классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="83b6f-120">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="83b6f-121">Отладка ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="83b6f-121">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
