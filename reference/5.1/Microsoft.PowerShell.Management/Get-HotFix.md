---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 33da44a4a228b57296b85fbafb40da51657df1c1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228397"
---
# <span data-ttu-id="2eb0b-103">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="2eb0b-103">Get-HotFix</span></span>

## <span data-ttu-id="2eb0b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2eb0b-104">SYNOPSIS</span></span>
<span data-ttu-id="2eb0b-105">Возвращает исправления, установленные на локальных или удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-105">Gets the hotfixes that are installed on local or remote computers.</span></span>

## <span data-ttu-id="2eb0b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2eb0b-106">SYNTAX</span></span>

### <span data-ttu-id="2eb0b-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2eb0b-107">Default (Default)</span></span>

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### <span data-ttu-id="2eb0b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2eb0b-108">Description</span></span>

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## <span data-ttu-id="2eb0b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2eb0b-109">DESCRIPTION</span></span>

<span data-ttu-id="2eb0b-110">`Get-Hotfix`Командлет получает исправления или обновления, установленные на локальном компьютере или на указанных удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-110">The `Get-Hotfix` cmdlet gets hotfixes, or updates, that are installed on the local computer or specified remote computers.</span></span> <span data-ttu-id="2eb0b-111">Обновления могут устанавливаться Центр обновления Windows, Центр обновления Майкрософт, Windows Server Update Services или вручную.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-111">The updates can be installed by Windows Update, Microsoft Update, Windows Server Update Services, or manually installed.</span></span>

## <span data-ttu-id="2eb0b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="2eb0b-112">EXAMPLES</span></span>

### <span data-ttu-id="2eb0b-113">Пример 1. получение всех исправлений на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="2eb0b-113">Example 1: Get all hotfixes on the local computer</span></span>

<span data-ttu-id="2eb0b-114">`Get-Hotfix`Командлет возвращает все исправления, установленные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-114">The `Get-Hotfix` cmdlet gets all hotfixes installed on the local computer.</span></span>

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### <span data-ttu-id="2eb0b-115">Пример 2. получение исправлений с нескольких компьютеров, отфильтрованных по строке</span><span class="sxs-lookup"><span data-stu-id="2eb0b-115">Example 2: Get hotfixes from multiple computers filtered by a string</span></span>

<span data-ttu-id="2eb0b-116">`Get-Hotfix`Команда использует параметры для получения исправлений, установленных на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-116">The `Get-Hotfix` command uses parameters to get hotfixes installed on remote computers.</span></span> <span data-ttu-id="2eb0b-117">Результаты фильтруются по указанной строке описания.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-117">The results are filtered by a specified description string.</span></span>

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

<span data-ttu-id="2eb0b-118">`Get-Hotfix` фильтрует выходные данные с помощью параметра **Description** и строки **безопасности** , включающей `*` подстановочный знак звездочки ().</span><span class="sxs-lookup"><span data-stu-id="2eb0b-118">`Get-Hotfix` filters the output with the **Description** parameter and the string **Security** that includes the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="2eb0b-119">Параметр **ComputerName** включает строку имен удаленных компьютеров с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-119">The **ComputerName** parameter includes a comma-separated string of remote computer names.</span></span> <span data-ttu-id="2eb0b-120">Параметр **Credential** указывает учетную запись пользователя, имеющую разрешение на доступ к удаленным компьютерам и командам выполнения.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-120">The **Credential** parameter specifies a user account that has permission to access the remote computers and run commands.</span></span>

### <span data-ttu-id="2eb0b-121">Пример 3. Проверка установки обновления и запись имен компьютеров в файл</span><span class="sxs-lookup"><span data-stu-id="2eb0b-121">Example 3: Verify if an update is installed and write computer names to a file</span></span>

<span data-ttu-id="2eb0b-122">Команды в этом примере проверяют, установлено ли конкретное обновление.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-122">The commands in this example verify whether a particular update installed.</span></span> <span data-ttu-id="2eb0b-123">Если обновление не установлено, имя компьютера записывается в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-123">If the update isn't installed, the computer name is written to a text file.</span></span>

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

<span data-ttu-id="2eb0b-124">`$A`Переменная содержит имена компьютеров, полученные `Get-Content` из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-124">The `$A` variable contains computer names that were obtained by `Get-Content` from a text file.</span></span> <span data-ttu-id="2eb0b-125">Объекты в `$A` отправляются по конвейеру в `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="2eb0b-125">The objects in `$A` are sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="2eb0b-126">`if`Оператор использует `Get-Hotfix` командлет с параметром **ID** и конкретным идентификатором для каждого имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-126">An `if` statement uses the `Get-Hotfix` cmdlet with the **Id** parameter and a specific Id number for each computer name.</span></span> <span data-ttu-id="2eb0b-127">Если на компьютере не установлен указанный идентификатор исправления, `Add-Content` командлет записывает имя компьютера в файл.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-127">If a computer doesn't have the specified hotfix Id installed, the `Add-Content` cmdlet writes the computer name to a file.</span></span>

### <span data-ttu-id="2eb0b-128">Пример 4. Получение последнего исправления на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="2eb0b-128">Example 4: Get the most recent hotfix on the local computer</span></span>

<span data-ttu-id="2eb0b-129">В этом примере возвращается последнее исправление, установленное на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-129">This example gets the most recent hotfix installed on a computer.</span></span>

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

<span data-ttu-id="2eb0b-130">`Get-Hotfix` отправляет объекты по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-130">`Get-Hotfix` sends the objects down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2eb0b-131">`Sort-Object` Сортирует объекты по возрастанию и использует параметр **Property** для вычисления каждой **установить** даты.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-131">`Sort-Object` sorts objects by ascending order and uses the **Property** parameter to evaluate each **InstalledOn** date.</span></span> <span data-ttu-id="2eb0b-132">В нотации массива `[-1]` выбирается последнее установленное исправление.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-132">The array notation `[-1]` selects the most recent installed hotfix.</span></span>

## <span data-ttu-id="2eb0b-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2eb0b-133">PARAMETERS</span></span>

### <span data-ttu-id="2eb0b-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2eb0b-134">-ComputerName</span></span>

<span data-ttu-id="2eb0b-135">Указывает удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-135">Specifies a remote computer.</span></span> <span data-ttu-id="2eb0b-136">Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-136">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>

<span data-ttu-id="2eb0b-137">Если параметр **ComputerName** не указан, `Get-Hotfix` выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-137">When the **ComputerName** parameter isn't specified, `Get-Hotfix` runs on the local computer.</span></span>

<span data-ttu-id="2eb0b-138">Параметр **ComputerName** не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-138">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="2eb0b-139">Если компьютер не настроен для выполнения удаленных команд, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="2eb0b-139">If your computer isn't configured to run remote commands, use the **ComputerName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0b-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="2eb0b-140">-Credential</span></span>

<span data-ttu-id="2eb0b-141">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-141">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="2eb0b-142">Значение по умолчанию — текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-142">The default is the current user</span></span>

<span data-ttu-id="2eb0b-143">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-143">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2eb0b-144">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-144">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="2eb0b-145">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="2eb0b-145">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2eb0b-146">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2eb0b-146">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0b-147">-Description</span><span class="sxs-lookup"><span data-stu-id="2eb0b-147">-Description</span></span>

<span data-ttu-id="2eb0b-148">`Get-HotFix` использует параметр **Description** для указания типов исправлений.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-148">`Get-HotFix` uses the **Description** parameter to specify hotfix types.</span></span> <span data-ttu-id="2eb0b-149">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-149">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2eb0b-150">-Id</span><span class="sxs-lookup"><span data-stu-id="2eb0b-150">-Id</span></span>

<span data-ttu-id="2eb0b-151">Фильтрует `Get-HotFix` результаты для конкретных идентификаторов исправлений.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-151">Filters the `Get-HotFix` results for specific hotfix Ids.</span></span> <span data-ttu-id="2eb0b-152">Подстановочные знаки не принимаются.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-152">Wildcards aren't accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2eb0b-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2eb0b-153">CommonParameters</span></span>

<span data-ttu-id="2eb0b-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2eb0b-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2eb0b-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2eb0b-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2eb0b-156">INPUTS</span></span>

### <span data-ttu-id="2eb0b-157">Строка</span><span class="sxs-lookup"><span data-stu-id="2eb0b-157">String</span></span>

<span data-ttu-id="2eb0b-158">Одно или несколько имен компьютеров можно передать в командлет Get-HotFix по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-158">You can pipe one or more computer names to Get-HotFix.</span></span>

## <span data-ttu-id="2eb0b-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2eb0b-159">OUTPUTS</span></span>

### <span data-ttu-id="2eb0b-160">System. Management. ManagementObject # root\CIMV2\ Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="2eb0b-160">System.Management.ManagementObject#root\CIMV2\Win32_QuickFixEngineering</span></span>

<span data-ttu-id="2eb0b-161">`Get-HotFix` Возвращает объекты, представляющие исправления на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-161">`Get-HotFix` returns objects that represent the hotfixes on the computer.</span></span>

## <span data-ttu-id="2eb0b-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2eb0b-162">NOTES</span></span>

<span data-ttu-id="2eb0b-163">[Класс WMI](/windows/desktop/WmiSdk/retrieving-a-class) **Win32_QuickFixEngineering** представляет небольшое обновление на уровне системы, которое обычно называется обновлением QFE, которое применяется к текущей операционной системе.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-163">The **Win32_QuickFixEngineering** [WMI class](/windows/desktop/WmiSdk/retrieving-a-class) represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the current operating system.</span></span> <span data-ttu-id="2eb0b-164">Этот класс возвращает только обновления, предоставляемые компонентом обслуживания на основе компонентов (CBS).</span><span class="sxs-lookup"><span data-stu-id="2eb0b-164">This class returns only the updates supplied by Component Based Servicing (CBS).</span></span> <span data-ttu-id="2eb0b-165">Эти обновления не перечислены в реестре.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-165">These updates are not listed in the registry.</span></span> <span data-ttu-id="2eb0b-166">Обновления, предоставляемые Microsoft установщик Windows (MSI) или [Центр обновления Windows](https://update.microsoft.com) сайте, не возвращаются **Win32_QuickFixEngineering** .</span><span class="sxs-lookup"><span data-stu-id="2eb0b-166">Updates supplied by Microsoft Windows Installer (MSI) or the [Windows Update](https://update.microsoft.com) site are not returned by **Win32_QuickFixEngineering** .</span></span> <span data-ttu-id="2eb0b-167">Дополнительные сведения см. в разделе [класс Win32_QuickFixEngineering](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span><span class="sxs-lookup"><span data-stu-id="2eb0b-167">For more information, see [Win32_QuickFixEngineering class](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span></span>

<span data-ttu-id="2eb0b-168">`Get-HotFix`Выходные данные могут отличаться в разных операционных системах.</span><span class="sxs-lookup"><span data-stu-id="2eb0b-168">The `Get-HotFix` output might vary on different operating systems.</span></span>

## <span data-ttu-id="2eb0b-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2eb0b-169">RELATED LINKS</span></span>

[<span data-ttu-id="2eb0b-170">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="2eb0b-170">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="2eb0b-171">Add-Content</span><span class="sxs-lookup"><span data-stu-id="2eb0b-171">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="2eb0b-172">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="2eb0b-172">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="2eb0b-173">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="2eb0b-173">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="2eb0b-174">Класс Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="2eb0b-174">Win32_QuickFixEngineering class</span></span>](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
