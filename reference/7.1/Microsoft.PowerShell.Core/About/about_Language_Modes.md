---
description: Объясняет языковые режимы и их воздействие на сеансы PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 0b94125574bc65359b264225bb6c64231c1052d7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230885"
---
# <a name="about-language-modes"></a><span data-ttu-id="8bae9-104">Сведения о языковых режимах</span><span class="sxs-lookup"><span data-stu-id="8bae9-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="8bae9-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8bae9-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8bae9-106">Объясняет языковые режимы и их воздействие на сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bae9-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="8bae9-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8bae9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8bae9-108">Языковой режим сеанса PowerShell определяет, в части которого элементы языка PowerShell можно использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="8bae9-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="8bae9-109">PowerShell поддерживает следующие языковые режимы:</span><span class="sxs-lookup"><span data-stu-id="8bae9-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="8bae9-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-110">FullLanguage</span></span>
- <span data-ttu-id="8bae9-111">ConstrainedLanguage (введено в PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="8bae9-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="8bae9-112">рестриктедлангуаже</span><span class="sxs-lookup"><span data-stu-id="8bae9-112">RestrictedLanguage</span></span>
- <span data-ttu-id="8bae9-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="8bae9-114">ЧТО ТАКОЕ ЯЗЫКОВОЙ РЕЖИМ?</span><span class="sxs-lookup"><span data-stu-id="8bae9-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="8bae9-115">Языковой режим определяет языковые элементы, разрешенные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="8bae9-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="8bae9-116">Языковой режим фактически является свойством конфигурации сеанса (или "конечной точки"), используемой для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="8bae9-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="8bae9-117">Все сеансы, использующие определенную конфигурацию сеанса, имеют языковой режим конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8bae9-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="8bae9-118">Все сеансы PowerShell имеют языковой режим, включая PSSession, созданные с помощью `New-PSSession` командлета, временные сеансы, которые используют параметр ComputerName, и сеансы по умолчанию, которые отображаются при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bae9-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="8bae9-119">Удаленные сеансы создаются с помощью конфигураций сеансов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8bae9-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="8bae9-120">Языковой режим, заданный в конфигурации сеанса, определяет языковой режим сеанса.</span><span class="sxs-lookup"><span data-stu-id="8bae9-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="8bae9-121">Чтобы указать конфигурацию сеанса PSSession, используйте параметр ConfigurationName командлетов, которые создают сеанс.</span><span class="sxs-lookup"><span data-stu-id="8bae9-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="8bae9-122">ЯЗЫКОВЫЕ РЕЖИМЫ</span><span class="sxs-lookup"><span data-stu-id="8bae9-122">LANGUAGE MODES</span></span>

<span data-ttu-id="8bae9-123">В этом разделе описываются языковые режимы в сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bae9-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="8bae9-124">ПОЛНЫЙ язык (Фулллангуаже)</span><span class="sxs-lookup"><span data-stu-id="8bae9-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="8bae9-125">Режим Фулллангуаже позволяет использовать все языковые элементы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="8bae9-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="8bae9-126">Фулллангуаже — это языковой режим по умолчанию для сеансов по умолчанию во всех версиях Windows, за исключением Windows RT.</span><span class="sxs-lookup"><span data-stu-id="8bae9-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="8bae9-127">ОГРАНИЧЕНный язык (Рестриктедлангуаже)</span><span class="sxs-lookup"><span data-stu-id="8bae9-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="8bae9-128">В режиме Рестриктедлангуаже пользователи могут выполнять команды (командлеты, функции, команды CIM и рабочие процессы), но не могут использовать блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="8bae9-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="8bae9-129">По умолчанию в режиме Рестриктедлангуаже разрешены только следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="8bae9-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="8bae9-130">Манифесты модулей, использующие режим Рестриктедлангуаже, также допускают следующие дополнительные переменные:</span><span class="sxs-lookup"><span data-stu-id="8bae9-130">Module manifests, which use RestrictedLanguage mode, permit the following additional variables as well:</span></span>

- `$PSScriptRoot`
- <span data-ttu-id="8bae9-131">`$PSEdition` (в PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="8bae9-131">`$PSEdition` (in PowerShell Core)</span></span>
- <span data-ttu-id="8bae9-132">`$EnabledExperimentalFeatures` (в PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="8bae9-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span></span>

<span data-ttu-id="8bae9-133">Допустимы только следующие операторы сравнения:</span><span class="sxs-lookup"><span data-stu-id="8bae9-133">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="8bae9-134">`-eq` равномерно</span><span class="sxs-lookup"><span data-stu-id="8bae9-134">`-eq` (equal)</span></span>
- <span data-ttu-id="8bae9-135">`-gt` (больше)</span><span class="sxs-lookup"><span data-stu-id="8bae9-135">`-gt` (greater-than)</span></span>
- <span data-ttu-id="8bae9-136">`-lt` (меньше)</span><span class="sxs-lookup"><span data-stu-id="8bae9-136">`-lt` (less-than)</span></span>

<span data-ttu-id="8bae9-137">Операторы присваивания, ссылки на свойство и вызовы методов не разрешены.</span><span class="sxs-lookup"><span data-stu-id="8bae9-137">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="8bae9-138">НЕТ языка (язык)</span><span class="sxs-lookup"><span data-stu-id="8bae9-138">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="8bae9-139">Режим "неязыкового интерфейса" можно использовать только через API.</span><span class="sxs-lookup"><span data-stu-id="8bae9-139">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="8bae9-140">Режим без языка означает, что текст скрипта для любой формы не разрешен.</span><span class="sxs-lookup"><span data-stu-id="8bae9-140">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="8bae9-141">Это исключает использование метода **аддскрипт ()** , который отправляет фрагменты сценария PowerShell для синтаксического анализа и выполнения.</span><span class="sxs-lookup"><span data-stu-id="8bae9-141">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="8bae9-142">Можно использовать только **AddCommand ()** и **аддпараметер ()** , которые не проходят через средство синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="8bae9-142">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="8bae9-143">ОГРАНИЧЕНный язык (ограниченный язык)</span><span class="sxs-lookup"><span data-stu-id="8bae9-143">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="8bae9-144">Режим ConstrainedLanguage позволяет использовать все командлеты и все элементы языка PowerShell, но ограничивает разрешенные типы.</span><span class="sxs-lookup"><span data-stu-id="8bae9-144">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="8bae9-145">Режим ConstrainedLanguage предназначен для поддержки целостности кода пользовательского режима (УМЦИ) в Windows RT.</span><span class="sxs-lookup"><span data-stu-id="8bae9-145">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="8bae9-146">Это единственный поддерживаемый языковой режим в Windows RT, но он доступен во всех поддерживаемых системах.</span><span class="sxs-lookup"><span data-stu-id="8bae9-146">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="8bae9-147">УМЦИ защищает устройства ARM, разрешая установку на устройствах с Windows RT только приложений, подписанных корпорацией Майкрософт и сертифицированных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8bae9-147">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="8bae9-148">Режим ConstrainedLanguage запрещает пользователям использовать PowerShell для обхода или нарушения правил УМЦИ.</span><span class="sxs-lookup"><span data-stu-id="8bae9-148">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="8bae9-149">Ниже приведены функции режима ConstrainedLanguage.</span><span class="sxs-lookup"><span data-stu-id="8bae9-149">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="8bae9-150">Все командлеты в модулях Windows и другие командлеты, утвержденные УМЦИ, полностью работоспособны и имеют полный доступ к системным ресурсам, за исключением указанных.</span><span class="sxs-lookup"><span data-stu-id="8bae9-150">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="8bae9-151">Разрешены все элементы языка сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bae9-151">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="8bae9-152">Все модули, входящие в Windows, можно импортировать, а также все команды, выполняемые при экспорте модулей в сеансе.</span><span class="sxs-lookup"><span data-stu-id="8bae9-152">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="8bae9-153">В рабочем процессе PowerShell можно создавать и запускать рабочие процессы скриптов (рабочие процессы, написанные на языке PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8bae9-153">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="8bae9-154">Рабочие процессы на основе XAML не поддерживаются, и вы не можете запускать XAML в рабочем процессе скрипта, например с помощью `Invoke-Expression -Language XAML` .</span><span class="sxs-lookup"><span data-stu-id="8bae9-154">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="8bae9-155">Кроме того, рабочие процессы не могут вызывать другие рабочие процессы, хотя разрешены вложенные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="8bae9-155">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="8bae9-156">`Add-Type`Командлет может загружать подписанные сборки, но не может загрузить произвольный код C# или API-интерфейсы Win32.</span><span class="sxs-lookup"><span data-stu-id="8bae9-156">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="8bae9-157">`New-Object`Командлет можно использовать только для допустимых типов (перечисленных ниже).</span><span class="sxs-lookup"><span data-stu-id="8bae9-157">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="8bae9-158">В PowerShell можно использовать только допустимые типы (перечисленные ниже).</span><span class="sxs-lookup"><span data-stu-id="8bae9-158">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="8bae9-159">Другие типы не допускаются.</span><span class="sxs-lookup"><span data-stu-id="8bae9-159">Other types are not permitted.</span></span>

- <span data-ttu-id="8bae9-160">Преобразование типов разрешено, но только если результатом является допустимый тип.</span><span class="sxs-lookup"><span data-stu-id="8bae9-160">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="8bae9-161">Параметры командлета, которые преобразуют входные данные строки в типы, работают только в том случае, если результирующий тип является допустимым типом.</span><span class="sxs-lookup"><span data-stu-id="8bae9-161">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="8bae9-162">Можно вызвать метод **ToString ()** и методы .NET допустимых типов (перечисленных ниже).</span><span class="sxs-lookup"><span data-stu-id="8bae9-162">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="8bae9-163">Невозможно вызвать другие методы.</span><span class="sxs-lookup"><span data-stu-id="8bae9-163">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="8bae9-164">Пользователи могут получить все свойства разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="8bae9-164">Users can get all properties of allowed types.</span></span> <span data-ttu-id="8bae9-165">Пользователи могут устанавливать значения свойств только для основных типов.</span><span class="sxs-lookup"><span data-stu-id="8bae9-165">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="8bae9-166">Разрешены только следующие объекты COM:</span><span class="sxs-lookup"><span data-stu-id="8bae9-166">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="8bae9-167">**Скрипт. словарь**</span><span class="sxs-lookup"><span data-stu-id="8bae9-167">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="8bae9-168">**Scripting.FileSystemObject;**</span><span class="sxs-lookup"><span data-stu-id="8bae9-168">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="8bae9-169">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="8bae9-169">**VBScript.RegExp**</span></span>

<span data-ttu-id="8bae9-170">В режиме ConstrainedLanguage разрешены следующие типы.</span><span class="sxs-lookup"><span data-stu-id="8bae9-170">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="8bae9-171">Пользователи могут получать свойства, вызывать методы и преобразовывать объекты в эти типы.</span><span class="sxs-lookup"><span data-stu-id="8bae9-171">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="8bae9-172">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="8bae9-172">Allowed Types:</span></span>

- <span data-ttu-id="8bae9-173">алиасаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-173">AliasAttribute</span></span>
- <span data-ttu-id="8bae9-174">алловемптиколлектионаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-174">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="8bae9-175">алловемптистрингаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-175">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="8bae9-176">алловнуллаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-176">AllowNullAttribute</span></span>
- <span data-ttu-id="8bae9-177">Массив</span><span class="sxs-lookup"><span data-stu-id="8bae9-177">Array</span></span>
- <span data-ttu-id="8bae9-178">Bool</span><span class="sxs-lookup"><span data-stu-id="8bae9-178">Bool</span></span>
- <span data-ttu-id="8bae9-179">byte</span><span class="sxs-lookup"><span data-stu-id="8bae9-179">byte</span></span>
- <span data-ttu-id="8bae9-180">char</span><span class="sxs-lookup"><span data-stu-id="8bae9-180">char</span></span>
- <span data-ttu-id="8bae9-181">кмдлетбиндингаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-181">CmdletBindingAttribute</span></span>
- <span data-ttu-id="8bae9-182">Дата и время</span><span class="sxs-lookup"><span data-stu-id="8bae9-182">DateTime</span></span>
- <span data-ttu-id="8bae9-183">Decimal</span><span class="sxs-lookup"><span data-stu-id="8bae9-183">decimal</span></span>
- <span data-ttu-id="8bae9-184">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="8bae9-184">DirectoryEntry</span></span>
- <span data-ttu-id="8bae9-185">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="8bae9-185">DirectorySearcher</span></span>
- <span data-ttu-id="8bae9-186">double</span><span class="sxs-lookup"><span data-stu-id="8bae9-186">double</span></span>
- <span data-ttu-id="8bae9-187">FLOAT</span><span class="sxs-lookup"><span data-stu-id="8bae9-187">float</span></span>
- <span data-ttu-id="8bae9-188">Guid</span><span class="sxs-lookup"><span data-stu-id="8bae9-188">Guid</span></span>
- <span data-ttu-id="8bae9-189">Хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="8bae9-189">Hashtable</span></span>
- <span data-ttu-id="8bae9-190">INT</span><span class="sxs-lookup"><span data-stu-id="8bae9-190">int</span></span>
- <span data-ttu-id="8bae9-191">Int16</span><span class="sxs-lookup"><span data-stu-id="8bae9-191">Int16</span></span>
- <span data-ttu-id="8bae9-192">long</span><span class="sxs-lookup"><span data-stu-id="8bae9-192">long</span></span>
- <span data-ttu-id="8bae9-193">манажементкласс</span><span class="sxs-lookup"><span data-stu-id="8bae9-193">ManagementClass</span></span>
- <span data-ttu-id="8bae9-194">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="8bae9-194">ManagementObject</span></span>
- <span data-ttu-id="8bae9-195">манажементобжектсеарчер</span><span class="sxs-lookup"><span data-stu-id="8bae9-195">ManagementObjectSearcher</span></span>
- <span data-ttu-id="8bae9-196">нуллстринг</span><span class="sxs-lookup"><span data-stu-id="8bae9-196">NullString</span></span>
- <span data-ttu-id="8bae9-197">аутпуттипеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-197">OutputTypeAttribute</span></span>
- <span data-ttu-id="8bae9-198">параметераттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-198">ParameterAttribute</span></span>
- <span data-ttu-id="8bae9-199">PSCredential</span><span class="sxs-lookup"><span data-stu-id="8bae9-199">PSCredential</span></span>
- <span data-ttu-id="8bae9-200">псдефаултвалуеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-200">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="8bae9-201">пслистмодифиер</span><span class="sxs-lookup"><span data-stu-id="8bae9-201">PSListModifier</span></span>
- <span data-ttu-id="8bae9-202">PSObject</span><span class="sxs-lookup"><span data-stu-id="8bae9-202">PSObject</span></span>
- <span data-ttu-id="8bae9-203">пспримитиведиктионари</span><span class="sxs-lookup"><span data-stu-id="8bae9-203">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="8bae9-204">псреференце</span><span class="sxs-lookup"><span data-stu-id="8bae9-204">PSReference</span></span>
- <span data-ttu-id="8bae9-205">пстипенамеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-205">PSTypeNameAttribute</span></span>
- <span data-ttu-id="8bae9-206">Регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="8bae9-206">Regex</span></span>
- <span data-ttu-id="8bae9-207">SByte</span><span class="sxs-lookup"><span data-stu-id="8bae9-207">SByte</span></span>
- <span data-ttu-id="8bae9-208">строка</span><span class="sxs-lookup"><span data-stu-id="8bae9-208">string</span></span>
- <span data-ttu-id="8bae9-209">суппортсвилдкардсаттрибуте</span><span class="sxs-lookup"><span data-stu-id="8bae9-209">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="8bae9-210">Параметр-переключатель</span><span class="sxs-lookup"><span data-stu-id="8bae9-210">SwitchParameter</span></span>
- <span data-ttu-id="8bae9-211">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="8bae9-211">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="8bae9-212">System .NET. IPAddress</span><span class="sxs-lookup"><span data-stu-id="8bae9-212">System.Net.IPAddress</span></span>
- <span data-ttu-id="8bae9-213">System .NET. mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="8bae9-213">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="8bae9-214">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="8bae9-214">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="8bae9-215">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="8bae9-215">System.Security.SecureString</span></span>
- <span data-ttu-id="8bae9-216">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8bae9-216">TimeSpan</span></span>
- <span data-ttu-id="8bae9-217">UInt16</span><span class="sxs-lookup"><span data-stu-id="8bae9-217">UInt16</span></span>
- <span data-ttu-id="8bae9-218">UInt32</span><span class="sxs-lookup"><span data-stu-id="8bae9-218">UInt32</span></span>
- <span data-ttu-id="8bae9-219">UInt64</span><span class="sxs-lookup"><span data-stu-id="8bae9-219">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="8bae9-220">ПОИСК ЯЗЫКОВОГО РЕЖИМА КОНФИГУРАЦИИ СЕАНСА</span><span class="sxs-lookup"><span data-stu-id="8bae9-220">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="8bae9-221">Если конфигурация сеанса создается с помощью файла конфигурации сеанса, то конфигурация сеанса имеет свойство Лангуажемоде.</span><span class="sxs-lookup"><span data-stu-id="8bae9-221">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="8bae9-222">Чтобы найти языковой режим, можно получить значение свойства Лангуажемоде.</span><span class="sxs-lookup"><span data-stu-id="8bae9-222">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="8bae9-223">В других конфигурациях сеанса языковой режим можно найти косвенно, находя языковой режим сеанса, созданного с помощью конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="8bae9-223">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="8bae9-224">ПОИСК ЯЗЫКОВОГО РЕЖИМА СЕАНСА</span><span class="sxs-lookup"><span data-stu-id="8bae9-224">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="8bae9-225">Языковой режим сеанса Фулллангуаже или ConstrainedLanguage можно найти, получая значение свойства Лангуажемоде состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="8bae9-225">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="8bae9-226">Пример:</span><span class="sxs-lookup"><span data-stu-id="8bae9-226">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="8bae9-227">Однако в сеансах с Рестриктедлангуаже и неязыковыми режимами нельзя использовать метод Dot для получения значений свойств.</span><span class="sxs-lookup"><span data-stu-id="8bae9-227">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="8bae9-228">Вместо этого сообщение об ошибке отображает языковой режим.</span><span class="sxs-lookup"><span data-stu-id="8bae9-228">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="8bae9-229">При выполнении `$ExecutionContext.SessionState.LanguageMode` команды в сеансе Рестриктедлангуаже PowerShell возвращает сообщения об ошибках пропертиреференценотсуппортединдатасектион и вариаблереференценотсуппортединдатасектион.</span><span class="sxs-lookup"><span data-stu-id="8bae9-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="8bae9-230">Пропертиреференценотсуппортединдатасектион: ссылки на свойства не разрешены в ограниченном языковом режиме или в разделе данных.</span><span class="sxs-lookup"><span data-stu-id="8bae9-230">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="8bae9-231">Вариаблереференценотсуппортединдатасектион переменную, на которую нельзя ссылаться в ограниченном языковом режиме, или на раздел данных имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="8bae9-231">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="8bae9-232">При выполнении `$ExecutionContext.SessionState.LanguageMode` команды в сеансе на языке PowerShell возвращает сообщение об ошибке скриптсноталловед.</span><span class="sxs-lookup"><span data-stu-id="8bae9-232">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="8bae9-233">Скриптсноталловед: синтаксис не поддерживается этим пространством выполнения.</span><span class="sxs-lookup"><span data-stu-id="8bae9-233">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="8bae9-234">Это может быть вызвано тем, что он находится в неязыковом режиме.</span><span class="sxs-lookup"><span data-stu-id="8bae9-234">This might be because it is in no-language mode.</span></span>

## <a name="keywords"></a><span data-ttu-id="8bae9-235">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="8bae9-235">KEYWORDS</span></span>

- <span data-ttu-id="8bae9-236">about_ConstrainedLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-236">about_ConstrainedLanguage</span></span>
- <span data-ttu-id="8bae9-237">about_FullLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-237">about_FullLanguage</span></span>
- <span data-ttu-id="8bae9-238">about_NoLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-238">about_NoLanguage</span></span>
- <span data-ttu-id="8bae9-239">about_RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="8bae9-239">about_RestrictedLanguage</span></span>

## <a name="see-also"></a><span data-ttu-id="8bae9-240">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="8bae9-240">SEE ALSO</span></span>

- [<span data-ttu-id="8bae9-241">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="8bae9-241">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="8bae9-242">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8bae9-242">about_Session_Configurations</span></span>](about_Session_Configurations.md)

