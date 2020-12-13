---
description: Объясняет языковые режимы и их воздействие на сеансы PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 91e3021c854945d86822c5d8219542eff7118aa7
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625658"
---
# <a name="about-language-modes"></a><span data-ttu-id="fac2d-104">Сведения о языковых режимах</span><span class="sxs-lookup"><span data-stu-id="fac2d-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="fac2d-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fac2d-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="fac2d-106">Объясняет языковые режимы и их воздействие на сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fac2d-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="fac2d-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fac2d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="fac2d-108">Языковой режим сеанса PowerShell определяет, в части которого элементы языка PowerShell можно использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fac2d-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="fac2d-109">PowerShell поддерживает следующие языковые режимы:</span><span class="sxs-lookup"><span data-stu-id="fac2d-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="fac2d-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="fac2d-110">FullLanguage</span></span>
- <span data-ttu-id="fac2d-111">ConstrainedLanguage (введено в PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="fac2d-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="fac2d-112">рестриктедлангуаже</span><span class="sxs-lookup"><span data-stu-id="fac2d-112">RestrictedLanguage</span></span>
- <span data-ttu-id="fac2d-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="fac2d-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="fac2d-114">ЧТО ТАКОЕ ЯЗЫКОВОЙ РЕЖИМ?</span><span class="sxs-lookup"><span data-stu-id="fac2d-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="fac2d-115">Языковой режим определяет языковые элементы, разрешенные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fac2d-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="fac2d-116">Языковой режим фактически является свойством конфигурации сеанса (или "конечной точки"), используемой для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="fac2d-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="fac2d-117">Все сеансы, использующие определенную конфигурацию сеанса, имеют языковой режим конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fac2d-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="fac2d-118">Все сеансы PowerShell имеют языковой режим, включая PSSession, созданные с помощью `New-PSSession` командлета, временные сеансы, которые используют параметр ComputerName, и сеансы по умолчанию, которые отображаются при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fac2d-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="fac2d-119">Удаленные сеансы создаются с помощью конфигураций сеансов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fac2d-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="fac2d-120">Языковой режим, заданный в конфигурации сеанса, определяет языковой режим сеанса.</span><span class="sxs-lookup"><span data-stu-id="fac2d-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="fac2d-121">Чтобы указать конфигурацию сеанса PSSession, используйте параметр ConfigurationName командлетов, которые создают сеанс.</span><span class="sxs-lookup"><span data-stu-id="fac2d-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="fac2d-122">ЯЗЫКОВЫЕ РЕЖИМЫ</span><span class="sxs-lookup"><span data-stu-id="fac2d-122">LANGUAGE MODES</span></span>

<span data-ttu-id="fac2d-123">В этом разделе описываются языковые режимы в сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fac2d-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="fac2d-124">ПОЛНЫЙ язык (Фулллангуаже)</span><span class="sxs-lookup"><span data-stu-id="fac2d-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="fac2d-125">Режим Фулллангуаже позволяет использовать все языковые элементы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fac2d-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="fac2d-126">Фулллангуаже — это языковой режим по умолчанию для сеансов по умолчанию во всех версиях Windows, за исключением Windows RT.</span><span class="sxs-lookup"><span data-stu-id="fac2d-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="fac2d-127">ОГРАНИЧЕНный язык (Рестриктедлангуаже)</span><span class="sxs-lookup"><span data-stu-id="fac2d-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="fac2d-128">В режиме Рестриктедлангуаже пользователи могут выполнять команды (командлеты, функции, команды CIM и рабочие процессы), но не могут использовать блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="fac2d-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="fac2d-129">По умолчанию в режиме Рестриктедлангуаже разрешены только следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="fac2d-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="fac2d-130">Допустимы только следующие операторы сравнения:</span><span class="sxs-lookup"><span data-stu-id="fac2d-130">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="fac2d-131">`-eq` равномерно</span><span class="sxs-lookup"><span data-stu-id="fac2d-131">`-eq` (equal)</span></span>
- <span data-ttu-id="fac2d-132">`-gt` (больше)</span><span class="sxs-lookup"><span data-stu-id="fac2d-132">`-gt` (greater-than)</span></span>
- <span data-ttu-id="fac2d-133">`-lt` (меньше)</span><span class="sxs-lookup"><span data-stu-id="fac2d-133">`-lt` (less-than)</span></span>

<span data-ttu-id="fac2d-134">Операторы присваивания, ссылки на свойство и вызовы методов не разрешены.</span><span class="sxs-lookup"><span data-stu-id="fac2d-134">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="fac2d-135">НЕТ языка (язык)</span><span class="sxs-lookup"><span data-stu-id="fac2d-135">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="fac2d-136">Режим "неязыкового интерфейса" можно использовать только через API.</span><span class="sxs-lookup"><span data-stu-id="fac2d-136">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="fac2d-137">Режим без языка означает, что текст скрипта для любой формы не разрешен.</span><span class="sxs-lookup"><span data-stu-id="fac2d-137">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="fac2d-138">Это исключает использование метода **аддскрипт ()** , который отправляет фрагменты сценария PowerShell для синтаксического анализа и выполнения.</span><span class="sxs-lookup"><span data-stu-id="fac2d-138">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="fac2d-139">Можно использовать только **AddCommand ()** и **аддпараметер ()** , которые не проходят через средство синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="fac2d-139">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="fac2d-140">ОГРАНИЧЕНный язык (ограниченный язык)</span><span class="sxs-lookup"><span data-stu-id="fac2d-140">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="fac2d-141">Режим ConstrainedLanguage позволяет использовать все командлеты и все элементы языка PowerShell, но ограничивает разрешенные типы.</span><span class="sxs-lookup"><span data-stu-id="fac2d-141">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="fac2d-142">Режим ConstrainedLanguage предназначен для поддержки целостности кода пользовательского режима (УМЦИ) в Windows RT.</span><span class="sxs-lookup"><span data-stu-id="fac2d-142">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="fac2d-143">Это единственный поддерживаемый языковой режим в Windows RT, но он доступен во всех поддерживаемых системах.</span><span class="sxs-lookup"><span data-stu-id="fac2d-143">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="fac2d-144">УМЦИ защищает устройства ARM, разрешая установку на устройствах с Windows RT только приложений, подписанных корпорацией Майкрософт и сертифицированных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fac2d-144">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="fac2d-145">Режим ConstrainedLanguage запрещает пользователям использовать PowerShell для обхода или нарушения правил УМЦИ.</span><span class="sxs-lookup"><span data-stu-id="fac2d-145">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="fac2d-146">Ниже приведены функции режима ConstrainedLanguage.</span><span class="sxs-lookup"><span data-stu-id="fac2d-146">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="fac2d-147">Все командлеты в модулях Windows и другие командлеты, утвержденные УМЦИ, полностью работоспособны и имеют полный доступ к системным ресурсам, за исключением указанных.</span><span class="sxs-lookup"><span data-stu-id="fac2d-147">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="fac2d-148">Разрешены все элементы языка сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fac2d-148">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="fac2d-149">Все модули, входящие в Windows, можно импортировать, а также все команды, выполняемые при экспорте модулей в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fac2d-149">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="fac2d-150">В рабочем процессе PowerShell можно создавать и запускать рабочие процессы скриптов (рабочие процессы, написанные на языке PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fac2d-150">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="fac2d-151">Рабочие процессы на основе XAML не поддерживаются, и вы не можете запускать XAML в рабочем процессе скрипта, например с помощью `Invoke-Expression -Language XAML` .</span><span class="sxs-lookup"><span data-stu-id="fac2d-151">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="fac2d-152">Кроме того, рабочие процессы не могут вызывать другие рабочие процессы, хотя разрешены вложенные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="fac2d-152">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="fac2d-153">`Add-Type`Командлет может загружать подписанные сборки, но не может загрузить произвольный код C# или API-интерфейсы Win32.</span><span class="sxs-lookup"><span data-stu-id="fac2d-153">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="fac2d-154">`New-Object`Командлет можно использовать только для допустимых типов (перечисленных ниже).</span><span class="sxs-lookup"><span data-stu-id="fac2d-154">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="fac2d-155">В PowerShell можно использовать только допустимые типы (перечисленные ниже).</span><span class="sxs-lookup"><span data-stu-id="fac2d-155">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="fac2d-156">Другие типы не допускаются.</span><span class="sxs-lookup"><span data-stu-id="fac2d-156">Other types are not permitted.</span></span>

- <span data-ttu-id="fac2d-157">Преобразование типов разрешено, но только если результатом является допустимый тип.</span><span class="sxs-lookup"><span data-stu-id="fac2d-157">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="fac2d-158">Параметры командлета, которые преобразуют входные данные строки в типы, работают только в том случае, если результирующий тип является допустимым типом.</span><span class="sxs-lookup"><span data-stu-id="fac2d-158">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="fac2d-159">Можно вызвать метод **ToString ()** и методы .NET допустимых типов (перечисленных ниже).</span><span class="sxs-lookup"><span data-stu-id="fac2d-159">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="fac2d-160">Невозможно вызвать другие методы.</span><span class="sxs-lookup"><span data-stu-id="fac2d-160">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="fac2d-161">Пользователи могут получить все свойства разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="fac2d-161">Users can get all properties of allowed types.</span></span> <span data-ttu-id="fac2d-162">Пользователи могут устанавливать значения свойств только для основных типов.</span><span class="sxs-lookup"><span data-stu-id="fac2d-162">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="fac2d-163">Разрешены только следующие объекты COM:</span><span class="sxs-lookup"><span data-stu-id="fac2d-163">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="fac2d-164">**Скрипт. словарь**</span><span class="sxs-lookup"><span data-stu-id="fac2d-164">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="fac2d-165">**Scripting.FileSystemObject;**</span><span class="sxs-lookup"><span data-stu-id="fac2d-165">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="fac2d-166">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="fac2d-166">**VBScript.RegExp**</span></span>

<span data-ttu-id="fac2d-167">В режиме ConstrainedLanguage разрешены следующие типы.</span><span class="sxs-lookup"><span data-stu-id="fac2d-167">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="fac2d-168">Пользователи могут получать свойства, вызывать методы и преобразовывать объекты в эти типы.</span><span class="sxs-lookup"><span data-stu-id="fac2d-168">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="fac2d-169">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="fac2d-169">Allowed Types:</span></span>

- <span data-ttu-id="fac2d-170">алиасаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-170">AliasAttribute</span></span>
- <span data-ttu-id="fac2d-171">алловемптиколлектионаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-171">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="fac2d-172">алловемптистрингаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-172">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="fac2d-173">алловнуллаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-173">AllowNullAttribute</span></span>
- <span data-ttu-id="fac2d-174">Массив</span><span class="sxs-lookup"><span data-stu-id="fac2d-174">Array</span></span>
- <span data-ttu-id="fac2d-175">Bool</span><span class="sxs-lookup"><span data-stu-id="fac2d-175">Bool</span></span>
- <span data-ttu-id="fac2d-176">byte</span><span class="sxs-lookup"><span data-stu-id="fac2d-176">byte</span></span>
- <span data-ttu-id="fac2d-177">char</span><span class="sxs-lookup"><span data-stu-id="fac2d-177">char</span></span>
- <span data-ttu-id="fac2d-178">кмдлетбиндингаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-178">CmdletBindingAttribute</span></span>
- <span data-ttu-id="fac2d-179">Дата/время</span><span class="sxs-lookup"><span data-stu-id="fac2d-179">DateTime</span></span>
- <span data-ttu-id="fac2d-180">Decimal</span><span class="sxs-lookup"><span data-stu-id="fac2d-180">decimal</span></span>
- <span data-ttu-id="fac2d-181">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="fac2d-181">DirectoryEntry</span></span>
- <span data-ttu-id="fac2d-182">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="fac2d-182">DirectorySearcher</span></span>
- <span data-ttu-id="fac2d-183">double</span><span class="sxs-lookup"><span data-stu-id="fac2d-183">double</span></span>
- <span data-ttu-id="fac2d-184">FLOAT</span><span class="sxs-lookup"><span data-stu-id="fac2d-184">float</span></span>
- <span data-ttu-id="fac2d-185">Guid</span><span class="sxs-lookup"><span data-stu-id="fac2d-185">Guid</span></span>
- <span data-ttu-id="fac2d-186">Хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="fac2d-186">Hashtable</span></span>
- <span data-ttu-id="fac2d-187">INT</span><span class="sxs-lookup"><span data-stu-id="fac2d-187">int</span></span>
- <span data-ttu-id="fac2d-188">Int16</span><span class="sxs-lookup"><span data-stu-id="fac2d-188">Int16</span></span>
- <span data-ttu-id="fac2d-189">long</span><span class="sxs-lookup"><span data-stu-id="fac2d-189">long</span></span>
- <span data-ttu-id="fac2d-190">манажементкласс</span><span class="sxs-lookup"><span data-stu-id="fac2d-190">ManagementClass</span></span>
- <span data-ttu-id="fac2d-191">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="fac2d-191">ManagementObject</span></span>
- <span data-ttu-id="fac2d-192">манажементобжектсеарчер</span><span class="sxs-lookup"><span data-stu-id="fac2d-192">ManagementObjectSearcher</span></span>
- <span data-ttu-id="fac2d-193">нуллстринг</span><span class="sxs-lookup"><span data-stu-id="fac2d-193">NullString</span></span>
- <span data-ttu-id="fac2d-194">аутпуттипеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-194">OutputTypeAttribute</span></span>
- <span data-ttu-id="fac2d-195">параметераттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-195">ParameterAttribute</span></span>
- <span data-ttu-id="fac2d-196">PSCredential</span><span class="sxs-lookup"><span data-stu-id="fac2d-196">PSCredential</span></span>
- <span data-ttu-id="fac2d-197">псдефаултвалуеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-197">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="fac2d-198">пслистмодифиер</span><span class="sxs-lookup"><span data-stu-id="fac2d-198">PSListModifier</span></span>
- <span data-ttu-id="fac2d-199">PSObject</span><span class="sxs-lookup"><span data-stu-id="fac2d-199">PSObject</span></span>
- <span data-ttu-id="fac2d-200">пспримитиведиктионари</span><span class="sxs-lookup"><span data-stu-id="fac2d-200">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="fac2d-201">псреференце</span><span class="sxs-lookup"><span data-stu-id="fac2d-201">PSReference</span></span>
- <span data-ttu-id="fac2d-202">пстипенамеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-202">PSTypeNameAttribute</span></span>
- <span data-ttu-id="fac2d-203">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="fac2d-203">Regex</span></span>
- <span data-ttu-id="fac2d-204">SByte</span><span class="sxs-lookup"><span data-stu-id="fac2d-204">SByte</span></span>
- <span data-ttu-id="fac2d-205">строка</span><span class="sxs-lookup"><span data-stu-id="fac2d-205">string</span></span>
- <span data-ttu-id="fac2d-206">суппортсвилдкардсаттрибуте</span><span class="sxs-lookup"><span data-stu-id="fac2d-206">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="fac2d-207">Параметр-переключатель</span><span class="sxs-lookup"><span data-stu-id="fac2d-207">SwitchParameter</span></span>
- <span data-ttu-id="fac2d-208">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="fac2d-208">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="fac2d-209">System .NET. IPAddress</span><span class="sxs-lookup"><span data-stu-id="fac2d-209">System.Net.IPAddress</span></span>
- <span data-ttu-id="fac2d-210">System .NET. mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="fac2d-210">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="fac2d-211">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="fac2d-211">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="fac2d-212">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="fac2d-212">System.Security.SecureString</span></span>
- <span data-ttu-id="fac2d-213">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="fac2d-213">TimeSpan</span></span>
- <span data-ttu-id="fac2d-214">UInt16</span><span class="sxs-lookup"><span data-stu-id="fac2d-214">UInt16</span></span>
- <span data-ttu-id="fac2d-215">UInt32</span><span class="sxs-lookup"><span data-stu-id="fac2d-215">UInt32</span></span>
- <span data-ttu-id="fac2d-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="fac2d-216">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="fac2d-217">ПОИСК ЯЗЫКОВОГО РЕЖИМА КОНФИГУРАЦИИ СЕАНСА</span><span class="sxs-lookup"><span data-stu-id="fac2d-217">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="fac2d-218">Если конфигурация сеанса создается с помощью файла конфигурации сеанса, то конфигурация сеанса имеет свойство Лангуажемоде.</span><span class="sxs-lookup"><span data-stu-id="fac2d-218">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="fac2d-219">Чтобы найти языковой режим, можно получить значение свойства Лангуажемоде.</span><span class="sxs-lookup"><span data-stu-id="fac2d-219">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="fac2d-220">В других конфигурациях сеанса языковой режим можно найти косвенно, находя языковой режим сеанса, созданного с помощью конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fac2d-220">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="fac2d-221">ПОИСК ЯЗЫКОВОГО РЕЖИМА СЕАНСА</span><span class="sxs-lookup"><span data-stu-id="fac2d-221">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="fac2d-222">Языковой режим сеанса Фулллангуаже или ConstrainedLanguage можно найти, получая значение свойства Лангуажемоде состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="fac2d-222">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="fac2d-223">Пример:</span><span class="sxs-lookup"><span data-stu-id="fac2d-223">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="fac2d-224">Однако в сеансах с Рестриктедлангуаже и неязыковыми режимами нельзя использовать метод Dot для получения значений свойств.</span><span class="sxs-lookup"><span data-stu-id="fac2d-224">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="fac2d-225">Вместо этого сообщение об ошибке отображает языковой режим.</span><span class="sxs-lookup"><span data-stu-id="fac2d-225">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="fac2d-226">При выполнении `$ExecutionContext.SessionState.LanguageMode` команды в сеансе Рестриктедлангуаже PowerShell возвращает сообщения об ошибках пропертиреференценотсуппортединдатасектион и вариаблереференценотсуппортединдатасектион.</span><span class="sxs-lookup"><span data-stu-id="fac2d-226">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="fac2d-227">Пропертиреференценотсуппортединдатасектион: ссылки на свойства не разрешены в ограниченном языковом режиме или в разделе данных.</span><span class="sxs-lookup"><span data-stu-id="fac2d-227">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="fac2d-228">Вариаблереференценотсуппортединдатасектион переменную, на которую нельзя ссылаться в ограниченном языковом режиме, или на раздел данных имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="fac2d-228">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="fac2d-229">При выполнении `$ExecutionContext.SessionState.LanguageMode` команды в сеансе на языке PowerShell возвращает сообщение об ошибке скриптсноталловед.</span><span class="sxs-lookup"><span data-stu-id="fac2d-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="fac2d-230">Скриптсноталловед: синтаксис не поддерживается этим пространством выполнения.</span><span class="sxs-lookup"><span data-stu-id="fac2d-230">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="fac2d-231">Это может быть вызвано тем, что он находится в неязыковом режиме.</span><span class="sxs-lookup"><span data-stu-id="fac2d-231">This might be because it is in no-language mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="fac2d-232">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="fac2d-232">SEE ALSO</span></span>

- [<span data-ttu-id="fac2d-233">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="fac2d-233">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="fac2d-234">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="fac2d-234">about_Session_Configurations</span></span>](about_Session_Configurations.md)
