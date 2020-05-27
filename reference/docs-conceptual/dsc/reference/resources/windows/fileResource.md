---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс File в DSC
ms.openlocfilehash: 54f4de9b3d337a6b9ad36c143eac70d5ef6b1c15
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560480"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="ff6d6-103">Ресурс File в DSC</span><span class="sxs-lookup"><span data-stu-id="ff6d6-103">DSC File Resource</span></span>

> <span data-ttu-id="ff6d6-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="ff6d6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="ff6d6-105">Ресурс **File** в DSC Windows PowerShell предоставляет механизм управления файлами и папками на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-105">The **File** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="ff6d6-106">Свойства **DestinationPath** и **SourcePath** должны быть доступны для целевого узла.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-106">**DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff6d6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff6d6-107">Syntax</span></span>

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="ff6d6-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="ff6d6-108">Properties</span></span>

|<span data-ttu-id="ff6d6-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="ff6d6-109">Property</span></span> |<span data-ttu-id="ff6d6-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ff6d6-110">Description</span></span> |
|---|---|
|<span data-ttu-id="ff6d6-111">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="ff6d6-111">DestinationPath</span></span> |<span data-ttu-id="ff6d6-112">Расположение на целевом узле, которое нужно проверить (**Ensure**) на наличие (**Present**) или отсутствие (**Absent**).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-112">The location, on the target node, you want to ensure is **Present** or **Absent** with **Ensure**.</span></span> |
|<span data-ttu-id="ff6d6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff6d6-113">Attributes</span></span> |<span data-ttu-id="ff6d6-114">Требуемое состояние атрибутов для целевого файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-114">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="ff6d6-115">Допустимые значения: _Archive_, _Hidden_, _ReadOnly_ и _System_.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-115">Valid values are _Archive_, _Hidden_, _ReadOnly_, and _System_.</span></span> |
|<span data-ttu-id="ff6d6-116">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="ff6d6-116">Checksum</span></span> |<span data-ttu-id="ff6d6-117">Тип контрольной суммы для использования при проверке двух файлов на идентичность.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-117">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="ff6d6-118">Допустимые значения: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-118">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> |
|<span data-ttu-id="ff6d6-119">Содержимое</span><span class="sxs-lookup"><span data-stu-id="ff6d6-119">Contents</span></span> |<span data-ttu-id="ff6d6-120">Допустимо только при использовании с типом **Type** **File**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-120">Only valid when used with **Type** **File**.</span></span> <span data-ttu-id="ff6d6-121">Указывает содержимое из целевого файла, которое нужно проверить (**Ensure**) на наличие (**Present**) или отсутствие (**Absent**).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-121">Indicates the contents to **Ensure** are **Present** or **Absent** from the targeted file.</span></span> |
|<span data-ttu-id="ff6d6-122">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="ff6d6-122">Credential</span></span> |<span data-ttu-id="ff6d6-123">Учетные данные, необходимые для доступа к ресурсам, например, к исходным файлам.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-123">The credentials that are required to access resources, such as source files.</span></span> |
|<span data-ttu-id="ff6d6-124">Force</span><span class="sxs-lookup"><span data-stu-id="ff6d6-124">Force</span></span> |<span data-ttu-id="ff6d6-125">Переопределяет операции доступа, которые вызывают ошибку (например, перезапись файла или удаление непустого каталога).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-125">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span> <span data-ttu-id="ff6d6-126">Значение по умолчанию: `$false`.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-126">Default value is `$false`.</span></span> |
|<span data-ttu-id="ff6d6-127">Recurse</span><span class="sxs-lookup"><span data-stu-id="ff6d6-127">Recurse</span></span> |<span data-ttu-id="ff6d6-128">Допустимо только при использовании с типом **Type** **Directory**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-128">Only valid when used with **Type** **Directory**.</span></span> <span data-ttu-id="ff6d6-129">Рекурсивно выполняет операции с состоянием во всех подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-129">Performs the state operation recursively to all subdirectories.</span></span> <span data-ttu-id="ff6d6-130">Значение по умолчанию: `$false`.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-130">Default value is `$false`.</span></span> |
|<span data-ttu-id="ff6d6-131">SourcePath</span><span class="sxs-lookup"><span data-stu-id="ff6d6-131">SourcePath</span></span> |<span data-ttu-id="ff6d6-132">Путь, откуда нужно скопировать ресурс файла или папки.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-132">The path from which to copy the file or folder resource.</span></span> |
|<span data-ttu-id="ff6d6-133">Тип</span><span class="sxs-lookup"><span data-stu-id="ff6d6-133">Type</span></span> |<span data-ttu-id="ff6d6-134">Тип настраиваемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-134">The type of resource being configured.</span></span> <span data-ttu-id="ff6d6-135">Допустимые значения: **Directory** и **File**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-135">Valid values are **Directory** and **File**.</span></span> <span data-ttu-id="ff6d6-136">Значение по умолчанию — **File**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-136">Default value is **File**.</span></span> |
|<span data-ttu-id="ff6d6-137">MatchSource</span><span class="sxs-lookup"><span data-stu-id="ff6d6-137">MatchSource</span></span> |<span data-ttu-id="ff6d6-138">Определяет, должен ли ресурс отслеживать новые файлы, добавленные в исходный каталог после исходной копии.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-138">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="ff6d6-139">Значение `$true` указывает, что после исходной копии все новые исходные файлы должны быть скопированы в место назначения.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-139">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="ff6d6-140">Если задано значение `$false`, ресурс кэширует содержимое исходного каталога и игнорирует любые файлы, добавленные после исходной копии.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-140">If set to `$false`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span> <span data-ttu-id="ff6d6-141">Значение по умолчанию: `$false`.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-141">Default value is `$false`.</span></span> |

> [!WARNING]
> <span data-ttu-id="ff6d6-142">Если не указать значение для свойства **Credential** или **PSRunAsCredential**, ресурс будет использовать учетную запись компьютера целевого узла для доступа к свойству **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-142">If you do not specify a value for **Credential** or **PSRunAsCredential**, the resource will use the computer account of the target node to access the **SourcePath**.</span></span> <span data-ttu-id="ff6d6-143">Если **SourcePath** представляет собой общий ресурс UNC, это может привести к ошибке отказа в доступе.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-143">When the **SourcePath** is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="ff6d6-144">Убедитесь, что разрешения установлены соответственно, или используйте свойства **Credential** или **PSRunAsCredential**, чтобы указать учетную запись, которая должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-144">Please ensure your permissions are set accordingly, or use the **Credential** or **PSRunAsCredential** properties to specify the account that should be used.</span></span>

## <a name="common-properties"></a><span data-ttu-id="ff6d6-145">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="ff6d6-145">Common properties</span></span>

|<span data-ttu-id="ff6d6-146">Свойство</span><span class="sxs-lookup"><span data-stu-id="ff6d6-146">Property</span></span> |<span data-ttu-id="ff6d6-147">Описание</span><span class="sxs-lookup"><span data-stu-id="ff6d6-147">Description</span></span> |
|---|---|
|<span data-ttu-id="ff6d6-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ff6d6-148">DependsOn</span></span> |<span data-ttu-id="ff6d6-149">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ff6d6-150">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ff6d6-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="ff6d6-151">Ensure</span></span> |<span data-ttu-id="ff6d6-152">Определяет, должны ли существовать файл и **Contents** в **Destination**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-152">Determines whether the file and **Contents** at the **Destination** should exist or not.</span></span> <span data-ttu-id="ff6d6-153">Чтобы гарантировать, что файл существует, укажите для этого свойства значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-153">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="ff6d6-154">Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-154">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="ff6d6-155">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-155">The default value is **Present**.</span></span> |
|<span data-ttu-id="ff6d6-156">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ff6d6-156">PsDscRunAsCredential</span></span> |<span data-ttu-id="ff6d6-157">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-157">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="ff6d6-158">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-158">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="ff6d6-159">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-159">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="ff6d6-160">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ff6d6-160">Additional information</span></span>

- <span data-ttu-id="ff6d6-161">При указании только свойства **DestinationPath** ресурс проверяет, что путь существует (**Present**) или не существует (**Absent**).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-161">When you only specify a **DestinationPath**, the resource ensures that the path exists if **Present** or does not exist if **Absent**.</span></span>
- <span data-ttu-id="ff6d6-162">При указании свойств **SourcePath** и **DestinationPath**, для которых свойство **Type** имеет значение **Directory**, ресурс копирует исходный каталог в путь назначения.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-162">When you specify a **SourcePath** and a **DestinationPath** with a **Type** value of **Directory**, the resource copies source directory to the destination path.</span></span> <span data-ttu-id="ff6d6-163">Свойства **Recurse**, **Force** и **MatchSource** изменяют тип выполняемой операции копирования, а свойство **Credential** определяет, какую учетную запись следует использовать для доступа к исходному каталогу.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-163">The properties **Recurse**, **Force**, and **MatchSource** change the type of copy operation performed, while **Credential** determines which account to use to access the source directory.</span></span>
- <span data-ttu-id="ff6d6-164">Если вы указали значение **ReadOnly** для свойства **Attributes** вместе с **DestinationPath**, **Ensure** и **Present** создадут указанный путь, а **Contents** зададут содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-164">If you specified a value of **ReadOnly** for the **Attributes** property alongside a **DestinationPath**, **Ensure** **Present** would create the path specified, while **Contents** would set the contents of the file.</span></span> <span data-ttu-id="ff6d6-165">Задание **Ensure** **Absent** приведет к пропуску свойства **Attributes** полностью и удалит любой файл по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-165">An **Ensure** **Absent** setting would ignore the **Attributes** property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="ff6d6-166">Пример</span><span class="sxs-lookup"><span data-stu-id="ff6d6-166">Example</span></span>

<span data-ttu-id="ff6d6-167">В следующем примере копируется каталог и его подкаталоги с опрашиваемого сервера на целевой узел, использующий ресурс File.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-167">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="ff6d6-168">Если операция прошла успешно, ресурс Log записывает в журнал событий сообщение с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-168">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="ff6d6-169">Исходный каталог — это UNC-путь (`\\PullServer\DemoSource`), к которому предоставлен общий доступ с опрашиваемого сервера.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-169">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="ff6d6-170">Свойство **Recurse** гарантирует, что также копируются все подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-170">The **Recurse** property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff6d6-171">LCM на целевом узле выполняется в контексте локальной системной учетной записи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-171">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="ff6d6-172">Чтобы предоставить доступ к свойству **SourcePath**, задайте соответствующие разрешения для учетной записи компьютера целевого узла.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-172">To grant access to the **SourcePath**, give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="ff6d6-173">Свойства **Credential** и **PSDSCRunAsCredential** изменяют контекст, который LCM использует для доступа к свойству **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-173">The **Credential** and **PSDSCRunAsCredential** both change the context the LCM uses to access the **SourcePath**.</span></span> <span data-ttu-id="ff6d6-174">Вам по-прежнему необходимо предоставить доступ к учетной записи, которая будет использоваться для доступа к свойству **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="ff6d6-174">You still need to grant access to the account that will be used to access the **SourcePath**.</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

<span data-ttu-id="ff6d6-175">Дополнительные сведения об использовании свойства **Credentials** в DSC см. в разделе [Use Credentials with DSC Resources](../../../configurations/runAsUser.md) (Использование учетных данных с ресурсами DSC) или [Credentials Options in Configuration Data](../../../configurations/configDataCredentials.md) (Параметры учетных данных в данных конфигурации).</span><span class="sxs-lookup"><span data-stu-id="ff6d6-175">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>
