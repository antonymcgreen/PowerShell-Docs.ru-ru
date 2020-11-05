---
ms.date: 06/12/2017
title: Исправления ошибок в WMF 5.1
description: В этой статье приведены ошибки, которые были исправлены в выпуске WMF 5.1.
ms.openlocfilehash: 2673860852ecd6e0b6582f6f69076f8c463eeccc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660772"
---
# <a name="bug-fixes-in-wmf-51"></a><span data-ttu-id="fe128-103">Исправления ошибок в WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="fe128-103">Bug Fixes in WMF 5.1</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="fe128-104">Исправления ошибок</span><span class="sxs-lookup"><span data-stu-id="fe128-104">Bug fixes</span></span>

<span data-ttu-id="fe128-105">В WMF 5.1 исправлены следующие важные ошибки.</span><span class="sxs-lookup"><span data-stu-id="fe128-105">The following notable bugs are fixed in WMF 5.1:</span></span>

### <a name="module-auto-discovery-fully-honors-psmodulepath"></a><span data-ttu-id="fe128-106">При автоматическом обнаружении модулей полностью учитывается PSModulePath</span><span class="sxs-lookup"><span data-stu-id="fe128-106">Module auto-discovery fully honors PSModulePath</span></span>

<span data-ttu-id="fe128-107">Автоматическое обнаружение модулей (их автоматическая загрузка без явного вызова Import-Module при вызове команды) появилось в WMF 3.</span><span class="sxs-lookup"><span data-stu-id="fe128-107">Module auto-discovery (loading modules automatically without an explicit Import-Module when calling a command) was introduced in WMF 3.</span></span> <span data-ttu-id="fe128-108">В этой версии среда PowerShell проверяла команды в `$PSHome\Modules` перед использованием `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="fe128-108">When introduced, PowerShell checked for commands in `$PSHome\Modules` before using `$env:PSModulePath`.</span></span>

<span data-ttu-id="fe128-109">В WMF 5.1 это поведение изменилось: `$env:PSModulePath` учитывается полностью.</span><span class="sxs-lookup"><span data-stu-id="fe128-109">WMF 5.1 changes this behavior to honor `$env:PSModulePath` completely.</span></span> <span data-ttu-id="fe128-110">Это позволяет автоматически загружать созданные пользователями модули, в которых определяются предоставляемые PowerShell команды (например, `Get-ChildItem`), и правильно переопределять встроенные команды.</span><span class="sxs-lookup"><span data-stu-id="fe128-110">This allows for a user-authored module that defines commands provided by PowerShell (e.g. `Get-ChildItem`) to be auto-loaded and correctly overriding the built-in command.</span></span>

### <a name="file-redirection-no-longer-hard-codes--encoding-unicode"></a><span data-ttu-id="fe128-111">При перенаправлении файлов Encoding Unicode больше не задается жестко</span><span class="sxs-lookup"><span data-stu-id="fe128-111">File redirection no longer hard-codes -Encoding Unicode</span></span>

<span data-ttu-id="fe128-112">Во всех предыдущих версиях PowerShell было невозможно контролировать кодировку файлов, используемую оператором перенаправления файлов.</span><span class="sxs-lookup"><span data-stu-id="fe128-112">In all previous versions of PowerShell, it was impossible to control the file encoding used by the file redirection operator.</span></span>

<span data-ttu-id="fe128-113">Начиная с версии WMF 5.1 можно изменять кодировку файлов при перенаправлении, задавая `$PSDefaultParameterValues`:</span><span class="sxs-lookup"><span data-stu-id="fe128-113">Starting with WMF 5.1, you can now change the file encoding of redirection by setting `$PSDefaultParameterValues`:</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### <a name="fixed-a-regression-in-accessing-members-of-systemreflectiontypeinfo"></a><span data-ttu-id="fe128-114">Исправлена регрессия при доступе к членам System.Reflection.TypeInfo</span><span class="sxs-lookup"><span data-stu-id="fe128-114">Fixed a regression in accessing members of System.Reflection.TypeInfo</span></span>

<span data-ttu-id="fe128-115">Появившаяся в WMF 5.0 регрессия нарушала доступ к членам `System.Reflection.RuntimeType`, например `[int].ImplementedInterfaces`.</span><span class="sxs-lookup"><span data-stu-id="fe128-115">A regression introduced in WMF 5.0 broke accessing members of `System.Reflection.RuntimeType`, for example, `[int].ImplementedInterfaces`.</span></span> <span data-ttu-id="fe128-116">Эта ошибка исправлена в WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="fe128-116">This bug has been fixed in WMF 5.1.</span></span>

### <a name="fixed-some-issues-with-com-objects"></a><span data-ttu-id="fe128-117">Исправлены некоторые проблемы с объектами COM</span><span class="sxs-lookup"><span data-stu-id="fe128-117">Fixed some issues with COM objects</span></span>

<span data-ttu-id="fe128-118">В WMF 5.0 появился новый модуль привязки COM для вызова методов применительно к COM-объектам и доступа к свойствам COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="fe128-118">WMF 5.0 introduced a new COM binder for invoking methods on COM objects and accessing properties of COM objects.</span></span> <span data-ttu-id="fe128-119">Этот новый модуль значительно повысил производительность, но в нем был ряд ошибок, которые исправлены в WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="fe128-119">This new binder improved performance significantly but also introduced some bugs which have been fixed in WMF 5.1.</span></span>

#### <a name="argument-conversions-were-not-always-performed-correctly"></a><span data-ttu-id="fe128-120">Преобразование аргументов не всегда выполнялось правильно</span><span class="sxs-lookup"><span data-stu-id="fe128-120">Argument conversions were not always performed correctly</span></span>

<span data-ttu-id="fe128-121">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="fe128-121">In the following example:</span></span>

```powershell
$obj = New-Object -ComObject WScript.Shell
$obj.SendKeys([char]173)
```

<span data-ttu-id="fe128-122">Метод **SendKeys** требует строку, но среда PowerShell не преобразовала char в string, отложив преобразование до вызова метода **IDispatch::Invoke** , который использует **VariantChangeType** для выполнения преобразования.</span><span class="sxs-lookup"><span data-stu-id="fe128-122">The **SendKeys** method expects a string, but PowerShell did not convert the char to a string, deferring the conversion to **IDispatch::Invoke** , which uses **VariantChangeType** to do the conversion.</span></span> <span data-ttu-id="fe128-123">В этом примере это приводит к отправке ключей "1", "7" и "3" вместо требуемого ключа **Volume.Mute**.</span><span class="sxs-lookup"><span data-stu-id="fe128-123">In this example, this resulted in sending the keys '1', '7', and '3' instead of the expected **Volume.Mute** key.</span></span>

#### <a name="enumerable-com-objects-not-always-handled-correctly"></a><span data-ttu-id="fe128-124">Перечисляемые COM-объекты не всегда обрабатывались правильно</span><span class="sxs-lookup"><span data-stu-id="fe128-124">Enumerable COM objects not always handled correctly</span></span>

<span data-ttu-id="fe128-125">Среда PowerShell, как правило, перечисляет большинство перечисляемых объектов, но регрессия, появившаяся в WMF 5.0, препятствовала перечислению COM-объектов, реализующих интерфейс IEnumerable.</span><span class="sxs-lookup"><span data-stu-id="fe128-125">PowerShell normally enumerates most enumerable objects, but a regression introduced in WMF 5.0 prevented the enumeration of COM objects that implement IEnumerable.</span></span> <span data-ttu-id="fe128-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="fe128-126">For example:</span></span>

```powershell
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

<span data-ttu-id="fe128-127">В приведенном выше примере WMF 5.0 записывает **Scripting.Dictionary** в конвейер (что неправильно) вместо перечисления пар "ключ — значение".</span><span class="sxs-lookup"><span data-stu-id="fe128-127">In the above example, WMF 5.0 incorrectly wrote the **Scripting.Dictionary** to the pipeline instead of enumerating the key/value pairs.</span></span>

### <a name="ordered-was-not-allowed-inside-classes"></a><span data-ttu-id="fe128-128">[ordered] не разрешалось использовать в классах</span><span class="sxs-lookup"><span data-stu-id="fe128-128">[ordered] was not allowed inside classes</span></span>

<span data-ttu-id="fe128-129">В WMF 5.0 появились классы, в которых проверялось использование литералов типов.</span><span class="sxs-lookup"><span data-stu-id="fe128-129">WMF 5.0 introduced classes with validation of type literals used in classes.</span></span> <span data-ttu-id="fe128-130">`[ordered]` выглядит как литерал типа, но в действительности не является типом .NET.</span><span class="sxs-lookup"><span data-stu-id="fe128-130">`[ordered]` looks like a type literal but is not a true .NET type.</span></span> <span data-ttu-id="fe128-131">В WMF 5.0 ошибочно выдавалась ошибка для `[ordered]` внутри класса:</span><span class="sxs-lookup"><span data-stu-id="fe128-131">WMF 5.0 incorrectly reported an error on `[ordered]` inside a class:</span></span>

```powershell
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```

### <a name="help-on-about-topics-with-multiple-versions-does-not-work"></a><span data-ttu-id="fe128-132">Вызов разделов справки при наличии нескольких версий не работал</span><span class="sxs-lookup"><span data-stu-id="fe128-132">Help on About topics with multiple versions does not work</span></span>

<span data-ttu-id="fe128-133">До версии WMF 5.1 при наличии нескольких установленных версий модуля с общим разделом справки, например "about_PSReadline", команда `help about_PSReadline` возвращала несколько разделов без возможности просмотреть саму справку.</span><span class="sxs-lookup"><span data-stu-id="fe128-133">Before WMF 5.1, if you had multiple versions of a module installed and they all shared a help topic, for example, about_PSReadline, `help about_PSReadline` would return multiple topics with no obvious way to view the real help.</span></span>

<span data-ttu-id="fe128-134">В WMF 5.1 эта проблема устранена: теперь возвращается последняя версия раздела.</span><span class="sxs-lookup"><span data-stu-id="fe128-134">WMF 5.1 fixes this by returning the help for the latest version of the topic.</span></span>

<span data-ttu-id="fe128-135">`Get-Help` не позволяет указать версию, по которой требуется справка.</span><span class="sxs-lookup"><span data-stu-id="fe128-135">`Get-Help` does not provide a way to specify which version you want help for.</span></span> <span data-ttu-id="fe128-136">В качестве обходного решения можно перейти к каталогу модулей и открыть справку напрямую, например с помощью любимого редактора.</span><span class="sxs-lookup"><span data-stu-id="fe128-136">To work around this, navigate to the modules directory and view the help directly with a tool like your favorite editor.</span></span>

### <a name="powershellexe-reading-from-stdin-stopped-working"></a><span data-ttu-id="fe128-137">Программа powershell.exe, считывающая данные из STDIN, прекратила работу.</span><span class="sxs-lookup"><span data-stu-id="fe128-137">powershell.exe reading from STDIN stopped working</span></span>

<span data-ttu-id="fe128-138">Клиенты используют `powershell -command -` в приложениях в машинном коде для передачи скрипта PowerShell с помощью STDIN. Теперь это невозможно из-за других изменений в узле консоли.</span><span class="sxs-lookup"><span data-stu-id="fe128-138">Customers use `powershell -command -` from native apps to execute PowerShell passing in the script via STDIN unfortunately this was broken by other changes in the console host.</span></span>

<span data-ttu-id="fe128-139">Эта проблема устранена в версии 5.1 в юбилейном обновлении Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fe128-139">This is fixed for version 5.1 in the Windows 10 Anniversary Update.</span></span>

### <a name="powershellexe-creates-spike-in-cpu-usage-on-startup"></a><span data-ttu-id="fe128-140">Программа powershell.exe создает пик загрузки ЦП при запуске.</span><span class="sxs-lookup"><span data-stu-id="fe128-140">powershell.exe creates spike in CPU usage on startup</span></span>

<span data-ttu-id="fe128-141">PowerShell использует запрос WMI, чтобы проверить, запущен ли он с помощью групповой политики, чтобы избежать задержки входа.</span><span class="sxs-lookup"><span data-stu-id="fe128-141">PowerShell uses a WMI query to check if it was started via Group Policy to avoid causing delay in login.</span></span> <span data-ttu-id="fe128-142">Запрос WMI завершается вставкой tzres.mui.dll в каждый процесс в системе, так как класс WMI **Win 32_Process** пытается извлечь сведения о локальном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="fe128-142">The WMI query ends up injecting tzres.mui.dll into every process on the system since the WMI **Win32_Process** class attempts to retrieve local timezone information.</span></span> <span data-ttu-id="fe128-143">Это приводит к пику загрузки ЦП в **wmiprvse** (узел поставщика WMI).</span><span class="sxs-lookup"><span data-stu-id="fe128-143">This results in a large CPU spike in **wmiprvse** (the WMI provider host).</span></span> <span data-ttu-id="fe128-144">Чтобы исправить это, используйте вызовы API Win32 вместо WMI, чтобы получить те же сведения.</span><span class="sxs-lookup"><span data-stu-id="fe128-144">Fix is to use Win32 API calls to get the same information instead of using WMI.</span></span>
