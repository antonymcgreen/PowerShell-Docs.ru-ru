---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Усовершенствования консоли в WMF 5.1
ms.openlocfilehash: ae3d08a34a09bc32d40a8a45788999ee9c54a562
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808990"
---
# <a name="console-improvements-in-wmf-51"></a><span data-ttu-id="01caa-103">Усовершенствования консоли в WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="01caa-103">Console Improvements in WMF 5.1</span></span>

## <a name="powershell-console-improvements"></a><span data-ttu-id="01caa-104">Усовершенствования консоли PowerShell</span><span class="sxs-lookup"><span data-stu-id="01caa-104">PowerShell console improvements</span></span>

<span data-ttu-id="01caa-105">Для улучшения работы с консолью в Powershell.exe в WMF 5.1 были внесены перечисленные ниже изменения.</span><span class="sxs-lookup"><span data-stu-id="01caa-105">The following changes have been made to powershell.exe in WMF 5.1 to improve the console experience:</span></span>

### <a name="vt100-support"></a><span data-ttu-id="01caa-106">Поддержка VT100</span><span class="sxs-lookup"><span data-stu-id="01caa-106">VT100 support</span></span>

<span data-ttu-id="01caa-107">В Windows 10 реализована поддержка [escape-последовательностей VT100](/windows/console/console-virtual-terminal-sequences).</span><span class="sxs-lookup"><span data-stu-id="01caa-107">Windows 10 added support for [VT100 escape sequences](/windows/console/console-virtual-terminal-sequences).</span></span>
<span data-ttu-id="01caa-108">При расчете ширины таблиц PowerShell игнорирует некоторые escape-последовательности форматирования VT100.</span><span class="sxs-lookup"><span data-stu-id="01caa-108">PowerShell will ignore certain VT100 formatting escape sequences when calculating table widths.</span></span>

<span data-ttu-id="01caa-109">В PowerShell также появился новый интерфейс API, который можно использовать при форматировании кода для определения наличия поддержки VT100.</span><span class="sxs-lookup"><span data-stu-id="01caa-109">PowerShell also added a new API that can be used in formatting code to determine if VT100 is supported.</span></span> <span data-ttu-id="01caa-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="01caa-110">For example:</span></span>

```powershell
if ($host.UI.SupportsVirtualTerminal)
{
    $esc = [char]0x1b
    "A yellow ${esc}[93mhello${esc}[0m"
}
else
{
    "A default hello"
}
```

<span data-ttu-id="01caa-111">Вот полный [пример](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7), который можно использовать для выделения совпадений в результатах выполнения командлета `Select-String`.</span><span class="sxs-lookup"><span data-stu-id="01caa-111">Here is a complete [example](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) that can be used to highlight matches from `Select-String`.</span></span> <span data-ttu-id="01caa-112">Сохраните пример в файле с именем `MatchInfo.format.ps1xml`. Чтобы использовать его, в своем профиле или другом месте выполните команду `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span><span class="sxs-lookup"><span data-stu-id="01caa-112">Save the example in a file named `MatchInfo.format.ps1xml`, then to use it, in your profile or elsewhere, run `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span></span>

<span data-ttu-id="01caa-113">Имейте в виду, что escape-последовательности VT100 поддерживаются только начиная с юбилейного обновления Windows 10.</span><span class="sxs-lookup"><span data-stu-id="01caa-113">Note that VT100 escape sequences are only supported starting with the Windows 10 Anniversary update.</span></span>
<span data-ttu-id="01caa-114">В более ранних системах они не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="01caa-114">They are not supported on earlier systems.</span></span>

### <a name="vi-mode-support-in-psreadline"></a><span data-ttu-id="01caa-115">Поддержка режима vi в PSReadline</span><span class="sxs-lookup"><span data-stu-id="01caa-115">Vi mode support in PSReadline</span></span>

<span data-ttu-id="01caa-116">В [PSReadline](https://github.com/PowerShell/PSReadLine) добавлена поддержка режима vi.</span><span class="sxs-lookup"><span data-stu-id="01caa-116">[PSReadline](https://github.com/PowerShell/PSReadLine) adds support for vi mode.</span></span> <span data-ttu-id="01caa-117">Чтобы включить режим vi, выполните команду `Set-PSReadlineOption -EditMode Vi`.</span><span class="sxs-lookup"><span data-stu-id="01caa-117">To use vi mode, run `Set-PSReadlineOption -EditMode Vi`.</span></span>

### <a name="redirected-stdin-with-interactive-input"></a><span data-ttu-id="01caa-118">Перенаправленный поток stdin с интерактивным вводом</span><span class="sxs-lookup"><span data-stu-id="01caa-118">Redirected stdin with interactive input</span></span>

<span data-ttu-id="01caa-119">В предыдущих версиях среду PowerShell требовалось запускать с помощью команды `powershell -File -`, если поток stdin перенаправлялся и необходимо было вводить команды в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="01caa-119">In earlier versions, starting PowerShell with `powershell -File -` was required when stdin was redirected and you wanted to enter commands interactively.</span></span>

<span data-ttu-id="01caa-120">В WMF 5.1 этот сложный для обнаружения вариант больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="01caa-120">With WMF 5.1, this hard to discover option is no longer necessary.</span></span> <span data-ttu-id="01caa-121">PowerShell можно запустить без параметров.</span><span class="sxs-lookup"><span data-stu-id="01caa-121">You can start PowerShell without any options.</span></span>

<span data-ttu-id="01caa-122">Обратите внимание на то, что PSReadline не поддерживает перенаправленный поток stdin, а встроенные возможности редактирования в командной строке с перенаправленным потоком stdin крайне ограничены (например, не работают клавиши со стрелками).</span><span class="sxs-lookup"><span data-stu-id="01caa-122">Note that PSReadline does not support redirected stdin, and the built-in command-line editing experience with redirected stdin is extremely limited, for example, arrow keys don't work.</span></span> <span data-ttu-id="01caa-123">В будущих версиях PSReadline эта проблема должна быть решена.</span><span class="sxs-lookup"><span data-stu-id="01caa-123">A future release of PSReadline should address this issue.</span></span>