---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: aa83b6318b8e3b07d17cbb3e511bc7ab4aa9a774
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600873"
---
# <span data-ttu-id="430c2-102">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="430c2-102">Get-PSDrive</span></span>

## <span data-ttu-id="430c2-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="430c2-103">SYNOPSIS</span></span>
<span data-ttu-id="430c2-104">Получает диски в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-104">Gets drives in the current session.</span></span>

## <span data-ttu-id="430c2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="430c2-105">SYNTAX</span></span>

### <span data-ttu-id="430c2-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="430c2-106">Name (Default)</span></span>

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="430c2-107">литералнаме</span><span class="sxs-lookup"><span data-stu-id="430c2-107">LiteralName</span></span>

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="430c2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="430c2-108">DESCRIPTION</span></span>

<span data-ttu-id="430c2-109">`Get-PSDrive`Командлет возвращает диски в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-109">The `Get-PSDrive` cmdlet gets the drives in the current session.</span></span> <span data-ttu-id="430c2-110">Можно получить определенный диск или все диски в сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-110">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="430c2-111">Этот командлет получает следующие типы дисков:</span><span class="sxs-lookup"><span data-stu-id="430c2-111">This cmdlet gets the following types of drives:</span></span>

- <span data-ttu-id="430c2-112">Логические диски Windows на компьютере, включая диски, сопоставленные с сетевыми общими папками.</span><span class="sxs-lookup"><span data-stu-id="430c2-112">Windows logical drives on the computer, including drives mapped to network shares.</span></span>
- <span data-ttu-id="430c2-113">Диски, предоставляемые поставщиками PowerShell (например, Certificate:, функция: и псевдонимы дисков), а также диски HKLM: и HKCU:, предоставляемые поставщиком реестра Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-113">Drives exposed by PowerShell providers (such as the Certificate:, Function:, and Alias: drives) and the HKLM: and HKCU: drives that are exposed by the Windows PowerShell Registry provider.</span></span>
- <span data-ttu-id="430c2-114">Указанные сеансом временные диски и постоянные сопоставленные сетевые диски, созданные с помощью командлета New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="430c2-114">Session-specified temporary drives and persistent mapped network drives that you create by using the New-PSDrive cmdlet.</span></span>

<span data-ttu-id="430c2-115">Начиная с Windows PowerShell 3,0, параметр **Persist** `New-PSDrive` командлета может создавать сопоставленные сетевые диски, сохраненные на локальном компьютере и доступные в других сеансах.</span><span class="sxs-lookup"><span data-stu-id="430c2-115">Beginning in Windows PowerShell 3.0, the **Persist** parameter of the `New-PSDrive` cmdlet can create mapped network drives that are saved on the local computer and are available in other sessions.</span></span> <span data-ttu-id="430c2-116">Дополнительные сведения см. в разделе New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="430c2-116">For more information, see New-PSDrive.</span></span>

<span data-ttu-id="430c2-117">Кроме того, начиная с Windows PowerShell 3.0, когда внешний диск подключается к компьютеру, Windows PowerShell автоматически добавляет в файловую систему объект PSDrive, представляющий новый диск.</span><span class="sxs-lookup"><span data-stu-id="430c2-117">Also, beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, Windows PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="430c2-118">Перезапускать Windows PowerShell не нужно.</span><span class="sxs-lookup"><span data-stu-id="430c2-118">You do not need to restart Windows PowerShell.</span></span> <span data-ttu-id="430c2-119">Аналогичным образом, когда внешний диск отключается от компьютера, Windows PowerShell автоматически удаляет объект PSDrive, представляющий удаленный диск.</span><span class="sxs-lookup"><span data-stu-id="430c2-119">Similarly, when an external drive is disconnected from the computer, Windows PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="430c2-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="430c2-120">EXAMPLES</span></span>

### <span data-ttu-id="430c2-121">Пример 1. Получение дисков в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="430c2-121">Example 1: Get drives in the current session</span></span>

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

<span data-ttu-id="430c2-122">Эта команда получает диски в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-122">This command gets the drives in the current session.</span></span>

<span data-ttu-id="430c2-123">В выходных данных отображается жесткий диск (C:), дисковод компакт-дисков (D:), а также диски, предоставляемые поставщиками Windows PowerShell (псевдоним:, CERT:, env:, функция:, HKCU:, HKLM: и переменная:).</span><span class="sxs-lookup"><span data-stu-id="430c2-123">The output shows the hard drive (C:), CD-ROM drive (D:), and the drives exposed by the Windows PowerShell providers (Alias:, Cert:, Env:, Function:, HKCU:, HKLM:, and Variable:).</span></span>

### <span data-ttu-id="430c2-124">Пример 2. получение диска на компьютере</span><span class="sxs-lookup"><span data-stu-id="430c2-124">Example 2: Get a drive on the computer</span></span>

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

<span data-ttu-id="430c2-125">Эта команда получает диск D: на компьютере.</span><span class="sxs-lookup"><span data-stu-id="430c2-125">This command gets the D: drive on the computer.</span></span> <span data-ttu-id="430c2-126">Обратите внимание, что за буквой диска в команде не следует двоеточие.</span><span class="sxs-lookup"><span data-stu-id="430c2-126">Note that the drive letter in the command is not followed by a colon.</span></span>

### <span data-ttu-id="430c2-127">Пример 3. получение всех дисков, поддерживаемых поставщиком файловой системы Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="430c2-127">Example 3: Get all the drives that are supported by the Windows PowerShell file system provider</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

<span data-ttu-id="430c2-128">Эта команда получает все диски, которые поддерживаются поставщиком FileSystem оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-128">This command gets all of the drives that are supported by the Windows PowerShell FileSystem provider.</span></span> <span data-ttu-id="430c2-129">Сюда входят фиксированные диски, логические разделы, сопоставленные сетевые диски и временные диски, созданные с помощью командлета New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="430c2-129">This includes fixed drives, logical partitions, mapped network drives, and temporary drives that you create by using the New-PSDrive cmdlet.</span></span>

### <span data-ttu-id="430c2-130">Пример 4. Проверьте, используется ли диск в качестве имени диска Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-130">Example 4: Check to see if a drive is in use as a Windows PowerShell drive name</span></span>

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

<span data-ttu-id="430c2-131">Эта команда проверяет, используется ли диск X в качестве имени диска Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-131">This command checks to see whether the X drive is already in use as a Windows PowerShell drive name.</span></span>
<span data-ttu-id="430c2-132">Если это не так, команда использует `New-PSDrive` командлет для создания временного диска, сопоставленного с ключом реестра HKLM: \ Software.</span><span class="sxs-lookup"><span data-stu-id="430c2-132">If it is not, the command uses the `New-PSDrive` cmdlet to create a temporary drive that is mapped to the HKLM:\SOFTWARE registry key.</span></span>

### <span data-ttu-id="430c2-133">Пример 5. Сравнение типов системных дисков</span><span class="sxs-lookup"><span data-stu-id="430c2-133">Example 5: Compare the types of files system drives</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

<span data-ttu-id="430c2-134">В этом примере сравниваются типы дисков файловой системы, отображаемые в, `Get-PSDrive` отображаемые с помощью других методов.</span><span class="sxs-lookup"><span data-stu-id="430c2-134">This example compares the types of file system drives that are displayed by `Get-PSDrive` to those displayed by using other methods.</span></span> <span data-ttu-id="430c2-135">В этом примере демонстрируются различные способы отображения дисков в Windows PowerShell и показано, что диски конкретного сеанса, созданные с помощью командлета New-PSDrive, доступны только в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-135">This example demonstrates different ways to display drives in Windows PowerShell, and it shows that session-specific drives created by using the New-PSDrive cmdlet are accessible only in Windows PowerShell.</span></span>

<span data-ttu-id="430c2-136">Первая команда использует `Get-PSDrive` для получения всех дисков файловой системы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-136">The first command uses `Get-PSDrive` to get all of the file system drives in the session.</span></span> <span data-ttu-id="430c2-137">Это относится к фиксированным дискам (C: и D:), подключенному сетевому диску (G:) , созданного с помощью параметра **Persist** среды `New-PSDrive` , и диска PowerShell (T:) , который был создан с помощью `New-PSDrive` без параметра **Persist** .</span><span class="sxs-lookup"><span data-stu-id="430c2-137">This includes the fixed drives (C: and D:), a mapped network drive (G:) that was created by using the **Persist** parameter of `New-PSDrive`, and a PowerShell drive (T:) that was created by using `New-PSDrive` without the **Persist** parameter.</span></span>

<span data-ttu-id="430c2-138">Команда **net use** отображает сопоставленные сетевые диски Windows. в этом случае отображается только диск G.</span><span class="sxs-lookup"><span data-stu-id="430c2-138">The **net use** command displays Windows mapped network drives, in this case it displays only the G drive.</span></span> <span data-ttu-id="430c2-139">Он не отображает диск X:, созданный `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="430c2-139">It does not display the X: drive that was created by `New-PSDrive`.</span></span> <span data-ttu-id="430c2-140">Он показывает, что диск G: также сопоставлен с \\ \\ музыкой \\ гратефулдеад.</span><span class="sxs-lookup"><span data-stu-id="430c2-140">It shows that the G: drive is also mapped to \\\\Music\\GratefulDead.</span></span>

<span data-ttu-id="430c2-141">Третья команда использует метод **GetDrives** класса **System.IO.DriveInfo** Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="430c2-141">The third command uses the **GetDrives** method of the Microsoft .NET Framework **System.IO.DriveInfo** class.</span></span> <span data-ttu-id="430c2-142">Эта команда получает диски файловой системы Windows, включая диск G:, но не получает диски, созданные `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="430c2-142">This command gets the Windows file system drives, including drive G:, but it does not get the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="430c2-143">Четвертая команда использует `Get-CimInstance` командлет для получения экземпляров класса **Win32_LogicalDisk** .</span><span class="sxs-lookup"><span data-stu-id="430c2-143">The fourth command uses the `Get-CimInstance` cmdlet to get the instances of the **Win32_LogicalDisk** class.</span></span> <span data-ttu-id="430c2-144">Он возвращает диски A:, C:, D:, E: и G:, но не диски, созданные `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="430c2-144">It returns the A:, C:, D:, E:, and G: drives, but not the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="430c2-145">Последняя команда использует `Get-CimInstance` командлет для вывода экземпляров класса **Win32_NetworkConnection** .</span><span class="sxs-lookup"><span data-stu-id="430c2-145">The last command uses the `Get-CimInstance` cmdlet to display the instances of the **Win32_NetworkConnection** class.</span></span> <span data-ttu-id="430c2-146">Как и при **использовании команды net use**, она возвращает только постоянный диск G:, созданный `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="430c2-146">Like **net use**, it returns only the persistent G: drive created by `New-PSDrive`.</span></span>

## <span data-ttu-id="430c2-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="430c2-147">PARAMETERS</span></span>

### <span data-ttu-id="430c2-148">-Литералнаме</span><span class="sxs-lookup"><span data-stu-id="430c2-148">-LiteralName</span></span>

<span data-ttu-id="430c2-149">Задает имя диска.</span><span class="sxs-lookup"><span data-stu-id="430c2-149">Specifies the name of the drive.</span></span>

<span data-ttu-id="430c2-150">Значение параметра **LiteralName** используется точно так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="430c2-150">The value of **LiteralName** is used exactly as it is typed.</span></span> <span data-ttu-id="430c2-151">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="430c2-151">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="430c2-152">Если имя включает escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="430c2-152">If the name includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="430c2-153">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="430c2-153">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="430c2-154">-Name</span><span class="sxs-lookup"><span data-stu-id="430c2-154">-Name</span></span>

<span data-ttu-id="430c2-155">Указывает в виде массива строк имя или имя дисков, которые этот командлет получает в операции.</span><span class="sxs-lookup"><span data-stu-id="430c2-155">Specifies, as a string array, the name or name of drives that this cmdlet gets in the operation.</span></span>
<span data-ttu-id="430c2-156">Введите имя диска или букву без двоеточия (:).</span><span class="sxs-lookup"><span data-stu-id="430c2-156">Type the drive name or letter without a colon (:).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="430c2-157">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="430c2-157">-PSProvider</span></span>

<span data-ttu-id="430c2-158">Указывает в качестве массива строк поставщик Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="430c2-158">Specifies, as a string array, the Windows PowerShell provider.</span></span> <span data-ttu-id="430c2-159">Этот командлет возвращает только диски, поддерживаемые этим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="430c2-159">This cmdlet gets only the drives supported by this provider.</span></span> <span data-ttu-id="430c2-160">Введите имя поставщика, например FileSystem, Registry или Certificate.</span><span class="sxs-lookup"><span data-stu-id="430c2-160">Type the name of a provider, such as FileSystem, Registry, or Certificate.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="430c2-161">-Scope</span><span class="sxs-lookup"><span data-stu-id="430c2-161">-Scope</span></span>

<span data-ttu-id="430c2-162">Указывает область, в которой этот командлет получает диски.</span><span class="sxs-lookup"><span data-stu-id="430c2-162">Specifies the scope in which this cmdlet gets the drives.</span></span>

<span data-ttu-id="430c2-163">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="430c2-163">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="430c2-164">Глобальный</span><span class="sxs-lookup"><span data-stu-id="430c2-164">Global</span></span>
- <span data-ttu-id="430c2-165">Локальная</span><span class="sxs-lookup"><span data-stu-id="430c2-165">Local</span></span>
- <span data-ttu-id="430c2-166">Скрипт</span><span class="sxs-lookup"><span data-stu-id="430c2-166">Script</span></span>
- <span data-ttu-id="430c2-167">число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).</span><span class="sxs-lookup"><span data-stu-id="430c2-167">a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span> <span data-ttu-id="430c2-168">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="430c2-168">"Local" is the default.</span></span>

<span data-ttu-id="430c2-169">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="430c2-169">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="430c2-170">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="430c2-170">CommonParameters</span></span>

<span data-ttu-id="430c2-171">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="430c2-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="430c2-172">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="430c2-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="430c2-173">Входные данные</span><span class="sxs-lookup"><span data-stu-id="430c2-173">INPUTS</span></span>

### <span data-ttu-id="430c2-174">None</span><span class="sxs-lookup"><span data-stu-id="430c2-174">None</span></span>

<span data-ttu-id="430c2-175">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="430c2-175">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="430c2-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="430c2-176">OUTPUTS</span></span>

### <span data-ttu-id="430c2-177">System.Management.Automation.PSDРивеинфо</span><span class="sxs-lookup"><span data-stu-id="430c2-177">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="430c2-178">Этот командлет возвращает объекты, представляющие диски в сеансе.</span><span class="sxs-lookup"><span data-stu-id="430c2-178">This cmdlet returns objects that represent the drives in the session.</span></span>

## <span data-ttu-id="430c2-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="430c2-179">NOTES</span></span>

* <span data-ttu-id="430c2-180">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="430c2-180">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="430c2-181">Чтобы получить список поставщиков, доступных в вашем сеансе, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="430c2-181">To list the providers available in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="430c2-182">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="430c2-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
* <span data-ttu-id="430c2-183">Сопоставленные сетевые диски, созданные с помощью параметра **Persist** командлета New-PSDrive, относятся к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="430c2-183">Mapped network drives that are created by using the **Persist** parameter of the New-PSDrive cmdlet are specific to a user account.</span></span> <span data-ttu-id="430c2-184">Подключенные сетевые диски, созданные в сеансах с параметром Запуск от имени администратора или с учетными данными другого пользователя, не отображаются в сеансах, запущенных без явных учетных данных или с учетными данными текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="430c2-184">Mapped network drives that you create in sessions that are started with the Run as administrator option or with the credentials of another user are not visible in sessions that are started without explicit credentials or with the credentials of the current user.</span></span>

## <span data-ttu-id="430c2-185">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="430c2-185">RELATED LINKS</span></span>

[<span data-ttu-id="430c2-186">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="430c2-186">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="430c2-187">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="430c2-187">Remove-PSDrive</span></span>](Remove-PSDrive.md)

[<span data-ttu-id="430c2-188">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="430c2-188">Get-PSProvider</span></span>](Get-PSProvider.md)

