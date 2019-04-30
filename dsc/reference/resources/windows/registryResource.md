---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Registry в DSC
ms.openlocfilehash: e0ae1a4a27edc08c4e6ccd47786426917eb1ccb4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076962"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="e3d5c-103">Ресурс Registry в DSC</span><span class="sxs-lookup"><span data-stu-id="e3d5c-103">DSC Registry Resource</span></span>

<span data-ttu-id="e3d5c-104">_Применяется к: Windows PowerShell 4.0, Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="e3d5c-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="e3d5c-105">Ресурс **Registry** в DSC Windows PowerShell предоставляет механизм управления разделами и значениями реестра на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3d5c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3d5c-106">Syntax</span></span>

```
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Ensure = [string] { Present | Absent }  ]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ DependsOn = [string[]] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
}
```

## <a name="properties"></a><span data-ttu-id="e3d5c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e3d5c-107">Properties</span></span>

| <span data-ttu-id="e3d5c-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="e3d5c-108">Property</span></span> | <span data-ttu-id="e3d5c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3d5c-109">Description</span></span> |
| --- | --- |
| <span data-ttu-id="e3d5c-110">Клавиши</span><span class="sxs-lookup"><span data-stu-id="e3d5c-110">Key</span></span>| <span data-ttu-id="e3d5c-111">Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="e3d5c-112">Этот путь должен включать куст.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-112">This path must include the hive.</span></span>|
| <span data-ttu-id="e3d5c-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="e3d5c-113">ValueName</span></span>| <span data-ttu-id="e3d5c-114">Указывает имя значения реестра.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="e3d5c-115">Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая ValueType или ValueData.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-115">To add or remove a registry key, specify this property as an empty string without specifying ValueType or ValueData.</span></span> <span data-ttu-id="e3d5c-116">Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав ValueType или ValueData.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying ValueType or ValueData.</span></span>|
| <span data-ttu-id="e3d5c-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="e3d5c-117">Ensure</span></span>| <span data-ttu-id="e3d5c-118">Указывает, существует ли ключ и значение.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-118">Indicates if the key and value exist.</span></span> <span data-ttu-id="e3d5c-119">Для этого укажите для этого свойства значение Present.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-119">To ensure that they do, set this property to "Present".</span></span> <span data-ttu-id="e3d5c-120">Чтобы они не существовали, укажите для этого свойства значение Absent.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-120">To ensure that they do not exist, set the property to "Absent".</span></span> <span data-ttu-id="e3d5c-121">Значение по умолчанию — Present.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-121">The default value is "Present".</span></span>|
| <span data-ttu-id="e3d5c-122">Force</span><span class="sxs-lookup"><span data-stu-id="e3d5c-122">Force</span></span>| <span data-ttu-id="e3d5c-123">Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-123">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="e3d5c-124">При удалении раздела реестра с подразделами необходимо выбрать **$true**</span><span class="sxs-lookup"><span data-stu-id="e3d5c-124">If deleting a registry key with subkeys, this needs to be **$true**</span></span> |
| <span data-ttu-id="e3d5c-125">Hex</span><span class="sxs-lookup"><span data-stu-id="e3d5c-125">Hex</span></span>| <span data-ttu-id="e3d5c-126">Указывает, будут ли данные выражены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-126">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="e3d5c-127">Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-127">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="e3d5c-128">Недопустимо для других типов.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-128">Not valid for other types.</span></span> <span data-ttu-id="e3d5c-129">Значение по умолчанию — **$false**.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-129">The default value is **$false**.</span></span>|
| <span data-ttu-id="e3d5c-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e3d5c-130">DependsOn</span></span>| <span data-ttu-id="e3d5c-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e3d5c-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-132">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="e3d5c-133">ValueData</span><span class="sxs-lookup"><span data-stu-id="e3d5c-133">ValueData</span></span>| <span data-ttu-id="e3d5c-134">Данные для значения реестра.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-134">The data for the registry value.</span></span>|
| <span data-ttu-id="e3d5c-135">ValueType</span><span class="sxs-lookup"><span data-stu-id="e3d5c-135">ValueType</span></span>| <span data-ttu-id="e3d5c-136">Указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-136">Indicates the type of the value.</span></span> <span data-ttu-id="e3d5c-137">Поддерживаемые типы: строковый (REG_SZ), двоичный (REG-BINARY), Dword — 32-битный (REG_DWORD), Qword — 64-битный (REG_QWORD), многостроковый (REG_MULTI_SZ), расширяемый строковый (REG_EXPAND_SZ).</span><span class="sxs-lookup"><span data-stu-id="e3d5c-137">The supported types are: String (REG_SZ), Binary (REG-BINARY), Dword 32-bit (REG_DWORD), Qword 64-bit (REG_QWORD), Multi-string (REG_MULTI_SZ), Expandable string (REG_EXPAND_SZ)</span></span> |

## <a name="example"></a><span data-ttu-id="e3d5c-138">Пример</span><span class="sxs-lookup"><span data-stu-id="e3d5c-138">Example</span></span>

<span data-ttu-id="e3d5c-139">В этом примере гарантируется, что ключ с именем ExampleKey присутствует в кусте **HKEY\_LOCAL\_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-139">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> <span data-ttu-id="e3d5c-140">Для изменения настройки реестра в кусте `HKEY\CURRENT\USER` требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-140">Changing a registry setting in the `HKEY\CURRENT\USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="e3d5c-141">Вы можете использовать свойство **PsDscRunAsCredential**, чтобы указать учетные данные пользователя для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e3d5c-141">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="e3d5c-142">Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](../../../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="e3d5c-142">For an example, see [Running DSC with user credentials](../../../configurations/runAsUser.md).</span></span>
