---
title: Жизненный цикл поддержки PowerShell Core
description: Политики, распространяемые на поддержку PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: 178e5c43520f9a392ca219b9f785eb18b1ec5436
ms.sourcegitcommit: f268dce5b5e72be669be0c6634b8db11369bbae2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623864"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="b59d9-103">Жизненный цикл поддержки PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="b59d9-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="b59d9-104">PowerShell Core — это отдельный набор средств и компонентов, поставляемых, устанавливаемых и настраиваемых отдельно от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b59d9-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="b59d9-105">Поэтому на PowerShell Core не распространяются лицензионные соглашения Windows 7, 8.1, 10 или Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b59d9-105">So, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="b59d9-106">Однако PowerShell Core поддерживается в рамках традиционных соглашений о поддержке корпорации Майкрософт, включая [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement] и [Microsoft Software Assurance][assurance].</span><span class="sxs-lookup"><span data-stu-id="b59d9-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="b59d9-107">Вы также можете оплатить [техническую поддержку][] по PowerShell Core, направив в службу поддержки запрос о своей проблеме.</span><span class="sxs-lookup"><span data-stu-id="b59d9-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="b59d9-108">Поддержка сообщества</span><span class="sxs-lookup"><span data-stu-id="b59d9-108">Community Support</span></span>

<span data-ttu-id="b59d9-109">Мы также предлагаем [поддержку сообщества][] на GitHub, где вы можете зарегистрировать вопрос, ошибку или запрос функции.</span><span class="sxs-lookup"><span data-stu-id="b59d9-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="b59d9-110">Кроме того, вы можете обратиться за помощью к другим членам сообщества на сайтах [Microsoft Community][] или Microsoft [PowerShell Tech Community][].</span><span class="sxs-lookup"><span data-stu-id="b59d9-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="b59d9-111">Но мы не можем гарантировать, что там вам оперативно помогут решить вашу проблему.</span><span class="sxs-lookup"><span data-stu-id="b59d9-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span>
<span data-ttu-id="b59d9-112">Если ваша проблема требует немедленного вмешательства, следует использовать традиционные платные варианты поддержки.</span><span class="sxs-lookup"><span data-stu-id="b59d9-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="b59d9-113">Жизненный цикл PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="b59d9-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="b59d9-114">В PowerShell Core внедряется [политика современного жизненного цикла Майкрософт][modern].</span><span class="sxs-lookup"><span data-stu-id="b59d9-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="b59d9-115">Этот жизненный цикл поддержки предназначен для предоставления клиентам актуальных версий.</span><span class="sxs-lookup"><span data-stu-id="b59d9-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="b59d9-116">Ветвь PowerShell Core версии 6.x будет обновляться примерно каждые шесть месяцев: 6.0, 6.1, 6.2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="b59d9-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b59d9-117">Чтобы продолжить получать поддержку, вам нужно обновить продукт в течение шести месяцев после выпуска версии с новым дополнительным номером.</span><span class="sxs-lookup"><span data-stu-id="b59d9-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="b59d9-118">Например, если версия PowerShell Core 6.1 выпущена 1 июля 2018 г., чтобы продолжать получать поддержку, вам нужно выполнить обновление до версии PowerShell Core 6.1 к 1 января 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b59d9-119">Кроме того, вам нужно обновлять продукт в течение 30 дней после выпуска версии с новым исправлением.</span><span class="sxs-lookup"><span data-stu-id="b59d9-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="b59d9-120">Например, если вы используете PowerShell Core 6.1, а версия 6.1.3 выпущена 19 февраля 2019 г., вам нужно выполнить обновление до версии PowerShell Core 6.1.3 в течение 30 дней, т. е. до 21 марта 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-120">For example, If you are running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span>
<span data-ttu-id="b59d9-121">Если требуется какие-либо исправления, они будут включены в наше следующе накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="b59d9-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

![Жизненный цикл ветви PowerShell Core][lifecycle-chart]

<span data-ttu-id="b59d9-123">Согласно политике современного жизненного цикла также требуется, чтобы корпорация Майкрософт предоставляла клиентам уведомление за 12 месяцев до прекращения поддержки продукта (например, PowerShell Core).</span><span class="sxs-lookup"><span data-stu-id="b59d9-123">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="b59d9-124">Со временем мы планируем реализовать для PowerShell Core возможность долгосрочного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="b59d9-124">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach.</span></span>
<span data-ttu-id="b59d9-125">Это позволит нам осуществлять обслуживание и выпускать обновления для системы безопасности, чтобы обеспечить поддержку определенной ветви или версии 6.x.</span><span class="sxs-lookup"><span data-stu-id="b59d9-125">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="b59d9-126">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="b59d9-126">Supported platforms</span></span>

<span data-ttu-id="b59d9-127">В таблице ниже указано, какая платформа используемой версии PowerShell Core официально поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b59d9-127">The following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="b59d9-128">Наше сообщество также предоставило пакеты для некоторых платформ, но они не поддерживаются официально.</span><span class="sxs-lookup"><span data-stu-id="b59d9-128">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="b59d9-129">Эти пакеты, отмечены как `Community` в таблице.</span><span class="sxs-lookup"><span data-stu-id="b59d9-129">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="b59d9-130">Отмеченные как `Experimental` платформы официально не поддерживаются, но доступны для экспериментов с возможностью обратной связи.</span><span class="sxs-lookup"><span data-stu-id="b59d9-130">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="b59d9-131">6.1</span><span class="sxs-lookup"><span data-stu-id="b59d9-131">6.1</span></span>         | <span data-ttu-id="b59d9-132">6.2</span><span class="sxs-lookup"><span data-stu-id="b59d9-132">6.2</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="b59d9-133">Windows 7, 8.1 и 10</span><span class="sxs-lookup"><span data-stu-id="b59d9-133">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="b59d9-134">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-134">Supported</span></span>   | <span data-ttu-id="b59d9-135">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-135">Supported</span></span>   |
| <span data-ttu-id="b59d9-136">Windows Server 2008 R2, 2012 R2, 2016</span><span class="sxs-lookup"><span data-stu-id="b59d9-136">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="b59d9-137">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-137">Supported</span></span>   | <span data-ttu-id="b59d9-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-138">Supported</span></span>   |
| <span data-ttu-id="b59d9-139">[Windows Server Semi-Annual Channel][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="b59d9-139">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="b59d9-140">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-140">Supported</span></span>   | <span data-ttu-id="b59d9-141">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-141">Supported</span></span>   |
| <span data-ttu-id="b59d9-142">Ubuntu 16.04 и 18.04</span><span class="sxs-lookup"><span data-stu-id="b59d9-142">Ubuntu 16.04 and 18.04</span></span>                            | <span data-ttu-id="b59d9-143">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-143">Supported</span></span>   | <span data-ttu-id="b59d9-144">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-144">Supported</span></span>   |
| <span data-ttu-id="b59d9-145">Ubuntu 18.10 (с помощью snap-пакета)</span><span class="sxs-lookup"><span data-stu-id="b59d9-145">Ubuntu 18.10 (via Snap Package)</span></span>                   | <span data-ttu-id="b59d9-146">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-146">Community</span></span>   | <span data-ttu-id="b59d9-147">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-147">Community</span></span>   |
| <span data-ttu-id="b59d9-148">Debian 9</span><span class="sxs-lookup"><span data-stu-id="b59d9-148">Debian 9</span></span>                                          | <span data-ttu-id="b59d9-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-149">Supported</span></span>   | <span data-ttu-id="b59d9-150">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-150">Supported</span></span>   |
| <span data-ttu-id="b59d9-151">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="b59d9-151">CentOS 7</span></span>                                          | <span data-ttu-id="b59d9-152">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-152">Supported</span></span>   | <span data-ttu-id="b59d9-153">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-153">Supported</span></span>   |
| <span data-ttu-id="b59d9-154">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="b59d9-154">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="b59d9-155">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-155">Supported</span></span>   | <span data-ttu-id="b59d9-156">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-156">Supported</span></span>   |
| <span data-ttu-id="b59d9-157">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="b59d9-157">openSUSE 42.3</span></span>                                     | <span data-ttu-id="b59d9-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-158">Supported</span></span>   | <span data-ttu-id="b59d9-159">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-159">Supported</span></span>   |
| <span data-ttu-id="b59d9-160">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="b59d9-160">Fedora 28</span></span>                                         | <span data-ttu-id="b59d9-161">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-161">Supported</span></span>   | <span data-ttu-id="b59d9-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-162">Supported</span></span>   |
| <span data-ttu-id="b59d9-163">macOS 10.12+</span><span class="sxs-lookup"><span data-stu-id="b59d9-163">macOS 10.12+</span></span>                                      | <span data-ttu-id="b59d9-164">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-164">Supported</span></span>   | <span data-ttu-id="b59d9-165">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="b59d9-165">Supported</span></span>   |
| <span data-ttu-id="b59d9-166">Arch</span><span class="sxs-lookup"><span data-stu-id="b59d9-166">Arch</span></span>                                              | <span data-ttu-id="b59d9-167">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-167">Community</span></span>   | <span data-ttu-id="b59d9-168">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-168">Community</span></span>   |
| <span data-ttu-id="b59d9-169">Raspbian</span><span class="sxs-lookup"><span data-stu-id="b59d9-169">Raspbian</span></span>                                          | <span data-ttu-id="b59d9-170">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-170">Community</span></span>   | <span data-ttu-id="b59d9-171">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-171">Community</span></span>   |
| <span data-ttu-id="b59d9-172">Kali</span><span class="sxs-lookup"><span data-stu-id="b59d9-172">Kali</span></span>                                              | <span data-ttu-id="b59d9-173">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-173">Community</span></span>   | <span data-ttu-id="b59d9-174">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-174">Community</span></span>   |
| <span data-ttu-id="b59d9-175">AppImage (работает на нескольких платформах Linux)</span><span class="sxs-lookup"><span data-stu-id="b59d9-175">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="b59d9-176">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-176">Community</span></span>   | <span data-ttu-id="b59d9-177">Сообщество</span><span class="sxs-lookup"><span data-stu-id="b59d9-177">Community</span></span>   |
| [<span data-ttu-id="b59d9-178">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="b59d9-178">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="b59d9-179">См. примечание</span><span class="sxs-lookup"><span data-stu-id="b59d9-179">See note</span></span>    | <span data-ttu-id="b59d9-180">См. примечание</span><span class="sxs-lookup"><span data-stu-id="b59d9-180">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="b59d9-181">Прикрепленные пакеты поддерживаются так же, как и соответствующий дистрибутив.</span><span class="sxs-lookup"><span data-stu-id="b59d9-181">Snap packages are supported the same as the distribution you are running the package on.</span></span>

## <a name="powershell-release-end-of-life"></a><span data-ttu-id="b59d9-182">Завершение жизненного цикла PowerShell</span><span class="sxs-lookup"><span data-stu-id="b59d9-182">PowerShell release end of life</span></span>

<span data-ttu-id="b59d9-183">В следующей таблице перечислены даты прекращения поддержки разных выпусков PowerShell Core с учетом [жизненного цикла этого продукта](#lifecycle-of-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="b59d9-183">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various release will no longer be supported.</span></span>

| <span data-ttu-id="b59d9-184">Версия</span><span class="sxs-lookup"><span data-stu-id="b59d9-184">Version</span></span> | <span data-ttu-id="b59d9-185">Завершение срока службы</span><span class="sxs-lookup"><span data-stu-id="b59d9-185">End Of Life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="b59d9-186">6.0</span><span class="sxs-lookup"><span data-stu-id="b59d9-186">6.0</span></span>     | <span data-ttu-id="b59d9-187">13 февраля 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-187">February 13, 2019</span></span>             |
| <span data-ttu-id="b59d9-188">6.1</span><span class="sxs-lookup"><span data-stu-id="b59d9-188">6.1</span></span>     | <span data-ttu-id="b59d9-189">28 сентября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-189">September 28, 2019</span></span>            |
| <span data-ttu-id="b59d9-190">6.2</span><span class="sxs-lookup"><span data-stu-id="b59d9-190">6.2</span></span>     | <span data-ttu-id="b59d9-191">6 месяцев после выпуска версии 6.3</span><span class="sxs-lookup"><span data-stu-id="b59d9-191">6 months after 6.3 releases</span></span>   |

## <a name="platforms-which-are-out-of-support"></a><span data-ttu-id="b59d9-192">Неподдерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="b59d9-192">Platforms, which are out of support</span></span>

<span data-ttu-id="b59d9-193">По завершении жизненного цикла определенной версии платформы (определяется ее владельцем), прекращается ее поддержка в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="b59d9-193">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span>
<span data-ttu-id="b59d9-194">Предыдущие выпуски пакетов останутся доступными для клиентов, которым требуется доступ, но официальная поддержка и обновления больше не будет предоставляться.</span><span class="sxs-lookup"><span data-stu-id="b59d9-194">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="b59d9-195">Таким образом, поддержка следующих версий прекращается владельцами дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="b59d9-195">So, the distribution owners ended support for the following versions and are not supported.</span></span>

| <span data-ttu-id="b59d9-196">ОС</span><span class="sxs-lookup"><span data-stu-id="b59d9-196">OS</span></span>       | <span data-ttu-id="b59d9-197">Версия</span><span class="sxs-lookup"><span data-stu-id="b59d9-197">Version</span></span> | <span data-ttu-id="b59d9-198">Завершение срока службы</span><span class="sxs-lookup"><span data-stu-id="b59d9-198">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="b59d9-199">Fedora</span><span class="sxs-lookup"><span data-stu-id="b59d9-199">Fedora</span></span>   | <span data-ttu-id="b59d9-200">24</span><span class="sxs-lookup"><span data-stu-id="b59d9-200">24</span></span>      | [<span data-ttu-id="b59d9-201">Август 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-201">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="b59d9-202">Fedora</span><span class="sxs-lookup"><span data-stu-id="b59d9-202">Fedora</span></span>   | <span data-ttu-id="b59d9-203">25</span><span class="sxs-lookup"><span data-stu-id="b59d9-203">25</span></span>      | [<span data-ttu-id="b59d9-204">Декабрь 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-204">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="b59d9-205">Fedora</span><span class="sxs-lookup"><span data-stu-id="b59d9-205">Fedora</span></span>   | <span data-ttu-id="b59d9-206">26</span><span class="sxs-lookup"><span data-stu-id="b59d9-206">26</span></span>      | [<span data-ttu-id="b59d9-207">Май 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-207">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="b59d9-208">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b59d9-208">openSUSE</span></span> | <span data-ttu-id="b59d9-209">42.1</span><span class="sxs-lookup"><span data-stu-id="b59d9-209">42.1</span></span>    | [<span data-ttu-id="b59d9-210">Май 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-210">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="b59d9-211">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b59d9-211">openSUSE</span></span> | <span data-ttu-id="b59d9-212">42.2</span><span class="sxs-lookup"><span data-stu-id="b59d9-212">42.2</span></span>    | [<span data-ttu-id="b59d9-213">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-213">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="b59d9-214">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b59d9-214">Ubuntu</span></span>   | <span data-ttu-id="b59d9-215">16.10</span><span class="sxs-lookup"><span data-stu-id="b59d9-215">16.10</span></span>   | [<span data-ttu-id="b59d9-216">Июль 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-216">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="b59d9-217">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b59d9-217">Ubuntu</span></span>   | <span data-ttu-id="b59d9-218">17.04</span><span class="sxs-lookup"><span data-stu-id="b59d9-218">17.04</span></span>   | [<span data-ttu-id="b59d9-219">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-219">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="b59d9-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b59d9-220">Ubuntu</span></span>   | <span data-ttu-id="b59d9-221">17.10</span><span class="sxs-lookup"><span data-stu-id="b59d9-221">17.10</span></span>   | [<span data-ttu-id="b59d9-222">Июль 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-222">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="b59d9-223">Debian</span><span class="sxs-lookup"><span data-stu-id="b59d9-223">Debian</span></span>   | <span data-ttu-id="b59d9-224">8</span><span class="sxs-lookup"><span data-stu-id="b59d9-224">8</span></span>       | [<span data-ttu-id="b59d9-225">Июнь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-225">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="b59d9-226">Fedora</span><span class="sxs-lookup"><span data-stu-id="b59d9-226">Fedora</span></span>   | <span data-ttu-id="b59d9-227">27</span><span class="sxs-lookup"><span data-stu-id="b59d9-227">27</span></span>      | [<span data-ttu-id="b59d9-228">Ноябрь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-228">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="b59d9-229">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b59d9-229">Ubuntu</span></span>   | <span data-ttu-id="b59d9-230">14.04</span><span class="sxs-lookup"><span data-stu-id="b59d9-230">14.04</span></span>   | [<span data-ttu-id="b59d9-231">Апрель 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b59d9-231">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="b59d9-232">Замечания по лицензированию</span><span class="sxs-lookup"><span data-stu-id="b59d9-232">Notes on licensing</span></span>

<span data-ttu-id="b59d9-233">PowerShell Core выпускается по [Лицензия MIT][].</span><span class="sxs-lookup"><span data-stu-id="b59d9-233">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="b59d9-234">По этой лицензии и без соглашения о платной подписке пользователям предоставляется только [поддержку сообщества][].</span><span class="sxs-lookup"><span data-stu-id="b59d9-234">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="b59d9-235">В рамках поддержки сообщества корпорация Майкрософт не предоставляет никаких гарантий оперативного реагирования или выпуска исправлений.</span><span class="sxs-lookup"><span data-stu-id="b59d9-235">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="b59d9-236">Модуль Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b59d9-236">Windows PowerShell Module</span></span>

<span data-ttu-id="b59d9-237">Поддержка PowerShell Core не распространяется на другие модули продукта, если только они не поддерживают PowerShell Core явным образом.</span><span class="sxs-lookup"><span data-stu-id="b59d9-237">Support for PowerShell Core does not include product modules, unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="b59d9-238">Например, использование модуля `ActiveDirectory`, который поставляется в составе Windows Server, является неподдерживаемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="b59d9-238">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="b59d9-239">Однако в некоторых случаях модули, которые не поддерживают PowerShell Core явным образом, могут быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="b59d9-239">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="b59d9-240">Установив модуль [`WindowsPSModulePath`][], можно добавить `PSModulePath` Windows PowerShell в `PSModulePath` PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="b59d9-240">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="b59d9-241">Сначала установите модуль `WindowsPSModulePath` из коллекции PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b59d9-241">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="b59d9-242">После установки модуля запустите командлет `Add-WindowsPSModulePath`, чтобы добавить `PSModulePath` Windows PowerShell в PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="b59d9-242">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="b59d9-243">Экспериментальные функции</span><span class="sxs-lookup"><span data-stu-id="b59d9-243">Experimental features</span></span>

<span data-ttu-id="b59d9-244">Для [Экспериментальные функции][] предоставляется только [поддержка сообщества](#community-support).</span><span class="sxs-lookup"><span data-stu-id="b59d9-244">[Experimental features][] are limited to [community support](#community-support).</span></span>

[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[поддержку сообщества]: https://github.com/powershell/powershell/issues
[community support]: https://github.com/powershell/powershell/issues
[Microsoft Community]: https://answers.microsoft.com/
[PowerShell Tech Community]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[техническую поддержку]: https://support.microsoft.com/assistedsupportproducts
[assisted support]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[Лицензия MIT]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[MIT license]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
["WindowsPSModulePath"]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[`WindowsPSModulePath`]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Экспериментальные функции]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
[Experimental features]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
