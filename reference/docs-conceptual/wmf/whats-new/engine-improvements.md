---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,установка
title: Усовершенствования подсистемы PowerShell в WMF 5.1
ms.openlocfilehash: a0af702832c0a90c994650e25918ecacdc33fc4b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147654"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="21b84-103">Усовершенствования подсистемы PowerShell</span><span class="sxs-lookup"><span data-stu-id="21b84-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="21b84-104">В WMF 5.1 были реализованы перечисленные ниже улучшения основной подсистемы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21b84-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="21b84-105">Производительность</span><span class="sxs-lookup"><span data-stu-id="21b84-105">Performance</span></span>

<span data-ttu-id="21b84-106">Производительность улучшена в некоторых важных аспектах:</span><span class="sxs-lookup"><span data-stu-id="21b84-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="21b84-107">Запуск</span><span class="sxs-lookup"><span data-stu-id="21b84-107">Startup</span></span>
- <span data-ttu-id="21b84-108">Передача данных по конвейеру в такие командлеты, как `ForEach-Object` и `Where-Object`, выполняется примерно на 50 % быстрее.</span><span class="sxs-lookup"><span data-stu-id="21b84-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="21b84-109">Примеры некоторых улучшений (результаты могут различаться в зависимости от оборудования):</span><span class="sxs-lookup"><span data-stu-id="21b84-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="21b84-110">Сценарий</span><span class="sxs-lookup"><span data-stu-id="21b84-110">Scenario</span></span> | <span data-ttu-id="21b84-111">Время в версии 5.0 (мс)</span><span class="sxs-lookup"><span data-stu-id="21b84-111">5.0 Time (ms)</span></span> | <span data-ttu-id="21b84-112">Время в версии 5.1 (мс)</span><span class="sxs-lookup"><span data-stu-id="21b84-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="21b84-113">900</span><span class="sxs-lookup"><span data-stu-id="21b84-113">900</span></span> | <span data-ttu-id="21b84-114">250</span><span class="sxs-lookup"><span data-stu-id="21b84-114">250</span></span> |
| <span data-ttu-id="21b84-115">Самый первый запуск PowerShell: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="21b84-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="21b84-116">30 000</span><span class="sxs-lookup"><span data-stu-id="21b84-116">30000</span></span> | <span data-ttu-id="21b84-117">13 000</span><span class="sxs-lookup"><span data-stu-id="21b84-117">13000</span></span> |
| <span data-ttu-id="21b84-118">Построение кэша анализа команд: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="21b84-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="21b84-119">7000</span><span class="sxs-lookup"><span data-stu-id="21b84-119">7000</span></span> | <span data-ttu-id="21b84-120">520</span><span class="sxs-lookup"><span data-stu-id="21b84-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="21b84-121">1400</span><span class="sxs-lookup"><span data-stu-id="21b84-121">1400</span></span> | <span data-ttu-id="21b84-122">750</span><span class="sxs-lookup"><span data-stu-id="21b84-122">750</span></span> |

> [!NOTE]
> <span data-ttu-id="21b84-123">Одно из изменений, связанных с запуском, может повлиять на некоторые неподдерживаемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="21b84-123">One change related to startup might impact some unsupported scenarios.</span></span> <span data-ttu-id="21b84-124">PowerShell больше не считывает файлы `$pshome\*.ps1xml` — эти файлы были преобразованы в C# во избежание накладных расходов (файловых и ресурсов ЦП), связанных с обработкой XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="21b84-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> <span data-ttu-id="21b84-125">Эти файлы по-прежнему существуют для поддержки параллельно установленной версии 2, поэтому изменение их содержимого сказывается только на версии 2, но не на версии 5.</span><span class="sxs-lookup"><span data-stu-id="21b84-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> <span data-ttu-id="21b84-126">Обратите внимание на то, что изменение содержимого этих файлов никогда не поддерживалось.</span><span class="sxs-lookup"><span data-stu-id="21b84-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="21b84-127">Еще одним явным изменением является то, как PowerShell кэширует экспортируемые команды и другую информацию для модулей, установленных в системе.</span><span class="sxs-lookup"><span data-stu-id="21b84-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="21b84-128">Ранее этот кэш хранился в каталоге `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span><span class="sxs-lookup"><span data-stu-id="21b84-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="21b84-129">В WMF 5.1 этот кэш является отдельным файлом `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="21b84-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="21b84-130">Дополнительные сведения см. в статье [Кэш анализа модуля](release-notes.md#module-analysis-cache).</span><span class="sxs-lookup"><span data-stu-id="21b84-130">See [Module Analysis Cache](release-notes.md#module-analysis-cache) for more details.</span></span>