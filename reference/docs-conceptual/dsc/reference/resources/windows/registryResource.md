---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс Registry в DSC
description: Ресурс Registry в DSC
ms.openlocfilehash: 075f64abffb429b83958d859b0328b4eeec4cee6
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142503"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="268fa-103">Ресурс Registry в DSC</span><span class="sxs-lookup"><span data-stu-id="268fa-103">DSC Registry Resource</span></span>

> <span data-ttu-id="268fa-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="268fa-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="268fa-105">Ресурс **Registry** в DSC Windows PowerShell предоставляет механизм управления разделами и значениями реестра на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="268fa-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="268fa-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="268fa-106">Syntax</span></span>

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="268fa-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="268fa-107">Properties</span></span>

|<span data-ttu-id="268fa-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="268fa-108">Property</span></span> |<span data-ttu-id="268fa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="268fa-109">Description</span></span> |
|---|---|
|<span data-ttu-id="268fa-110">Клавиши</span><span class="sxs-lookup"><span data-stu-id="268fa-110">Key</span></span> |<span data-ttu-id="268fa-111">Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="268fa-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="268fa-112">Этот путь должен включать куст.</span><span class="sxs-lookup"><span data-stu-id="268fa-112">This path must include the hive.</span></span> |
|<span data-ttu-id="268fa-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="268fa-113">ValueName</span></span> |<span data-ttu-id="268fa-114">Указывает имя значения реестра.</span><span class="sxs-lookup"><span data-stu-id="268fa-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="268fa-115">Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая **ValueType** или **ValueData** .</span><span class="sxs-lookup"><span data-stu-id="268fa-115">To add or remove a registry key, specify this property as an empty string without specifying **ValueType** or **ValueData** .</span></span> <span data-ttu-id="268fa-116">Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав **ValueType** или **ValueData** .</span><span class="sxs-lookup"><span data-stu-id="268fa-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying **ValueType** or **ValueData** .</span></span> |
|<span data-ttu-id="268fa-117">Force</span><span class="sxs-lookup"><span data-stu-id="268fa-117">Force</span></span> |<span data-ttu-id="268fa-118">Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением.</span><span class="sxs-lookup"><span data-stu-id="268fa-118">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="268fa-119">При удалении раздела реестра с подразделами необходимо выбрать `$true`.</span><span class="sxs-lookup"><span data-stu-id="268fa-119">If deleting a registry key with subkeys, this needs to be `$true`.</span></span> |
|<span data-ttu-id="268fa-120">Hex</span><span class="sxs-lookup"><span data-stu-id="268fa-120">Hex</span></span> |<span data-ttu-id="268fa-121">Указывает, будут ли данные выражены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="268fa-121">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="268fa-122">Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="268fa-122">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="268fa-123">Недопустимо для других типов.</span><span class="sxs-lookup"><span data-stu-id="268fa-123">Not valid for other types.</span></span> <span data-ttu-id="268fa-124">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="268fa-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="268fa-125">ValueData</span><span class="sxs-lookup"><span data-stu-id="268fa-125">ValueData</span></span> |<span data-ttu-id="268fa-126">Данные для значения реестра.</span><span class="sxs-lookup"><span data-stu-id="268fa-126">The data for the registry value.</span></span> |
|<span data-ttu-id="268fa-127">ValueType</span><span class="sxs-lookup"><span data-stu-id="268fa-127">ValueType</span></span> |<span data-ttu-id="268fa-128">Указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="268fa-128">Indicates the type of the value.</span></span> <span data-ttu-id="268fa-129">Поддерживаемые типы: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-разрядный REG_DWORD), **Qword** (64-разрядный REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ).</span><span class="sxs-lookup"><span data-stu-id="268fa-129">The supported types are: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-bit REG_DWORD), **Qword** (64-bit REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ).</span></span> |

## <a name="common-properties"></a><span data-ttu-id="268fa-130">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="268fa-130">Common properties</span></span>

|<span data-ttu-id="268fa-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="268fa-131">Property</span></span> |<span data-ttu-id="268fa-132">Описание</span><span class="sxs-lookup"><span data-stu-id="268fa-132">Description</span></span> |
|---|---|
|<span data-ttu-id="268fa-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="268fa-133">DependsOn</span></span> |<span data-ttu-id="268fa-134">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="268fa-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="268fa-135">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="268fa-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="268fa-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="268fa-136">Ensure</span></span> |<span data-ttu-id="268fa-137">Указывает, существует ли ключ и значение.</span><span class="sxs-lookup"><span data-stu-id="268fa-137">Indicates if the key and value exist.</span></span> <span data-ttu-id="268fa-138">Чтобы гарантировать их существование, укажите для этого свойства значение **Present** .</span><span class="sxs-lookup"><span data-stu-id="268fa-138">To ensure that they do, set this property to **Present** .</span></span> <span data-ttu-id="268fa-139">Чтобы они не существовали, укажите для этого свойства значение **Absent** .</span><span class="sxs-lookup"><span data-stu-id="268fa-139">To ensure that they do not exist, set the property to **Absent** .</span></span> <span data-ttu-id="268fa-140">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="268fa-140">The default value is **Present** .</span></span> |
|<span data-ttu-id="268fa-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="268fa-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="268fa-142">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="268fa-142">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="268fa-143">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="268fa-143">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="268fa-144">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="268fa-144">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="examples"></a><span data-ttu-id="268fa-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="268fa-145">Examples</span></span>

### <a name="example-1-ensure-specified-value-and-data-under-specified-registry-key"></a><span data-ttu-id="268fa-146">Пример 1: Проверка того, что текущие значение и данные указаны в соответствующем разделе реестра</span><span class="sxs-lookup"><span data-stu-id="268fa-146">Example 1: Ensure specified Value and Data under specified registry key</span></span>

<span data-ttu-id="268fa-147">В этом примере значение реестра TestValue в разделе с именем ExampleKey1 содержится в кусте `HKEY\_LOCAL\_MACHINE` и содержит данные TestData.</span><span class="sxs-lookup"><span data-stu-id="268fa-147">This example ensures that the registry value "TestValue" under a key named "ExampleKey1" is present in the `HKEY\_LOCAL\_MACHINE` hive and has the data "TestData".</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey1"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

### <a name="example-2-ensure-specified-registry-key-exists"></a><span data-ttu-id="268fa-148">Пример 2. Проверка того, что указанный раздел реестра существует</span><span class="sxs-lookup"><span data-stu-id="268fa-148">Example 2: Ensure specified registry key exists</span></span>

<span data-ttu-id="268fa-149">В этом примере ключ с именем ExampleKey2 содержится в кусте **HKEY\_LOCAL\_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="268fa-149">This example ensures that a key named "ExampleKey2" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey2"
        ValueName   = ""
    }
}
```

> [!NOTE]
> <span data-ttu-id="268fa-150">Для изменения настройки реестра в кусте `HKEY_CURRENT_USER` требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных.</span><span class="sxs-lookup"><span data-stu-id="268fa-150">Changing a registry setting in the `HKEY_CURRENT_USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="268fa-151">Вы можете использовать свойство **PsDscRunAsCredential** , чтобы указать учетные данные пользователя для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="268fa-151">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="268fa-152">Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](../../../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="268fa-152">For an example, see [Running DSC with user credentials](../../../configurations/runAsUser.md).</span></span>
