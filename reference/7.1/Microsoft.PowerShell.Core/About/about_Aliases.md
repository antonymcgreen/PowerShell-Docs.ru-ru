---
description: Описание использования альтернативных имен для командлетов и команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 9213bd41af6d5383c7e67d33b8909736a6e380bb
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391295"
---
# <a name="about-aliases"></a><span data-ttu-id="325f2-104">About Aliases (О псевдонимах)</span><span class="sxs-lookup"><span data-stu-id="325f2-104">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="325f2-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="325f2-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="325f2-106">Описание использования альтернативных имен для командлетов и команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="325f2-106">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="325f2-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="325f2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="325f2-108">Псевдоним — это альтернативное имя или псевдоним для командлета или для элемента Command, например функции, скрипта, файла или исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="325f2-108">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="325f2-109">Вместо имени команды в командах PowerShell можно использовать псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-109">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="325f2-110">Чтобы создать псевдоним, используйте командлет New-Alias.</span><span class="sxs-lookup"><span data-stu-id="325f2-110">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="325f2-111">Например, следующая команда создает псевдоним "газов" для `Get-AuthenticodeSignature` командлета:</span><span class="sxs-lookup"><span data-stu-id="325f2-111">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="325f2-112">После создания псевдонима для имени командлета можно использовать псевдоним вместо имени командлета.</span><span class="sxs-lookup"><span data-stu-id="325f2-112">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="325f2-113">Например, чтобы получить подпись Authenticode для файла SqlScript.ps1, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-113">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="325f2-114">Или введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-114">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="325f2-115">При создании слова "Word" в качестве псевдонима для Microsoft Office Word можно ввести "Word" вместо следующего:</span><span class="sxs-lookup"><span data-stu-id="325f2-115">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="325f2-116">ВСТРОЕННЫЕ ПСЕВДОНИМЫ</span><span class="sxs-lookup"><span data-stu-id="325f2-116">BUILT-IN ALIASES</span></span>

<span data-ttu-id="325f2-117">PowerShell включает набор встроенных псевдонимов, включая "CD" и "chdir" для командлета Set-Location, а также "ls" и "Dir" для командлета Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="325f2-117">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="325f2-118">Чтобы получить все псевдонимы на компьютере, включая встроенные псевдонимы, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-118">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="325f2-119">КОМАНДЛЕТЫ ALIAS</span><span class="sxs-lookup"><span data-stu-id="325f2-119">ALIAS CMDLETS</span></span>

<span data-ttu-id="325f2-120">PowerShell включает следующие командлеты, предназначенные для работы с псевдонимами:</span><span class="sxs-lookup"><span data-stu-id="325f2-120">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="325f2-121">`Get-Alias` — Получает все псевдонимы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="325f2-121">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="325f2-122">`New-Alias` — Создает новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-122">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="325f2-123">`Set-Alias` — Создает или изменяет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-123">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="325f2-124">`Export-Alias` — Экспортирует один или несколько псевдонимов в файл.</span><span class="sxs-lookup"><span data-stu-id="325f2-124">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="325f2-125">`Import-Alias` — Импортирует файл псевдонима в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="325f2-125">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="325f2-126">Для получения подробных сведений о командлетах введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-126">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="325f2-127">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-127">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="325f2-128">СОЗДАНИЕ ПСЕВДОНИМА</span><span class="sxs-lookup"><span data-stu-id="325f2-128">CREATING AN ALIAS</span></span>

<span data-ttu-id="325f2-129">Чтобы создать новый псевдоним, используйте командлет New-Alias.</span><span class="sxs-lookup"><span data-stu-id="325f2-129">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="325f2-130">Например, чтобы создать псевдоним "GH" для Get-Help, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-130">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="325f2-131">Псевдоним можно использовать в командах так же, как и полное имя командлета, и можно использовать псевдоним с параметрами.</span><span class="sxs-lookup"><span data-stu-id="325f2-131">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="325f2-132">Например, чтобы получить подробную справку по командлету Get-WmiObject, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-132">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="325f2-133">Или введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-133">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="325f2-134">СОХРАНЕНИЕ ПСЕВДОНИМОВ</span><span class="sxs-lookup"><span data-stu-id="325f2-134">SAVING ALIASES</span></span>

<span data-ttu-id="325f2-135">Создаваемые псевдонимы сохраняются только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="325f2-135">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="325f2-136">Чтобы использовать псевдонимы в другом сеансе, добавьте псевдоним в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="325f2-136">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="325f2-137">Или используйте командлет Export-Alias, чтобы сохранить псевдонимы в файл.</span><span class="sxs-lookup"><span data-stu-id="325f2-137">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="325f2-138">Чтобы получить дополнительные сведения, введите: </span><span class="sxs-lookup"><span data-stu-id="325f2-138">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="325f2-139">ПОЛУЧЕНИЕ ПСЕВДОНИМОВ</span><span class="sxs-lookup"><span data-stu-id="325f2-139">GETTING ALIASES</span></span>

<span data-ttu-id="325f2-140">Чтобы получить все псевдонимы в текущем сеансе, включая встроенные псевдонимы, псевдонимы в профилях PowerShell и псевдонимы, созданные в текущем сеансе, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-140">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="325f2-141">Чтобы получить конкретные псевдонимы, используйте параметр Name командлета Get-Alias.</span><span class="sxs-lookup"><span data-stu-id="325f2-141">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="325f2-142">Например, чтобы получить псевдонимы, начинающиеся с "p", введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-142">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="325f2-143">Чтобы получить псевдонимы для определенного элемента, используйте параметр определения.</span><span class="sxs-lookup"><span data-stu-id="325f2-143">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="325f2-144">Например, чтобы получить псевдонимы для типа командлета Get-ChildItem:</span><span class="sxs-lookup"><span data-stu-id="325f2-144">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="325f2-145">ПОЛУЧЕНИЕ ВЫХОДНОГО ПСЕВДОНИМА</span><span class="sxs-lookup"><span data-stu-id="325f2-145">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="325f2-146">Get-Alias возвращает только один тип объекта — объект AliasInfo (System. Management. Automation. AliasInfo).</span><span class="sxs-lookup"><span data-stu-id="325f2-146">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="325f2-147">Имена псевдонимов, которые не содержат дефис, например "CD", отображаются в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="325f2-147">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="325f2-148">Это позволяет быстро и легко получить необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="325f2-148">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="325f2-149">Формат имени псевдонима со стрелками не используется для псевдонимов, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="325f2-149">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="325f2-150">Они, скорее всего, являются предпочтительными заменяемыми именами для командлетов и функций, а не стандартных сокращений или псевдонимов, и автор может не потребовать от них очевидного.</span><span class="sxs-lookup"><span data-stu-id="325f2-150">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="325f2-151">АЛЬТЕРНАТИВНЫЕ ИМЕНА ДЛЯ КОМАНД С ПАРАМЕТРАМИ</span><span class="sxs-lookup"><span data-stu-id="325f2-151">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="325f2-152">Можно назначить псевдоним командлету, сценарию, функции или исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="325f2-152">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="325f2-153">Нельзя назначить псевдоним для команды и ее параметров.</span><span class="sxs-lookup"><span data-stu-id="325f2-153">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="325f2-154">Например, можно присвоить `Get-Eventlog` командлету псевдоним, но нельзя присвоить `Get-Eventlog -LogName System` команде псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-154">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="325f2-155">Можно создать функцию, которая включает команду.</span><span class="sxs-lookup"><span data-stu-id="325f2-155">You can create a function that includes the command.</span></span> <span data-ttu-id="325f2-156">Чтобы создать функцию, введите слово "Function", за которым следует имя функции.</span><span class="sxs-lookup"><span data-stu-id="325f2-156">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="325f2-157">Введите команду и заключите ее в фигурные скобки ( {} ).</span><span class="sxs-lookup"><span data-stu-id="325f2-157">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="325f2-158">Например, следующая команда создает функцию syslog.</span><span class="sxs-lookup"><span data-stu-id="325f2-158">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="325f2-159">Эта функция представляет `Get-Eventlog -LogName System` команду:</span><span class="sxs-lookup"><span data-stu-id="325f2-159">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="325f2-160">Теперь можно ввести "syslog" вместо команды.</span><span class="sxs-lookup"><span data-stu-id="325f2-160">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="325f2-161">И можно создавать псевдонимы для новой функции.</span><span class="sxs-lookup"><span data-stu-id="325f2-161">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="325f2-162">Для получения дополнительных сведений о функциях введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-162">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="325f2-163">ПСЕВДОНИМЫ ОБЪЕКТОВ</span><span class="sxs-lookup"><span data-stu-id="325f2-163">ALIAS OBJECTS</span></span>

<span data-ttu-id="325f2-164">Псевдонимы PowerShell представлены объектами, которые являются экземплярами класса System. Management. Automation. AliasInfo.</span><span class="sxs-lookup"><span data-stu-id="325f2-164">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="325f2-165">Дополнительные сведения об этом типе объектов см. в разделе [класс AliasInfo][aliasinfo] в пакете SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="325f2-165">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the PowerShell SDK.</span></span>

<span data-ttu-id="325f2-166">Чтобы просмотреть свойства и методы объектов псевдонима, получите псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="325f2-166">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="325f2-167">Затем передаем их в командлет Get-Member.</span><span class="sxs-lookup"><span data-stu-id="325f2-167">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="325f2-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="325f2-168">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="325f2-169">Чтобы просмотреть значения свойств определенного псевдонима, например `dir` псевдонима, получите псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-169">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="325f2-170">Затем передаем его в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="325f2-170">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="325f2-171">Например, следующая команда возвращает псевдоним Dir.</span><span class="sxs-lookup"><span data-stu-id="325f2-171">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="325f2-172">Затем команда передает псевдоним в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="325f2-172">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="325f2-173">Затем команда использует параметр Property объекта Format-List с подстановочным знаком ( \* ) для вывода всех свойств `dir` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="325f2-173">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="325f2-174">Следующая команда выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="325f2-174">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="325f2-175">Поставщик ПСЕВДОНИМов PowerShell</span><span class="sxs-lookup"><span data-stu-id="325f2-175">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="325f2-176">В PowerShell имеется поставщик псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="325f2-176">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="325f2-177">Поставщик псевдонимов позволяет просматривать псевдонимы в PowerShell, как будто они находятся на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="325f2-177">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="325f2-178">Поставщик псевдонимов предоставляет диск Alias:.</span><span class="sxs-lookup"><span data-stu-id="325f2-178">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="325f2-179">Чтобы войти в диск Alias:, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-179">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="325f2-180">Чтобы просмотреть содержимое диска, введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-180">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="325f2-181">Чтобы просмотреть содержимое диска с другого диска PowerShell, Начните путь с имени диска.</span><span class="sxs-lookup"><span data-stu-id="325f2-181">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="325f2-182">Добавьте двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="325f2-182">Include the colon (:).</span></span> <span data-ttu-id="325f2-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="325f2-183">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="325f2-184">Чтобы получить сведения о конкретном псевдониме, введите имя диска и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="325f2-184">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="325f2-185">Или введите шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="325f2-185">Or, type a name pattern.</span></span> <span data-ttu-id="325f2-186">Например, чтобы получить все псевдонимы, начинающиеся с "p", введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-186">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="325f2-187">Для получения дополнительных сведений о поставщике псевдонимов PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="325f2-187">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="325f2-188">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="325f2-188">SEE ALSO</span></span>

- [<span data-ttu-id="325f2-189">New-Alias</span><span class="sxs-lookup"><span data-stu-id="325f2-189">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="325f2-190">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="325f2-190">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="325f2-191">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="325f2-191">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="325f2-192">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="325f2-192">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="325f2-193">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="325f2-193">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="325f2-194">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="325f2-194">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="325f2-195">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="325f2-195">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="325f2-196">about_functions</span><span class="sxs-lookup"><span data-stu-id="325f2-196">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="325f2-197">about_profiles</span><span class="sxs-lookup"><span data-stu-id="325f2-197">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="325f2-198">about_providers</span><span class="sxs-lookup"><span data-stu-id="325f2-198">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
