---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226694"
---
# <span data-ttu-id="6f467-103">Export-Console</span><span class="sxs-lookup"><span data-stu-id="6f467-103">Export-Console</span></span>

## <span data-ttu-id="6f467-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6f467-104">SYNOPSIS</span></span>
<span data-ttu-id="6f467-105">Экспортирует имена оснасток в текущем сеансе в файл консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-105">Exports the names of snap-ins in the current session to a console file.</span></span>

## <span data-ttu-id="6f467-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6f467-106">SYNTAX</span></span>

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6f467-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6f467-107">DESCRIPTION</span></span>
<span data-ttu-id="6f467-108">Командлет **Export-Console** экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл консоли Windows PowerShell (. psc1).</span><span class="sxs-lookup"><span data-stu-id="6f467-108">The **Export-Console** cmdlet exports the names of the Windows PowerShell snap-ins in the current session to a Windows PowerShell console file (.psc1).</span></span>
<span data-ttu-id="6f467-109">Можно использовать этот командлет, чтобы сохранить оснастки для использования в последующих сеансах.</span><span class="sxs-lookup"><span data-stu-id="6f467-109">You can use this cmdlet to save the snap-ins for use in future sessions.</span></span>

<span data-ttu-id="6f467-110">Чтобы добавить оснастки в файл консоли. psc1 в сеанс, запустите Windows PowerShell (Powershell.exe) в командной строке с помощью Cmd.exe или другого сеанса Windows PowerShell, а затем используйте параметр *PSConsoleFile* в Powershell.exe, чтобы указать файл консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-110">To add the snap-ins in the .psc1 console file to a session, start Windows PowerShell (Powershell.exe) at the command line by using Cmd.exe or another Windows PowerShell session, and then use the *PSConsoleFile* parameter of Powershell.exe to specify the console file.</span></span>

<span data-ttu-id="6f467-111">Дополнительные сведения об оснастках Windows PowerShell см. в разделе about_PSSnapins.</span><span class="sxs-lookup"><span data-stu-id="6f467-111">For more information about Windows PowerShell snap-ins, see about_PSSnapins.</span></span>

## <span data-ttu-id="6f467-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="6f467-112">EXAMPLES</span></span>

### <span data-ttu-id="6f467-113">Пример 1. экспорт имен оснасток в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="6f467-113">Example 1: Export the names of snap-ins in the current session</span></span>

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

<span data-ttu-id="6f467-114">Эта команда экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл ConsoleS1. psc1 в папке консолей установочной папки Windows PowerShell $pshome.</span><span class="sxs-lookup"><span data-stu-id="6f467-114">This command exports the names of Windows PowerShell snap-ins in the current session to the ConsoleS1.psc1 file in the Consoles folder of the Windows PowerShell installation folder, $pshome.</span></span>

### <span data-ttu-id="6f467-115">Пример 2. экспорт имен оснасток в самый последний файл консоли</span><span class="sxs-lookup"><span data-stu-id="6f467-115">Example 2: Export the names of snap-ins to the most recent console file</span></span>

```
PS C:\> Export-Console
```

<span data-ttu-id="6f467-116">Эта команда экспортирует имена оснасток Windows PowerShell из текущего сеанса в файл консоли Windows PowerShell, который использовался в текущем сеансе последним.</span><span class="sxs-lookup"><span data-stu-id="6f467-116">This command exports the names of Windows PowerShell snap-ins from current session to the Windows PowerShell console file that was most recently used in the current session.</span></span>
<span data-ttu-id="6f467-117">Содержимое файла перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="6f467-117">It overwrites the previous file contents.</span></span>

<span data-ttu-id="6f467-118">Если экспорт файла консоли в текущем сеансе не производился, пользователю предлагается подтвердить выполнение команды, а затем ввести имя файла.</span><span class="sxs-lookup"><span data-stu-id="6f467-118">If you have not exported a console file during the current session, you are prompted for permission to continue and then prompted for a file name.</span></span>

### <span data-ttu-id="6f467-119">Пример 3. Добавление оснастки и экспорт имен оснасток</span><span class="sxs-lookup"><span data-stu-id="6f467-119">Example 3: Add a snap-in and export the names of snap-ins</span></span>

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

<span data-ttu-id="6f467-120">Эти команды добавляют новую оснастку Windows PowerShell NewPSSnapin в текущий сеанс, экспортируют имена оснасток Windows PowerShell в текущем сеансе в файл консоли и запускают сеанс Windows PowerShell с использованием файла консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-120">These commands add the NewPSSnapin Windows PowerShell snap-in to the current session, export the names of Windows PowerShell snap-ins in the current session to a console file, and then start a Windows PowerShell session with the console file.</span></span>

<span data-ttu-id="6f467-121">Первая команда добавляет оснастку NewPSSnapin к текущему сеансу с помощью командлета **Add-PSSnapin** .</span><span class="sxs-lookup"><span data-stu-id="6f467-121">The first command uses the **Add-PSSnapin** cmdlet to add the NewPSSnapin snap-in to the current session.</span></span>
<span data-ttu-id="6f467-122">Добавлять можно только те оснастки Windows PowerShell, которые зарегистрированы в данной системе.</span><span class="sxs-lookup"><span data-stu-id="6f467-122">You can only add Windows PowerShell snap-ins that are registered on your system.</span></span>

<span data-ttu-id="6f467-123">Вторая команда экспортирует имена оснасток Windows PowerShell в файл NewPSSnapinConsole.psc1.</span><span class="sxs-lookup"><span data-stu-id="6f467-123">The second command exports the Windows PowerShell snap-in names to the NewPSSnapinConsole.psc1 file.</span></span>

<span data-ttu-id="6f467-124">Третья команда запускает Windows PowerShell с использованием файла NewPSSnapinConsole.psc1.</span><span class="sxs-lookup"><span data-stu-id="6f467-124">The third command starts Windows PowerShell with the NewPSSnapinConsole.psc1 file.</span></span>
<span data-ttu-id="6f467-125">Поскольку файл консоли включает имя оснастки Windows PowerShell, в текущем сеансе можно использовать командлеты и поставщики, которые поддерживаются оснасткой.</span><span class="sxs-lookup"><span data-stu-id="6f467-125">Because the console file includes the Windows PowerShell snap-in name, the cmdlets and providers in the snap-in are available in the current session.</span></span>

### <span data-ttu-id="6f467-126">Пример 4. экспорт имен оснасток в указанное расположение</span><span class="sxs-lookup"><span data-stu-id="6f467-126">Example 4: Export names of snap-ins to a specified location</span></span>

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

<span data-ttu-id="6f467-127">Эта команда экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл Console01.psc1 в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6f467-127">This command exports the names of the Windows PowerShell snap-ins in the current session to the Console01.psc1 file in the current directory.</span></span>

<span data-ttu-id="6f467-128">Вторая команда отображает содержимое файла Console01.psc1 в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="6f467-128">The second command displays the contents of the Console01.psc1 file in Notepad.</span></span>

### <span data-ttu-id="6f467-129">Пример 5. Определение файла консоли для обновления</span><span class="sxs-lookup"><span data-stu-id="6f467-129">Example 5: Determine the console file to update</span></span>

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

<span data-ttu-id="6f467-130">В этом примере показано, как использовать автоматическую переменную $ConsoleFileName для определения файла консоли, который будет обновлен при использовании командлета **Export-Console** без значения параметра *path* .</span><span class="sxs-lookup"><span data-stu-id="6f467-130">This example shows how to use the $ConsoleFileName automatic variable to determine the console file that will be updated if you use **Export-Console** without a *Path* parameter value.</span></span>

<span data-ttu-id="6f467-131">Первая команда использует параметр *PSConsoleFile* PowerShell.exe, чтобы открыть Windows PowerShell с помощью файла Console01. psc1.</span><span class="sxs-lookup"><span data-stu-id="6f467-131">The first command uses the *PSConsoleFile* parameter of PowerShell.exe to open Windows PowerShell with the Console01.psc1 file.</span></span>

<span data-ttu-id="6f467-132">Вторая команда использует командлет **Add-PSSnapin** для добавления оснастки Миснапин Windows PowerShell к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="6f467-132">The second command uses the **Add-PSSnapin** cmdlet to add the MySnapin Windows PowerShell snap-in to the current session.</span></span>

<span data-ttu-id="6f467-133">Третья команда использует командлет **Export-Console** для экспорта имен всех оснасток Windows PowerShell в сеансе в файл невконсоле. psc1.</span><span class="sxs-lookup"><span data-stu-id="6f467-133">The third command uses the **Export-Console** cmdlet to export the names of all the Windows PowerShell snap-ins in the session to the NewConsole.psc1 file.</span></span>

<span data-ttu-id="6f467-134">Четвертая команда отображает переменную $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="6f467-134">The fourth command displays the $ConsoleFileName variable.</span></span>
<span data-ttu-id="6f467-135">Он содержит последний использовавшийся файл консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-135">It contains the most recently used console file.</span></span>
<span data-ttu-id="6f467-136">Пример выходных данных показывает, что последним использовался файл NewConsole.ps1.</span><span class="sxs-lookup"><span data-stu-id="6f467-136">The sample output shows that NewConsole.ps1 is the most recently used file.</span></span>

<span data-ttu-id="6f467-137">Пятая команда добавляет в текущую консоль оснастку SnapIn03.</span><span class="sxs-lookup"><span data-stu-id="6f467-137">The fifth command adds SnapIn03 to the current console.</span></span>

<span data-ttu-id="6f467-138">Шестая команда использует командлет **Export-Console** без параметра *path* .</span><span class="sxs-lookup"><span data-stu-id="6f467-138">The sixth command uses the **Export-Console** cmdlet without a *Path* parameter.</span></span>
<span data-ttu-id="6f467-139">Эта команда экспортирует имена всех Windows PowerShell оснасток в текущем сеансе в последний использованный файл (в данном случае NewConsole.psc1).</span><span class="sxs-lookup"><span data-stu-id="6f467-139">This command exports the names of all the Windows PowerShell snap-ins in the current session to the most recently used file, NewConsole.psc1.</span></span>

## <span data-ttu-id="6f467-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6f467-140">PARAMETERS</span></span>

### <span data-ttu-id="6f467-141">-Force</span><span class="sxs-lookup"><span data-stu-id="6f467-141">-Force</span></span>
<span data-ttu-id="6f467-142">Указывает, что этот командлет перезаписывает данные в файле консоли без предупреждения, даже если файл имеет атрибут "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="6f467-142">Indicates that this cmdlet overwrites the data in a console file without warning, even if the file has the read-only attribute.</span></span>
<span data-ttu-id="6f467-143">Атрибут только для чтения изменяется и не сбрасывается после завершения команды.</span><span class="sxs-lookup"><span data-stu-id="6f467-143">The read-only attribute is changed and is not reset when the command finishes.</span></span>

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

### <span data-ttu-id="6f467-144">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="6f467-144">-NoClobber</span></span>
<span data-ttu-id="6f467-145">Указывает, что этот командлет не перезаписывает существующий файл консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-145">Indicates that this cmdlet does not overwrite  an existing console file.</span></span>
<span data-ttu-id="6f467-146">По умолчанию, если файл выполняется по указанному пути, **Export-Console** перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6f467-146">By default, if a file occurs in the specified path, **Export-Console** overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6f467-147">-Path</span><span class="sxs-lookup"><span data-stu-id="6f467-147">-Path</span></span>
<span data-ttu-id="6f467-148">Определяет путь и имя файла для файла консоли (\*.psc1).</span><span class="sxs-lookup"><span data-stu-id="6f467-148">Specifies a path and file name for the console file (\*.psc1).</span></span>
<span data-ttu-id="6f467-149">Введите необязательный путь и имя.</span><span class="sxs-lookup"><span data-stu-id="6f467-149">Enter an optional path and name.</span></span>
<span data-ttu-id="6f467-150">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="6f467-150">Wildcard characters are not permitted.</span></span>

<span data-ttu-id="6f467-151">Если указано только имя файла, **Export-Console** создает файл с таким именем и расширением имени файла PSC1 в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6f467-151">If you specify only a file name, **Export-Console** creates a file that has that name and the .psc1 file name extension in the current directory.</span></span>

<span data-ttu-id="6f467-152">Этот параметр является обязательным, если вы не открывали Windows PowerShell с параметром *PSConsoleFile* или не экспортировали файл консоли во время текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6f467-152">This parameter is required unless you have opened Windows PowerShell with the *PSConsoleFile* parameter or exported a console file during the current session.</span></span>
<span data-ttu-id="6f467-153">Он также необходим при использовании параметра *NoClobber* , чтобы предотвратить перезапись текущего файла консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-153">It is also required when you use the *NoClobber* parameter to prevent the current console file from being overwritten.</span></span>

<span data-ttu-id="6f467-154">Если этот параметр не указан, **Export-Console** перезаписывает файл консоли, который использовался в последнее время в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="6f467-154">If you omit this parameter, **Export-Console** overwrites the console file that was used most recently in this session.</span></span>
<span data-ttu-id="6f467-155">Путь к последнему используемому файлу консоли хранится в значении автоматической переменной $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="6f467-155">The path of the most recently used console file is stored in the value of the $ConsoleFileName automatic variable.</span></span>
<span data-ttu-id="6f467-156">Дополнительные сведения см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="6f467-156">For more information, see about_Automatic_Variables.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6f467-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6f467-157">-Confirm</span></span>
<span data-ttu-id="6f467-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6f467-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6f467-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6f467-159">-WhatIf</span></span>
<span data-ttu-id="6f467-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6f467-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6f467-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6f467-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6f467-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6f467-162">CommonParameters</span></span>
<span data-ttu-id="6f467-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6f467-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6f467-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6f467-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6f467-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6f467-165">INPUTS</span></span>

### <span data-ttu-id="6f467-166">System.String</span><span class="sxs-lookup"><span data-stu-id="6f467-166">System.String</span></span>
<span data-ttu-id="6f467-167">Строку пути можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6f467-167">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="6f467-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6f467-168">OUTPUTS</span></span>

### <span data-ttu-id="6f467-169">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="6f467-169">System.IO.FileInfo</span></span>
<span data-ttu-id="6f467-170">Этот командлет создает файл, содержащий экспортированные псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="6f467-170">This cmdlet creates a file that contains the exported aliases.</span></span>

## <span data-ttu-id="6f467-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6f467-171">NOTES</span></span>

* <span data-ttu-id="6f467-172">Если файл консоли (PSC1) используется для запуска сеанса, имя этого файла автоматически сохраняются в автоматической переменной $ConsoleFileName.</span><span class="sxs-lookup"><span data-stu-id="6f467-172">When a console file (.psc1) is used to start the session, the name of the console file is automatically stored in the $ConsoleFileName automatic variable.</span></span> <span data-ttu-id="6f467-173">Значение $ConsoleFileName обновляется при использовании параметра *path* командлета **Export-Console** для указания нового файла консоли.</span><span class="sxs-lookup"><span data-stu-id="6f467-173">The value of $ConsoleFileName is updated when you use the *Path* parameter of **Export-Console** to specify a new console file.</span></span> <span data-ttu-id="6f467-174">Если файл консоли не используется, $ConsoleFileName не имеет значения ($Null).</span><span class="sxs-lookup"><span data-stu-id="6f467-174">When no console file is used, $ConsoleFileName has no value ($Null).</span></span>

  <span data-ttu-id="6f467-175">Чтобы использовать файл консоли Windows PowerShell в новом сеансе, запустите Windows PowerShell с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="6f467-175">To use a Windows PowerShell console file in a new session, use the following syntax to start Windows PowerShell:</span></span>

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  <span data-ttu-id="6f467-176">Оснастки Windows PowerShell можно также сохранить для будущих сеансов, добавив команду Add-PSSnapin в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f467-176">You can also save Windows PowerShell snap-ins for future sessions by adding an Add-PSSnapin command to your Windows PowerShell profile.</span></span>
<span data-ttu-id="6f467-177">Дополнительные сведения см. в разделе about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="6f467-177">For more information, see about_Profiles.</span></span>


## <span data-ttu-id="6f467-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6f467-178">RELATED LINKS</span></span>

[<span data-ttu-id="6f467-179">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6f467-179">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="6f467-180">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6f467-180">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="6f467-181">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6f467-181">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
