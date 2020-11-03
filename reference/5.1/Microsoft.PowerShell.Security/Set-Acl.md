---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: fd3f603a3aa94845285411977c07370d0a777622
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227770"
---
# <span data-ttu-id="373c0-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="373c0-103">Set-Acl</span></span>

## <span data-ttu-id="373c0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="373c0-104">SYNOPSIS</span></span>
<span data-ttu-id="373c0-105">Изменяет дескриптор безопасности указанного элемента, например файла или раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="373c0-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="373c0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="373c0-106">SYNTAX</span></span>

### <span data-ttu-id="373c0-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="373c0-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>] [-ClearCentralAccessPolicy]
 [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="373c0-108">бинпутобжект</span><span class="sxs-lookup"><span data-stu-id="373c0-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="373c0-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="373c0-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>]
 [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="373c0-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="373c0-110">DESCRIPTION</span></span>

<span data-ttu-id="373c0-111">`Set-Acl`Командлет изменяет дескриптор безопасности указанного элемента, например файла или раздела реестра, для сопоставления значений в указанном дескрипторе безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="373c0-112">Для использования `Set-Acl` используйте параметр **path** или **InputObject** , чтобы указать элемент, дескриптор безопасности которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="373c0-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="373c0-113">Затем с помощью параметра **AclObject** или **SecurityDescriptor** предоставьте дескриптор безопасности, содержащий значения, которые необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="373c0-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="373c0-114">`Set-Acl` Применяет указанный дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="373c0-115">Он использует значение параметра **AclObject** как модель и изменяет значения в дескрипторе безопасности элемента в соответствии со значениями параметра **AclObject** .</span><span class="sxs-lookup"><span data-stu-id="373c0-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="373c0-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="373c0-116">EXAMPLES</span></span>

### <span data-ttu-id="373c0-117">Пример 1. копирование дескриптора безопасности из одного файла в другой</span><span class="sxs-lookup"><span data-stu-id="373c0-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="373c0-118">Эти команды копируют значения из дескриптора безопасности файла Dog.txt в дескриптор безопасности файла Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="373c0-119">После выполнения команд дескрипторы безопасности файлов Dog.txt и Cat.txt становятся идентичны.</span><span class="sxs-lookup"><span data-stu-id="373c0-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="373c0-120">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="373c0-121">Оператор присваивания ( `=` ) сохраняет дескриптор безопасности в значении переменной $DogACL.</span><span class="sxs-lookup"><span data-stu-id="373c0-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="373c0-122">Вторая команда использует `Set-Acl` , чтобы изменить значения в списке ACL для Cat.txt на значения в `$DogACL` .</span><span class="sxs-lookup"><span data-stu-id="373c0-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="373c0-123">Значение параметра **Path** представляет сбой путь к файлу Cat.txt,</span><span class="sxs-lookup"><span data-stu-id="373c0-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="373c0-124">Значением параметра **аклобжект** является ACL модели, в данном случае acl для Dog.txt, сохраненный в `$DogACL` переменной.</span><span class="sxs-lookup"><span data-stu-id="373c0-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="373c0-125">Пример 2. Использование оператора конвейера для передачи дескриптора</span><span class="sxs-lookup"><span data-stu-id="373c0-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="373c0-126">Эта команда почти аналогична команде в предыдущем примере, за исключением того, что она использует конвейерный оператор ( `|` ) для отправки дескриптора безопасности из `Get-Acl` команды в `Set-Acl` команду.</span><span class="sxs-lookup"><span data-stu-id="373c0-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="373c0-127">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="373c0-128">Оператор конвейера ( `|` ) передает объект, представляющий дескриптор безопасности Dog.txt для `Set-Acl` командлета.</span><span class="sxs-lookup"><span data-stu-id="373c0-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="373c0-129">Вторая команда использует `Set-Acl` для применения дескриптора безопасности Dog.txt к Cat.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="373c0-130">После выполнения команды списки контроля доступа к файлам Dog.txt и Cat.txt становятся идентичны.</span><span class="sxs-lookup"><span data-stu-id="373c0-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="373c0-131">Пример 3. применение дескриптора безопасности к нескольким файлам</span><span class="sxs-lookup"><span data-stu-id="373c0-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="373c0-132">Эти команды применяют дескрипторы безопасности в файле File0.txt ко всем текстовым файлам в `C:\Temp` каталоге и всем его подкаталогам.</span><span class="sxs-lookup"><span data-stu-id="373c0-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="373c0-133">Первая команда получает дескриптор безопасности файла File0.txt в текущем каталоге и использует оператор присваивания ( `=` ), чтобы сохранить его в `$NewACL` переменной.</span><span class="sxs-lookup"><span data-stu-id="373c0-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="373c0-134">Первая команда в конвейере использует командлет Get-ChildItem для получения всех текстовых файлов в `C:\Temp` каталоге.</span><span class="sxs-lookup"><span data-stu-id="373c0-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="373c0-135">Параметр **рекурсии** расширяет команду до всех подкаталогов `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="373c0-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="373c0-136">Параметр **include** ограничивает файлы, полученные с помощью `.txt` расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="373c0-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="373c0-137">Параметр **Force** позволяет получить скрытые файлы, которые в противном случае были бы пропущены.</span><span class="sxs-lookup"><span data-stu-id="373c0-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="373c0-138">(Нельзя использовать `c:\temp\*.txt` , так как **рекурсивный** параметр работает с каталогами, а не с файлами.)</span><span class="sxs-lookup"><span data-stu-id="373c0-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="373c0-139">Оператор конвейера ( `|` ) отправляет объекты, представляющие извлеченные файлы, в `Set-Acl` командлет, который применяет дескриптор безопасности в параметре **аклобжект** ко всем файлам в конвейере.</span><span class="sxs-lookup"><span data-stu-id="373c0-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="373c0-140">На практике рекомендуется использовать параметр **WhatIf** со всеми `Set-Acl` командами, которые могут повлиять на несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="373c0-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="373c0-141">В этом случае вторая команда в конвейере будет иметь значение `Set-Acl -AclObject $NewAcl -WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="373c0-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="373c0-142">Она выводит на экран список файлов, к которым применяется команда.</span><span class="sxs-lookup"><span data-stu-id="373c0-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="373c0-143">После просмотра результата можно выполнить команду еще раз без параметра **WhatIf** .</span><span class="sxs-lookup"><span data-stu-id="373c0-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="373c0-144">Пример 4. Отключение наследования и сохранение унаследованных правил доступа</span><span class="sxs-lookup"><span data-stu-id="373c0-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="373c0-145">Эти команды будут отключать наследование доступа из родительских папок, сохраняя при этом существующие унаследованные правила доступа.</span><span class="sxs-lookup"><span data-stu-id="373c0-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="373c0-146">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="373c0-147">Затем создаются переменные для преобразования наследуемых правил доступа в явные правила доступа.</span><span class="sxs-lookup"><span data-stu-id="373c0-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="373c0-148">Чтобы защитить правила доступа, связанные с этим, из наследования, задайте для `$isProtected` переменной значение `$true` . чтобы разрешить наследование, задайте значение `$isProtected` `$false` .</span><span class="sxs-lookup"><span data-stu-id="373c0-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="373c0-149">Дополнительные сведения см. в разделе [Настройка защиты правила доступа](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span><span class="sxs-lookup"><span data-stu-id="373c0-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="373c0-150">Для `$preserveInheritance` переменной задается значение `$true` , чтобы сохранить унаследованные правила доступа; значение false, чтобы удалить унаследованные правила доступа.</span><span class="sxs-lookup"><span data-stu-id="373c0-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="373c0-151">Затем защита правила доступа обновляется с помощью метода **сетакцессрулепротектион ()** .</span><span class="sxs-lookup"><span data-stu-id="373c0-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="373c0-152">Последняя команда использует `Set-Acl` для применения дескриптора безопасности к Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="373c0-153">После выполнения команды списки управления доступом к Dog.txt, унаследованные из папки pets, будут применены непосредственно к Dog.txt, а новые политики доступа, добавленные в pets, не будут изменять доступ к Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="373c0-154">Пример 5. Предоставление администраторам полного доступа к файлу</span><span class="sxs-lookup"><span data-stu-id="373c0-154">Example 5: Grant Administrators Full Control of the file</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="373c0-155">Эта команда предоставит группе **Builtin \ администраторы** полный доступ к файлу Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="373c0-156">Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="373c0-157">Далее создаются переменные, позволяющие предоставить группе **Builtin** \ полный доступ к файлу Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="373c0-158">`$identity`Для переменной задается имя [учетной записи пользователя](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span><span class="sxs-lookup"><span data-stu-id="373c0-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span>
<span data-ttu-id="373c0-159">`$fileSystemRights`Переменная, для которой задано значение фуллконтрол, может быть любым значением [филесистемригхтс](/dotnet/api/system.security.accesscontrol.filesystemrights) , указывающим тип операции, связанной с правилом доступа.</span><span class="sxs-lookup"><span data-stu-id="373c0-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="373c0-160">`$type`Переменная со значением "Allow" указывает, следует ли разрешить или запретить операцию.</span><span class="sxs-lookup"><span data-stu-id="373c0-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="373c0-161">`$fileSystemAccessRuleArgumentList`Переменная является списком аргументов, которая передается при создании нового объекта **филесистемакцессруле** .</span><span class="sxs-lookup"><span data-stu-id="373c0-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="373c0-162">Затем создается новый объект **филесистемакцессруле** , и объект **филесистемакцессруле** передается в метод **сетакцессруле ()** , добавляет новое правило доступа.</span><span class="sxs-lookup"><span data-stu-id="373c0-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="373c0-163">Последняя команда использует `Set-Acl` для применения дескриптора безопасности к Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span>
<span data-ttu-id="373c0-164">По завершении выполнения команды группа **Builtin \ администраторы** будет иметь полный доступ к Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="373c0-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="373c0-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="373c0-165">PARAMETERS</span></span>

### <span data-ttu-id="373c0-166">-Аклобжект</span><span class="sxs-lookup"><span data-stu-id="373c0-166">-AclObject</span></span>

<span data-ttu-id="373c0-167">Указывает список управления доступом с необходимыми значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="373c0-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="373c0-168">`Set-Acl` изменяет список управления доступом для элемента, указанного параметром **path** или **InputObject** , в соответствии со значениями в указанном объекте безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="373c0-169">Выходные данные команды можно сохранить `Get-Acl` в переменной, а затем использовать параметр **аклобжект** для передачи переменной или ввести `Get-Acl` команду.</span><span class="sxs-lookup"><span data-stu-id="373c0-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-170">-Централакцессполици</span><span class="sxs-lookup"><span data-stu-id="373c0-170">-CentralAccessPolicy</span></span>

<span data-ttu-id="373c0-171">Определяет или изменяет централизованную политику доступа к элементу.</span><span class="sxs-lookup"><span data-stu-id="373c0-171">Establishes or changes the central access policy of the item.</span></span>
<span data-ttu-id="373c0-172">Введите идентификатор CAP или понятное имя централизованной политики доступа на компьютере.</span><span class="sxs-lookup"><span data-stu-id="373c0-172">Enter the CAP ID or friendly name of a central access policy on the computer.</span></span>

<span data-ttu-id="373c0-173">Начиная с Windows Server 2012, администраторы могут использовать Active Directory и групповая политика, чтобы задать централизованные политики доступа для пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="373c0-173">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span>
<span data-ttu-id="373c0-174">Дополнительные сведения см. в разделе [динамический контроль доступа: обзор сценария](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="373c0-174">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="373c0-175">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="373c0-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-176">-Клеарцентралакцессполици</span><span class="sxs-lookup"><span data-stu-id="373c0-176">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="373c0-177">Удаляет централизованную политику доступа из указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="373c0-177">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="373c0-178">Начиная с Windows Server 2012, администраторы могут использовать Active Directory и групповая политика, чтобы задать централизованные политики доступа для пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="373c0-178">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="373c0-179">Дополнительные сведения см. в разделе [динамический контроль доступа: обзор сценария](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="373c0-179">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="373c0-180">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="373c0-180">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-181">-Exclude</span><span class="sxs-lookup"><span data-stu-id="373c0-181">-Exclude</span></span>

<span data-ttu-id="373c0-182">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="373c0-182">Omits the specified items.</span></span> <span data-ttu-id="373c0-183">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="373c0-183">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="373c0-184">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="373c0-184">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="373c0-185">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="373c0-185">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="373c0-186">-Filter</span><span class="sxs-lookup"><span data-stu-id="373c0-186">-Filter</span></span>

<span data-ttu-id="373c0-187">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="373c0-187">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="373c0-188">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="373c0-188">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="373c0-189">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="373c0-189">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="373c0-190">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="373c0-190">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="373c0-191">-Include</span><span class="sxs-lookup"><span data-stu-id="373c0-191">-Include</span></span>

<span data-ttu-id="373c0-192">Изменяет только указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="373c0-192">Changes only the specified items.</span></span> <span data-ttu-id="373c0-193">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="373c0-193">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="373c0-194">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="373c0-194">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="373c0-195">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="373c0-195">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="373c0-196">-InputObject</span><span class="sxs-lookup"><span data-stu-id="373c0-196">-InputObject</span></span>

<span data-ttu-id="373c0-197">Изменяет дескриптор безопасности указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="373c0-197">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="373c0-198">Введите переменную, содержащую объект, либо команду, которая его возвращают.</span><span class="sxs-lookup"><span data-stu-id="373c0-198">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="373c0-199">Объект нельзя передать в конвейер, чтобы изменить его `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="373c0-199">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="373c0-200">Вместо этого настроить параметр **InputObject** прямо в команде.</span><span class="sxs-lookup"><span data-stu-id="373c0-200">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="373c0-201">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="373c0-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-202">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="373c0-202">-LiteralPath</span></span>

<span data-ttu-id="373c0-203">Изменяет дескриптор безопасности указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="373c0-203">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="373c0-204">В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="373c0-204">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="373c0-205">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="373c0-205">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="373c0-206">Если путь содержит escape-символы, заключите его в одинарные кавычки ( `'` ).</span><span class="sxs-lookup"><span data-stu-id="373c0-206">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="373c0-207">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="373c0-207">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="373c0-208">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="373c0-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-209">-PassThru</span><span class="sxs-lookup"><span data-stu-id="373c0-209">-Passthru</span></span>

<span data-ttu-id="373c0-210">Возвращает объект, представляющий измененный дескриптор безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-210">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="373c0-211">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="373c0-211">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-212">-Path</span><span class="sxs-lookup"><span data-stu-id="373c0-212">-Path</span></span>

<span data-ttu-id="373c0-213">Изменяет дескриптор безопасности указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="373c0-213">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="373c0-214">Введите путь к элементу, например, путь к файлу или ключу реестра.</span><span class="sxs-lookup"><span data-stu-id="373c0-214">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="373c0-215">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="373c0-215">Wildcards are permitted.</span></span>

<span data-ttu-id="373c0-216">Если объект безопасности передается в `Set-Acl` (с помощью параметров **Аклобжект** или **SecurityDescriptor** или путем передачи объекта безопасности из Get-Acl в `Set-Acl` ), а параметр **пути** (имя и значение) не указан, `Set-Acl` используется путь, включенный в объект безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-216">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="373c0-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="373c0-217">-Confirm</span></span>

<span data-ttu-id="373c0-218">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="373c0-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-219">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="373c0-219">-UseTransaction</span></span>

<span data-ttu-id="373c0-220">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="373c0-220">Includes the command in the active transaction.</span></span>
<span data-ttu-id="373c0-221">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="373c0-221">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="373c0-222">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="373c0-222">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="373c0-223">-WhatIf</span></span>

<span data-ttu-id="373c0-224">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="373c0-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="373c0-225">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="373c0-225">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="373c0-226">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="373c0-226">CommonParameters</span></span>

<span data-ttu-id="373c0-227">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="373c0-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="373c0-228">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="373c0-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="373c0-229">Входные данные</span><span class="sxs-lookup"><span data-stu-id="373c0-229">INPUTS</span></span>

### <span data-ttu-id="373c0-230">System. Security. AccessControl. Обжектсекурити, System. Security. AccessControl. Коммонсекуритидескриптор</span><span class="sxs-lookup"><span data-stu-id="373c0-230">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="373c0-231">Объект ACL или дескриптор безопасности можно передать в `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="373c0-231">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="373c0-232">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="373c0-232">OUTPUTS</span></span>

### <span data-ttu-id="373c0-233">System. Security. AccessControl. FileSecurity</span><span class="sxs-lookup"><span data-stu-id="373c0-233">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="373c0-234">По умолчанию не `Set-Acl` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="373c0-234">By default, `Set-Acl` does not generate any output.</span></span>
<span data-ttu-id="373c0-235">но при использовании параметра **Passthru** создает объект безопасности.</span><span class="sxs-lookup"><span data-stu-id="373c0-235">However, if you use the **Passthru** parameter, it generates a security object.</span></span>
<span data-ttu-id="373c0-236">Тип объекта безопасности зависит от типа элемента.</span><span class="sxs-lookup"><span data-stu-id="373c0-236">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="373c0-237">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="373c0-237">NOTES</span></span>

 <span data-ttu-id="373c0-238">`Set-Acl`Командлет поддерживается в файловой системе PowerShell и поставщиках реестра.</span><span class="sxs-lookup"><span data-stu-id="373c0-238">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="373c0-239">а значит его можно использовать для изменения дескрипторов безопасности файлов, каталогов и разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="373c0-239">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="373c0-240">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="373c0-240">RELATED LINKS</span></span>

[<span data-ttu-id="373c0-241">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="373c0-241">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="373c0-242">филесистемакцессруле</span><span class="sxs-lookup"><span data-stu-id="373c0-242">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="373c0-243">Обжектсекурити. Сетакцессрулепротектион</span><span class="sxs-lookup"><span data-stu-id="373c0-243">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="373c0-244">филесистемригхтс</span><span class="sxs-lookup"><span data-stu-id="373c0-244">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
