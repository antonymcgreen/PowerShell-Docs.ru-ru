---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Archive в DSC
ms.openlocfilehash: cbe32012c2035fb3e145bd06fadd73cdba93fd3e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463794"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="71204-103">Ресурс Archive в DSC</span><span class="sxs-lookup"><span data-stu-id="71204-103">DSC Archive Resource</span></span>

> <span data-ttu-id="71204-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="71204-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="71204-105">Ресурс Archive в DSC Windows PowerShell предоставляет механизм распаковки файлов архивов (ZIP) в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="71204-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="71204-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71204-106">Syntax</span></span>

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="71204-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="71204-107">Properties</span></span>

|<span data-ttu-id="71204-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="71204-108">Property</span></span> |<span data-ttu-id="71204-109">Описание</span><span class="sxs-lookup"><span data-stu-id="71204-109">Description</span></span> |
|---|---|
| <span data-ttu-id="71204-110">Назначение</span><span class="sxs-lookup"><span data-stu-id="71204-110">Destination</span></span> | <span data-ttu-id="71204-111">Указывает, куда будет извлечено содержимое архива.</span><span class="sxs-lookup"><span data-stu-id="71204-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span> |
| <span data-ttu-id="71204-112">путь</span><span class="sxs-lookup"><span data-stu-id="71204-112">Path</span></span> | <span data-ttu-id="71204-113">Указывает исходный путь для файла архива.</span><span class="sxs-lookup"><span data-stu-id="71204-113">Specifies the source path of the archive file.</span></span> |
| <span data-ttu-id="71204-114">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="71204-114">Checksum</span></span> | <span data-ttu-id="71204-115">Определяет тип проверки пары файлов на идентичность.</span><span class="sxs-lookup"><span data-stu-id="71204-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="71204-116">Если свойство **Checksum** не задано, для сравнения используется только имя файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="71204-116">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="71204-117">Допустимые значения: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span><span class="sxs-lookup"><span data-stu-id="71204-117">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> <span data-ttu-id="71204-118">Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="71204-118">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> |
| <span data-ttu-id="71204-119">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="71204-119">Credential</span></span> | <span data-ttu-id="71204-120">Учетные данные учетной записи пользователя с разрешениями на доступ к указанному пути и назначению архива, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="71204-120">The credential of a user account with permissions to access the specified archive path and destination if needed.</span></span> |
| <span data-ttu-id="71204-121">Force</span><span class="sxs-lookup"><span data-stu-id="71204-121">Force</span></span> | <span data-ttu-id="71204-122">Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку.</span><span class="sxs-lookup"><span data-stu-id="71204-122">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="71204-123">Свойство **Force** позволяет переопределять такие ошибки.</span><span class="sxs-lookup"><span data-stu-id="71204-123">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="71204-124">Значение по умолчанию равно **False**.</span><span class="sxs-lookup"><span data-stu-id="71204-124">The default value is **False**.</span></span> |
| <span data-ttu-id="71204-125">Проверить</span><span class="sxs-lookup"><span data-stu-id="71204-125">Validate</span></span>| <span data-ttu-id="71204-126">Проверяет соответствие архива и подписи, используя свойство **Checksum**.</span><span class="sxs-lookup"><span data-stu-id="71204-126">Uses the **Checksum** property to determine if the archive matches the signature.</span></span> <span data-ttu-id="71204-127">Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="71204-127">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> <span data-ttu-id="71204-128">Если свойство **Validate** указано без свойства **Checksum**, по умолчанию для **Checksum** используется значение _SHA-256_.</span><span class="sxs-lookup"><span data-stu-id="71204-128">If you specify **Validate** without **Checksum**, a _SHA-256_ **Checksum** is used by default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="71204-129">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="71204-129">Common properties</span></span>

|<span data-ttu-id="71204-130">Свойство</span><span class="sxs-lookup"><span data-stu-id="71204-130">Property</span></span> |<span data-ttu-id="71204-131">Описание</span><span class="sxs-lookup"><span data-stu-id="71204-131">Description</span></span> |
|---|---|
|<span data-ttu-id="71204-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="71204-132">DependsOn</span></span> |<span data-ttu-id="71204-133">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="71204-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="71204-134">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="71204-134">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="71204-135">Ensure</span><span class="sxs-lookup"><span data-stu-id="71204-135">Ensure</span></span> |<span data-ttu-id="71204-136">Указывает необходимость проверки того, существует ли содержимое архива в **папке назначения**.</span><span class="sxs-lookup"><span data-stu-id="71204-136">Determines whether to check if the content of the archive exists at the **Destination**.</span></span> <span data-ttu-id="71204-137">Чтобы убедиться, что содержимое существует, укажите для этого свойства значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="71204-137">Set this property to **Present** to ensure the contents exist.</span></span> <span data-ttu-id="71204-138">Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="71204-138">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="71204-139">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="71204-139">The default value is **Present**.</span></span> |
|<span data-ttu-id="71204-140">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="71204-140">PsDscRunAsCredential</span></span> |<span data-ttu-id="71204-141">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="71204-141">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="71204-142">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="71204-142">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="71204-143">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="71204-143">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="71204-144">Пример</span><span class="sxs-lookup"><span data-stu-id="71204-144">Example</span></span>

<span data-ttu-id="71204-145">В следующем примере показано, как использовать ресурс Archive, чтобы убедиться, что содержимое архивного файла с именем `Test.zip` существует, извлекается в указанную папку и авторизовано.</span><span class="sxs-lookup"><span data-stu-id="71204-145">The following example shows how to use the Archive resource to ensure that the contents of an archive file called `Test.zip` exist and are extracted at a given destination using and authorized.</span></span>

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
