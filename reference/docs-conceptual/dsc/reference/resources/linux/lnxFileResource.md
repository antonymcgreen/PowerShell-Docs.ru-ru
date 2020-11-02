---
ms.date: 07/17/2020
ms.topic: reference
title: Ресурс nxFile в DSC для Linux
description: Ресурс nxFile в DSC для Linux
ms.openlocfilehash: 6ec2d8201f3594879b781fe04e32a28cc87ba934
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644745"
---
# <a name="dsc-for-linux-nxfile-resource"></a><span data-ttu-id="4f255-103">Ресурс nxFile в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="4f255-103">DSC for Linux nxFile Resource</span></span>

<span data-ttu-id="4f255-104">Ресурс **nxFile** в настройке требуемого состояния PowerShell предоставляет механизм управления файлами и каталогами на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="4f255-104">The **nxFile** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and directories on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f255-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f255-105">Syntax</span></span>

```Syntax
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage | ignore } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="4f255-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="4f255-106">Properties</span></span>

|<span data-ttu-id="4f255-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="4f255-107">Property</span></span> |<span data-ttu-id="4f255-108">Description</span><span class="sxs-lookup"><span data-stu-id="4f255-108">Description</span></span> |
|---|---|
|<span data-ttu-id="4f255-109">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="4f255-109">DestinationPath</span></span> |<span data-ttu-id="4f255-110">Указывает, в каком расположении нужно проверить состояние файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="4f255-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="4f255-111">SourcePath</span><span class="sxs-lookup"><span data-stu-id="4f255-111">SourcePath</span></span> |<span data-ttu-id="4f255-112">Указывает, откуда нужно скопировать файл или папку.</span><span class="sxs-lookup"><span data-stu-id="4f255-112">Specifies the path from which to copy the file or folder resource.</span></span> <span data-ttu-id="4f255-113">Этот может быть локальный путь или URL-адрес `http/https/ftp`.</span><span class="sxs-lookup"><span data-stu-id="4f255-113">This path may be a local path, or an `http/https/ftp` URL.</span></span> <span data-ttu-id="4f255-114">Удаленные URL-адреса `http/https/ftp` поддерживаются, только если для свойства **Type** выбрано значение **file** .</span><span class="sxs-lookup"><span data-stu-id="4f255-114">Remote `http/https/ftp` URLs are only supported when the value of the **Type** property is **file** .</span></span> |
|<span data-ttu-id="4f255-115">Тип</span><span class="sxs-lookup"><span data-stu-id="4f255-115">Type</span></span> |<span data-ttu-id="4f255-116">Указывает, является ли настраиваемый ресурс каталогом или файлом.</span><span class="sxs-lookup"><span data-stu-id="4f255-116">Specifies whether the resource being configured is a directory or a file.</span></span> <span data-ttu-id="4f255-117">Если выбрано значение **directory** , то ресурс является каталогом,</span><span class="sxs-lookup"><span data-stu-id="4f255-117">Set this property to **directory** to indicate that the resource is a directory.</span></span> <span data-ttu-id="4f255-118">а если значение **file**  — файлом.</span><span class="sxs-lookup"><span data-stu-id="4f255-118">Set it to **file** to indicate that the resource is a file.</span></span> <span data-ttu-id="4f255-119">Значение по умолчанию — **file** .</span><span class="sxs-lookup"><span data-stu-id="4f255-119">The default value is **file** .</span></span> |
|<span data-ttu-id="4f255-120">Содержимое</span><span class="sxs-lookup"><span data-stu-id="4f255-120">Contents</span></span> |<span data-ttu-id="4f255-121">Указывает содержимое файла, например определенную строку.</span><span class="sxs-lookup"><span data-stu-id="4f255-121">Specifies the contents of a file, such as a particular string.</span></span> |
|<span data-ttu-id="4f255-122">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="4f255-122">Checksum</span></span> |<span data-ttu-id="4f255-123">Определяет тип проверки пары файлов на идентичность.</span><span class="sxs-lookup"><span data-stu-id="4f255-123">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="4f255-124">Если свойство **Checksum** не задано, для сравнения используется только имя файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="4f255-124">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="4f255-125">Значения: **ctime** , **mtime** или **md5** .</span><span class="sxs-lookup"><span data-stu-id="4f255-125">Values are: **ctime** , **mtime** , or **md5** .</span></span> |
|<span data-ttu-id="4f255-126">Recurse</span><span class="sxs-lookup"><span data-stu-id="4f255-126">Recurse</span></span> |<span data-ttu-id="4f255-127">Указывает, используются ли вложенные папки.</span><span class="sxs-lookup"><span data-stu-id="4f255-127">Indicates if subdirectories are included.</span></span> <span data-ttu-id="4f255-128">Если свойство имеет значение `$true`, вложенные папки включаются.</span><span class="sxs-lookup"><span data-stu-id="4f255-128">Set this property to `$true` to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="4f255-129">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="4f255-129">The default is `$false`.</span></span> <span data-ttu-id="4f255-130">Это свойство можно использовать только в том случае, если свойство **Type** имеет значение **directory** .</span><span class="sxs-lookup"><span data-stu-id="4f255-130">This property is only valid when the **Type** property is set to **directory** .</span></span> |
|<span data-ttu-id="4f255-131">Force</span><span class="sxs-lookup"><span data-stu-id="4f255-131">Force</span></span> |<span data-ttu-id="4f255-132">Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку.</span><span class="sxs-lookup"><span data-stu-id="4f255-132">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="4f255-133">Свойство **Force** позволяет переопределять такие ошибки.</span><span class="sxs-lookup"><span data-stu-id="4f255-133">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="4f255-134">Значение по умолчанию — `$false`.</span><span class="sxs-lookup"><span data-stu-id="4f255-134">The default value is `$false`.</span></span> |
|<span data-ttu-id="4f255-135">Ссылки</span><span class="sxs-lookup"><span data-stu-id="4f255-135">Links</span></span> |<span data-ttu-id="4f255-136">Определяет желаемое поведение символических ссылок.</span><span class="sxs-lookup"><span data-stu-id="4f255-136">Specifies the desired behavior for symbolic links.</span></span> <span data-ttu-id="4f255-137">Если для свойства установлено значение **follow** , символические ссылки отслеживаются, а к целевым объектам применяются действия</span><span class="sxs-lookup"><span data-stu-id="4f255-137">Set this property to **follow** to follow symbolic links and act on the links target.</span></span> <span data-ttu-id="4f255-138">(например, копирование файла вместо ссылки).</span><span class="sxs-lookup"><span data-stu-id="4f255-138">For example, copy the file instead of the link.</span></span> <span data-ttu-id="4f255-139">Если установлено значение **manage** , действие применяется к ссылке</span><span class="sxs-lookup"><span data-stu-id="4f255-139">Set this property to **manage** to act on the link.</span></span> <span data-ttu-id="4f255-140">(например, копирование самой ссылки).</span><span class="sxs-lookup"><span data-stu-id="4f255-140">For example, copy the link itself.</span></span> <span data-ttu-id="4f255-141">Если установлено значение **ignore** , символические ссылки игнорируются.</span><span class="sxs-lookup"><span data-stu-id="4f255-141">Set this property to **ignore** to ignore symbolic links.</span></span> |
|<span data-ttu-id="4f255-142">Группа</span><span class="sxs-lookup"><span data-stu-id="4f255-142">Group</span></span> |<span data-ttu-id="4f255-143">Имя ресурса **Group**  — обладателя разрешений для файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="4f255-143">The name of the **Group** to have permissions to the file or directory.</span></span> |
|<span data-ttu-id="4f255-144">Режим</span><span class="sxs-lookup"><span data-stu-id="4f255-144">Mode</span></span> |<span data-ttu-id="4f255-145">Указывает нужные разрешения для ресурса в восьмеричной или символьной нотации</span><span class="sxs-lookup"><span data-stu-id="4f255-145">Specifies the desired permissions for the resource, in octal or symbolic notation.</span></span> <span data-ttu-id="4f255-146">(например, **777** или **rwxrwxrwx** ).</span><span class="sxs-lookup"><span data-stu-id="4f255-146">For example, **777** or **rwxrwxrwx** .</span></span> <span data-ttu-id="4f255-147">Если используется символьная нотация, не указывайте первый символ, обозначающий каталог или файл.</span><span class="sxs-lookup"><span data-stu-id="4f255-147">If using symbolic notation, do not provide the first character which indicates directory or file.</span></span> |
|<span data-ttu-id="4f255-148">Владелец</span><span class="sxs-lookup"><span data-stu-id="4f255-148">Owner</span></span> |<span data-ttu-id="4f255-149">Имя группы — владельца файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="4f255-149">The name of the group to own the file or directory.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4f255-150">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="4f255-150">Common properties</span></span>

|<span data-ttu-id="4f255-151">Свойство</span><span class="sxs-lookup"><span data-stu-id="4f255-151">Property</span></span> |<span data-ttu-id="4f255-152">Description</span><span class="sxs-lookup"><span data-stu-id="4f255-152">Description</span></span> |
|---|---|
|<span data-ttu-id="4f255-153">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4f255-153">DependsOn</span></span> |<span data-ttu-id="4f255-154">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="4f255-154">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4f255-155">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="4f255-155">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="4f255-156">Ensure</span><span class="sxs-lookup"><span data-stu-id="4f255-156">Ensure</span></span> |<span data-ttu-id="4f255-157">Определяет, нужно ли проверять существование файла.</span><span class="sxs-lookup"><span data-stu-id="4f255-157">Determines whether to check if the file exists.</span></span> <span data-ttu-id="4f255-158">Чтобы гарантировать, что файл существует, укажите для этого свойства значение **Present** .</span><span class="sxs-lookup"><span data-stu-id="4f255-158">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="4f255-159">Чтобы гарантировать, что файл не существует, укажите для этого свойства значение **Absent** .</span><span class="sxs-lookup"><span data-stu-id="4f255-159">Set it to **Absent** to ensure the file does not exist.</span></span> <span data-ttu-id="4f255-160">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="4f255-160">The default value is **Present** .</span></span> |

## <a name="additional-information"></a><span data-ttu-id="4f255-161">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4f255-161">Additional Information</span></span>

<span data-ttu-id="4f255-162">Linux и Windows используют разные символы разрыва строки в текстовых файлах по умолчанию, что может привести к непредвиденным результатам при настройке некоторых файлов на компьютере Linux с помощью **nxFile** .</span><span class="sxs-lookup"><span data-stu-id="4f255-162">Linux and Windows use different line break characters in text files by default, and this can cause unexpected results when configuring some files on a Linux computer with **nxFile** .</span></span> <span data-ttu-id="4f255-163">Избежать проблем из-за непредвиденных символов разрыва строки при работе с содержанием файла Linux можно разными способами:</span><span class="sxs-lookup"><span data-stu-id="4f255-163">There are multiple ways to manage the content of a Linux file while avoiding issues caused by unexpected line break characters:</span></span>

1. <span data-ttu-id="4f255-164">Копирование файла из удаленного источника (HTTP, HTTPS или FTP)</span><span class="sxs-lookup"><span data-stu-id="4f255-164">Copy the file from a remote source (http, https, or ftp)</span></span>

   <span data-ttu-id="4f255-165">Создайте файл с нужным содержанием на компьютере с Linux и поместите его на веб- или FTP-сервер, доступный для настраиваемого узла.</span><span class="sxs-lookup"><span data-stu-id="4f255-165">Create a file on Linux with the desired contents, and stage it on a web or ftp server accessible the node(s) you will configure.</span></span> <span data-ttu-id="4f255-166">Определите свойство **SourcePath** в ресурсе **nxFile** , указав URL-адрес файла на веб- или FTP-сервере.</span><span class="sxs-lookup"><span data-stu-id="4f255-166">Define the **SourcePath** property in the **nxFile** resource with the web or ftp URL to the file.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      nxFile resolvConf
      {
         SourcePath = "http://10.185.85.11/conf/resolv.conf"
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
      }
   }
   ```

1. <span data-ttu-id="4f255-167">Прочтите содержимое файла в сценарии PowerShell с помощью командлета [Get-Content](https://technet.microsoft.com/library/hh849787.aspx), настроив символ переноса строки Linux с помощью свойства **$OFS** .</span><span class="sxs-lookup"><span data-stu-id="4f255-167">Read the file contents in the PowerShell script with [Get-Content](https://technet.microsoft.com/library/hh849787.aspx) after setting the **$OFS** property to use the Linux line-break character.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      $OFS = "`n"
      $Contents = Get-Content C:\temp\resolv.conf

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = "$Contents"
      }
   }
   ```

1. <span data-ttu-id="4f255-168">Воспользуйтесь функцией PowerShell для замены символов разрыва строки в Windows на символы разрыва строки в Linux.</span><span class="sxs-lookup"><span data-stu-id="4f255-168">Use a PowerShell function to replace Windows line breaks with Linux line-break characters.</span></span>

   ```powershell
   Function LinuxString($inputStr){
      $outputStr = $inputStr.Replace("`r`n","`n")
      $outputStr += "`n"
      Return $outputStr
   }

   Import-DSCResource -Module nx

   Node $Node
   {
      $Contents = @'
   search contoso.com
   domain contoso.com
   nameserver 10.185.85.11
   '@
       $Contents = LinuxString $Contents

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = $Contents
      }
   }
   ```

## <a name="example"></a><span data-ttu-id="4f255-169">Пример</span><span class="sxs-lookup"><span data-stu-id="4f255-169">Example</span></span>

<span data-ttu-id="4f255-170">В следующем примере проверяется существование каталога `/opt/mydir` и файла с указанным содержимым в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="4f255-170">The following example ensures that the directory `/opt/mydir` exists, and that a file with specified contents exists this directory.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node {
    nxFile DirectoryExample
    {
        Ensure = "Present"
        DestinationPath = "/opt/mydir"
        Type = "Directory"
    }

    nxFile FileExample
    {
        Ensure = "Present"
        Destinationpath = "/opt/mydir/myfile"
        Contents=@"
#!/bin/bash`necho "hello world"`n
"@
        Mode = "755"
        DependsOn = "[nxFile]DirectoryExample"
    }
}
```
