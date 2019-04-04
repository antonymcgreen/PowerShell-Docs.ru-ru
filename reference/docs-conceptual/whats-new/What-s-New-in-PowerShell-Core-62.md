---
title: Новые возможности в PowerShell Core 6.2
description: Новые возможности и изменения в PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 2224d23a244175059a705c07001e8ad8d6ab3aa0
ms.sourcegitcommit: 8dd4394cf867005a8b9ef0bb74b744c964fbc332
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "58750059"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="b8cca-103">Новые возможности в PowerShell Core 6.2</span><span class="sxs-lookup"><span data-stu-id="b8cca-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="b8cca-104">Ниже указаны некоторые основные новые функции и изменения, которые были внесены в PowerShell Core 6.2.</span><span class="sxs-lookup"><span data-stu-id="b8cca-104">Below is a selection of some of the major new features and changes that have been introduced in PowerShell Core 6.2.</span></span>

<span data-ttu-id="b8cca-105">Кроме того, доступно **множество** добавлений, позволяющих повысить быстродействие и стабильность PowerShell (а также целый ряд исправлений ошибок).</span><span class="sxs-lookup"><span data-stu-id="b8cca-105">There's also **tons** of "boring stuff" that make PowerShell faster and more stable (plus lots and lots of bug fixes)!</span></span>
<span data-ttu-id="b8cca-106">Полный список изменений см. в нашем [журнале изменений на сайте GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span><span class="sxs-lookup"><span data-stu-id="b8cca-106">For a full list of changes, check out our [changelog on GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span></span>

<span data-ttu-id="b8cca-107">Несмотря на то что далее мы называем лишь часть имен, мы выражаем благодарность [всем участникам сообщества](https://github.com/PowerShell/PowerShell/graphs/contributors), которые внесли свой вклад в этот выпуск.</span><span class="sxs-lookup"><span data-stu-id="b8cca-107">And while we call out some names below, thank you to [all of the community contributors](https://github.com/PowerShell/PowerShell/graphs/contributors) that made this release possible.</span></span>

## <a name="engine-updates-and-fixes"></a><span data-ttu-id="b8cca-108">Обновления и исправления модулей</span><span class="sxs-lookup"><span data-stu-id="b8cca-108">Engine Updates and Fixes</span></span>

- <span data-ttu-id="b8cca-109">Добавлен командлет удаленного включения или отключения предупреждающих сообщений PowerShell ([#9203][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-109">Add PowerShell remoting enable/disable cmdlet warning messages ([#9203][])</span></span>
- <span data-ttu-id="b8cca-110">Исправлена ошибка с регрессией удаленной десериализации `FormatTable` ([#9116][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-110">Fix for `FormatTable` remote deserialization regression ([#9116][])</span></span>
- <span data-ttu-id="b8cca-111">Обновлены API `async` на основе задач, добавленные в PowerShell для получения объекта задачи напрямую ([#9079][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-111">Update the task-based `async` APIs added to PowerShell to return a Task object directly ([#9079][])</span></span>
- <span data-ttu-id="b8cca-112">Добавлено 5 перегрузок `InvokeAsync` и `StopAsync` для типа `PowerShell` ([#8056][]) (спасибо @KirkMunro!).</span><span class="sxs-lookup"><span data-stu-id="b8cca-112">Add 5 `InvokeAsync` overloads and `StopAsync` to the `PowerShell` type ([#8056][]) (Thanks @KirkMunro!)</span></span>

## <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="b8cca-113">Общие обновления и исправления командлетов</span><span class="sxs-lookup"><span data-stu-id="b8cca-113">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="b8cca-114">Включены командлеты `SecureString` для отличающихся от Windows продуктов с сохранением обычного текста ([#9199][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-114">Enable `SecureString` cmdlets for non-Windows by storing the plain text ([#9199][])</span></span>
- <span data-ttu-id="b8cca-115">Добавлено устаревшее сообщения для `Send-MailMessage` ([#9178][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-115">Add Obsolete message to `Send-MailMessage` ([#9178][])</span></span>
- <span data-ttu-id="b8cca-116">Исправлена ошибка с `Restart-Computer` при работе с `localhost` и отсутствием WinRM ([#9160][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-116">Fix `Restart-Computer` to work on `localhost` when WinRM is not present ([#9160][])</span></span>
- <span data-ttu-id="b8cca-117">В `Start-Job` включено получение неустранимой ошибки при размещении PowerShell ([#9128][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-117">Make `Start-Job` throw terminating error when PowerShell is being hosted ([#9128][])</span></span>
- <span data-ttu-id="b8cca-118">Обновлена версия для `PowerShell.Native` для размещения тестов ([#8983][]).</span><span class="sxs-lookup"><span data-stu-id="b8cca-118">Update version for `PowerShell.Native` and hosting tests ([#8983][])</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="b8cca-119">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="b8cca-119">Breaking Changes</span></span>

<span data-ttu-id="b8cca-120">Исправлено поведение NoEnumerate в сценариях Write-Output для согласования с Windows PowerShell ([#9069][]) (спасибо @vexx32!).</span><span class="sxs-lookup"><span data-stu-id="b8cca-120">Fix -NoEnumerate behavior in Write-Output to be consistent with Windows PowerShell ([#9069][]) (Thanks @vexx32!)</span></span>

<!-- Link references -->
[#8056]: https://github.com/PowerShell/PowerShell/pull/8056
[#8983]: https://github.com/PowerShell/PowerShell/pull/8983
[#9069]: https://github.com/PowerShell/PowerShell/pull/9069
[#9079]: https://github.com/PowerShell/PowerShell/pull/9079
[#9116]: https://github.com/PowerShell/PowerShell/pull/9116
[#9128]: https://github.com/PowerShell/PowerShell/pull/9128
[#9160]: https://github.com/PowerShell/PowerShell/pull/9160
[#9178]: https://github.com/PowerShell/PowerShell/pull/9178
[#9199]: https://github.com/PowerShell/PowerShell/pull/9199
[#9203]: https://github.com/PowerShell/PowerShell/pull/9203
