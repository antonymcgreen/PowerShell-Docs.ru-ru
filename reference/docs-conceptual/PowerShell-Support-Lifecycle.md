---
title: Жизненный цикл поддержки PowerShell Core
description: Политики, распространяемые на поддержку PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: b8dd4891ecf245b87c3fe2fa61cd241a12209b57
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854381"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="a363a-103">Жизненный цикл поддержки PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="a363a-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="a363a-104">PowerShell Core — это отдельный набор средств и компонентов, поставляемых, устанавливаемых и настраиваемых отдельно от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a363a-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="a363a-105">Поэтому на PowerShell Core не распространяются лицензионные соглашения Windows 7, 8.1, 10 или Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a363a-105">So, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="a363a-106">Однако PowerShell Core поддерживается в рамках традиционных соглашений о поддержке корпорации Майкрософт, включая [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement] и [Microsoft Software Assurance][assurance].</span><span class="sxs-lookup"><span data-stu-id="a363a-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="a363a-107">Вы также можете оплатить [техническую поддержку][] по PowerShell Core, направив в службу поддержки запрос о своей проблеме.</span><span class="sxs-lookup"><span data-stu-id="a363a-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="a363a-108">Поддержка сообщества</span><span class="sxs-lookup"><span data-stu-id="a363a-108">Community Support</span></span>

<span data-ttu-id="a363a-109">Мы также предлагаем [поддержку сообщества][] на GitHub, где вы можете зарегистрировать вопрос, ошибку или запрос функции.</span><span class="sxs-lookup"><span data-stu-id="a363a-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="a363a-110">Кроме того, вы можете обратиться за помощью к другим членам сообщества на сайтах [Microsoft Community][] или Microsoft [PowerShell Tech Community][].</span><span class="sxs-lookup"><span data-stu-id="a363a-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="a363a-111">Но мы не можем гарантировать, что там вам оперативно помогут решить вашу проблему.</span><span class="sxs-lookup"><span data-stu-id="a363a-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span>
<span data-ttu-id="a363a-112">Если ваша проблема требует немедленного вмешательства, следует использовать традиционные платные варианты поддержки.</span><span class="sxs-lookup"><span data-stu-id="a363a-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="a363a-113">Жизненный цикл PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="a363a-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="a363a-114">В PowerShell Core внедряется [политика современного жизненного цикла Майкрософт][modern].</span><span class="sxs-lookup"><span data-stu-id="a363a-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="a363a-115">Этот жизненный цикл поддержки предназначен для предоставления клиентам актуальных версий.</span><span class="sxs-lookup"><span data-stu-id="a363a-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="a363a-116">Ветвь PowerShell Core версии 6.x будет обновляться примерно каждые шесть месяцев: 6.0, 6.1, 6.2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="a363a-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a363a-117">Чтобы продолжить получать поддержку, вам нужно обновить продукт в течение шести месяцев после выпуска версии с новым дополнительным номером.</span><span class="sxs-lookup"><span data-stu-id="a363a-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="a363a-118">Например, если версия PowerShell Core 6.1 выпущена 1 июля 2018 г., чтобы продолжать получать поддержку, вам нужно выполнить обновление до версии PowerShell Core 6.1 к 1 января 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a363a-119">Кроме того, вам нужно обновлять продукт в течение 30 дней после выпуска версии с новым исправлением.</span><span class="sxs-lookup"><span data-stu-id="a363a-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="a363a-120">Например, если вы используете PowerShell Core 6.1, а версия 6.1.3 выпущена 19 февраля 2019 г., вам нужно выполнить обновление до версии PowerShell Core 6.1.3 в течение 30 дней, т. е. до 21 марта 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-120">For example, If you are running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span>
<span data-ttu-id="a363a-121">Если требуется какие-либо исправления, они будут включены в наше следующе накопительное обновление.</span><span class="sxs-lookup"><span data-stu-id="a363a-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

<span data-ttu-id="a363a-122">Согласно политике современного жизненного цикла также требуется, чтобы корпорация Майкрософт предоставляла клиентам уведомление за 12 месяцев до прекращения поддержки продукта (например, PowerShell Core).</span><span class="sxs-lookup"><span data-stu-id="a363a-122">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="a363a-123">Со временем мы планируем реализовать для PowerShell Core возможность долгосрочного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a363a-123">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach.</span></span>
<span data-ttu-id="a363a-124">Это позволит нам осуществлять обслуживание и выпускать обновления для системы безопасности, чтобы обеспечить поддержку определенной ветви или версии 6.x.</span><span class="sxs-lookup"><span data-stu-id="a363a-124">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="a363a-125">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="a363a-125">Supported platforms</span></span>

<span data-ttu-id="a363a-126">В таблице ниже указано, какая платформа используемой версии PowerShell Core официально поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a363a-126">The following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="a363a-127">Наше сообщество также предоставило пакеты для некоторых платформ, но они не поддерживаются официально.</span><span class="sxs-lookup"><span data-stu-id="a363a-127">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="a363a-128">Эти пакеты, отмечены как `Community` в таблице.</span><span class="sxs-lookup"><span data-stu-id="a363a-128">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="a363a-129">Отмеченные как `Experimental` платформы официально не поддерживаются, но доступны для экспериментов с возможностью обратной связи.</span><span class="sxs-lookup"><span data-stu-id="a363a-129">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="a363a-130">6.1</span><span class="sxs-lookup"><span data-stu-id="a363a-130">6.1</span></span>         | <span data-ttu-id="a363a-131">6.2</span><span class="sxs-lookup"><span data-stu-id="a363a-131">6.2</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="a363a-132">Windows 7, 8.1 и 10</span><span class="sxs-lookup"><span data-stu-id="a363a-132">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="a363a-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-133">Supported</span></span>   | <span data-ttu-id="a363a-134">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-134">Supported</span></span>   |
| <span data-ttu-id="a363a-135">Windows Server 2008 R2, 2012 R2, 2016</span><span class="sxs-lookup"><span data-stu-id="a363a-135">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="a363a-136">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-136">Supported</span></span>   | <span data-ttu-id="a363a-137">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-137">Supported</span></span>   |
| <span data-ttu-id="a363a-138">[Windows Server Semi-Annual Channel][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="a363a-138">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="a363a-139">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-139">Supported</span></span>   | <span data-ttu-id="a363a-140">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-140">Supported</span></span>   |
| <span data-ttu-id="a363a-141">Ubuntu 16.04 и 18.04</span><span class="sxs-lookup"><span data-stu-id="a363a-141">Ubuntu 16.04 and 18.04</span></span>                            | <span data-ttu-id="a363a-142">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-142">Supported</span></span>   | <span data-ttu-id="a363a-143">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-143">Supported</span></span>   |
| <span data-ttu-id="a363a-144">Ubuntu 18.10 (с помощью snap-пакета)</span><span class="sxs-lookup"><span data-stu-id="a363a-144">Ubuntu 18.10 (via Snap Package)</span></span>                   | <span data-ttu-id="a363a-145">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-145">Community</span></span>   | <span data-ttu-id="a363a-146">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-146">Community</span></span>   |
| <span data-ttu-id="a363a-147">Debian 9</span><span class="sxs-lookup"><span data-stu-id="a363a-147">Debian 9</span></span>                                          | <span data-ttu-id="a363a-148">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-148">Supported</span></span>   | <span data-ttu-id="a363a-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-149">Supported</span></span>   |
| <span data-ttu-id="a363a-150">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="a363a-150">CentOS 7</span></span>                                          | <span data-ttu-id="a363a-151">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-151">Supported</span></span>   | <span data-ttu-id="a363a-152">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-152">Supported</span></span>   |
| <span data-ttu-id="a363a-153">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="a363a-153">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="a363a-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-154">Supported</span></span>   | <span data-ttu-id="a363a-155">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-155">Supported</span></span>   |
| <span data-ttu-id="a363a-156">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="a363a-156">openSUSE 42.3</span></span>                                     | <span data-ttu-id="a363a-157">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-157">Supported</span></span>   | <span data-ttu-id="a363a-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-158">Supported</span></span>   |
| <span data-ttu-id="a363a-159">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="a363a-159">Fedora 28</span></span>                                         | <span data-ttu-id="a363a-160">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-160">Supported</span></span>   | <span data-ttu-id="a363a-161">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-161">Supported</span></span>   |
| <span data-ttu-id="a363a-162">macOS 10.12+</span><span class="sxs-lookup"><span data-stu-id="a363a-162">macOS 10.12+</span></span>                                      | <span data-ttu-id="a363a-163">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-163">Supported</span></span>   | <span data-ttu-id="a363a-164">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="a363a-164">Supported</span></span>   |
| <span data-ttu-id="a363a-165">Arch</span><span class="sxs-lookup"><span data-stu-id="a363a-165">Arch</span></span>                                              | <span data-ttu-id="a363a-166">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-166">Community</span></span>   | <span data-ttu-id="a363a-167">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-167">Community</span></span>   |
| <span data-ttu-id="a363a-168">Raspbian</span><span class="sxs-lookup"><span data-stu-id="a363a-168">Raspbian</span></span>                                          | <span data-ttu-id="a363a-169">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-169">Community</span></span>   | <span data-ttu-id="a363a-170">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-170">Community</span></span>   |
| <span data-ttu-id="a363a-171">Kali</span><span class="sxs-lookup"><span data-stu-id="a363a-171">Kali</span></span>                                              | <span data-ttu-id="a363a-172">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-172">Community</span></span>   | <span data-ttu-id="a363a-173">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-173">Community</span></span>   |
| <span data-ttu-id="a363a-174">AppImage (работает на нескольких платформах Linux)</span><span class="sxs-lookup"><span data-stu-id="a363a-174">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="a363a-175">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-175">Community</span></span>   | <span data-ttu-id="a363a-176">Сообщество</span><span class="sxs-lookup"><span data-stu-id="a363a-176">Community</span></span>   |
| [<span data-ttu-id="a363a-177">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="a363a-177">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="a363a-178">См. примечание</span><span class="sxs-lookup"><span data-stu-id="a363a-178">See note</span></span>    | <span data-ttu-id="a363a-179">См. примечание</span><span class="sxs-lookup"><span data-stu-id="a363a-179">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="a363a-180">Прикрепленные пакеты поддерживаются так же, как и соответствующий дистрибутив.</span><span class="sxs-lookup"><span data-stu-id="a363a-180">Snap packages are supported the same as the distribution you are running the package on.</span></span>

## <a name="powershell-release-end-of-life"></a><span data-ttu-id="a363a-181">Завершение жизненного цикла PowerShell</span><span class="sxs-lookup"><span data-stu-id="a363a-181">PowerShell release end of life</span></span>

<span data-ttu-id="a363a-182">В следующей таблице перечислены даты прекращения поддержки разных выпусков PowerShell Core с учетом [жизненного цикла этого продукта](#lifecycle-of-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="a363a-182">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various release will no longer be supported.</span></span>

| <span data-ttu-id="a363a-183">Версия</span><span class="sxs-lookup"><span data-stu-id="a363a-183">Version</span></span> | <span data-ttu-id="a363a-184">Завершение срока службы</span><span class="sxs-lookup"><span data-stu-id="a363a-184">End Of Life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="a363a-185">6.0</span><span class="sxs-lookup"><span data-stu-id="a363a-185">6.0</span></span>     | <span data-ttu-id="a363a-186">13 февраля 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-186">February 13, 2019</span></span>             |
| <span data-ttu-id="a363a-187">6.1</span><span class="sxs-lookup"><span data-stu-id="a363a-187">6.1</span></span>     | <span data-ttu-id="a363a-188">28 сентября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-188">September 28, 2019</span></span>            |
| <span data-ttu-id="a363a-189">6.2</span><span class="sxs-lookup"><span data-stu-id="a363a-189">6.2</span></span>     | <span data-ttu-id="a363a-190">6 месяцев после выпуска версии 7</span><span class="sxs-lookup"><span data-stu-id="a363a-190">6 months after 7 releases</span></span>     |

## <a name="platforms-which-are-out-of-support"></a><span data-ttu-id="a363a-191">Неподдерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="a363a-191">Platforms, which are out of support</span></span>

<span data-ttu-id="a363a-192">По завершении жизненного цикла определенной версии платформы (определяется ее владельцем), прекращается ее поддержка в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="a363a-192">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span>
<span data-ttu-id="a363a-193">Предыдущие выпуски пакетов останутся доступными для клиентов, которым требуется доступ, но официальная поддержка и обновления больше не будет предоставляться.</span><span class="sxs-lookup"><span data-stu-id="a363a-193">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="a363a-194">Таким образом, поддержка следующих версий прекращается владельцами дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="a363a-194">So, the distribution owners ended support for the following versions and are not supported.</span></span>

| <span data-ttu-id="a363a-195">ОС</span><span class="sxs-lookup"><span data-stu-id="a363a-195">OS</span></span>       | <span data-ttu-id="a363a-196">Версия</span><span class="sxs-lookup"><span data-stu-id="a363a-196">Version</span></span> | <span data-ttu-id="a363a-197">Завершение срока службы</span><span class="sxs-lookup"><span data-stu-id="a363a-197">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="a363a-198">Fedora</span><span class="sxs-lookup"><span data-stu-id="a363a-198">Fedora</span></span>   | <span data-ttu-id="a363a-199">24</span><span class="sxs-lookup"><span data-stu-id="a363a-199">24</span></span>      | [<span data-ttu-id="a363a-200">Август 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-200">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="a363a-201">Fedora</span><span class="sxs-lookup"><span data-stu-id="a363a-201">Fedora</span></span>   | <span data-ttu-id="a363a-202">25</span><span class="sxs-lookup"><span data-stu-id="a363a-202">25</span></span>      | [<span data-ttu-id="a363a-203">Декабрь 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-203">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="a363a-204">Fedora</span><span class="sxs-lookup"><span data-stu-id="a363a-204">Fedora</span></span>   | <span data-ttu-id="a363a-205">26</span><span class="sxs-lookup"><span data-stu-id="a363a-205">26</span></span>      | [<span data-ttu-id="a363a-206">Май 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-206">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="a363a-207">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a363a-207">openSUSE</span></span> | <span data-ttu-id="a363a-208">42.1</span><span class="sxs-lookup"><span data-stu-id="a363a-208">42.1</span></span>    | [<span data-ttu-id="a363a-209">Май 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-209">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="a363a-210">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a363a-210">openSUSE</span></span> | <span data-ttu-id="a363a-211">42.2</span><span class="sxs-lookup"><span data-stu-id="a363a-211">42.2</span></span>    | [<span data-ttu-id="a363a-212">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-212">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="a363a-213">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a363a-213">Ubuntu</span></span>   | <span data-ttu-id="a363a-214">16.10</span><span class="sxs-lookup"><span data-stu-id="a363a-214">16.10</span></span>   | [<span data-ttu-id="a363a-215">Июль 2017 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-215">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="a363a-216">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a363a-216">Ubuntu</span></span>   | <span data-ttu-id="a363a-217">17.04</span><span class="sxs-lookup"><span data-stu-id="a363a-217">17.04</span></span>   | [<span data-ttu-id="a363a-218">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-218">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="a363a-219">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a363a-219">Ubuntu</span></span>   | <span data-ttu-id="a363a-220">17.10</span><span class="sxs-lookup"><span data-stu-id="a363a-220">17.10</span></span>   | [<span data-ttu-id="a363a-221">Июль 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-221">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="a363a-222">Debian</span><span class="sxs-lookup"><span data-stu-id="a363a-222">Debian</span></span>   | <span data-ttu-id="a363a-223">8</span><span class="sxs-lookup"><span data-stu-id="a363a-223">8</span></span>       | [<span data-ttu-id="a363a-224">Июнь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-224">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="a363a-225">Fedora</span><span class="sxs-lookup"><span data-stu-id="a363a-225">Fedora</span></span>   | <span data-ttu-id="a363a-226">27</span><span class="sxs-lookup"><span data-stu-id="a363a-226">27</span></span>      | [<span data-ttu-id="a363a-227">Ноябрь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-227">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="a363a-228">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a363a-228">Ubuntu</span></span>   | <span data-ttu-id="a363a-229">14.04</span><span class="sxs-lookup"><span data-stu-id="a363a-229">14.04</span></span>   | [<span data-ttu-id="a363a-230">Апрель 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a363a-230">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="a363a-231">Замечания по лицензированию</span><span class="sxs-lookup"><span data-stu-id="a363a-231">Notes on licensing</span></span>

<span data-ttu-id="a363a-232">PowerShell Core выпускается по [Лицензия MIT][].</span><span class="sxs-lookup"><span data-stu-id="a363a-232">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="a363a-233">По этой лицензии и без соглашения о платной подписке пользователям предоставляется только [поддержку сообщества][].</span><span class="sxs-lookup"><span data-stu-id="a363a-233">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="a363a-234">В рамках поддержки сообщества корпорация Майкрософт не предоставляет никаких гарантий оперативного реагирования или выпуска исправлений.</span><span class="sxs-lookup"><span data-stu-id="a363a-234">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="a363a-235">Модуль Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a363a-235">Windows PowerShell Module</span></span>

<span data-ttu-id="a363a-236">Поддержка PowerShell Core не распространяется на другие модули продукта, если только они не поддерживают PowerShell Core явным образом.</span><span class="sxs-lookup"><span data-stu-id="a363a-236">Support for PowerShell Core does not include product modules, unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="a363a-237">Например, использование модуля `ActiveDirectory`, который поставляется в составе Windows Server, является неподдерживаемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="a363a-237">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="a363a-238">Однако в некоторых случаях модули, которые не поддерживают PowerShell Core явным образом, могут быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="a363a-238">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="a363a-239">Установив модуль [`WindowsPSModulePath`][], можно добавить `PSModulePath` Windows PowerShell в `PSModulePath` PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="a363a-239">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="a363a-240">Сначала установите модуль `WindowsPSModulePath` из коллекции PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a363a-240">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="a363a-241">После установки модуля запустите командлет `Add-WindowsPSModulePath`, чтобы добавить `PSModulePath` Windows PowerShell в PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="a363a-241">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="a363a-242">Экспериментальные функции</span><span class="sxs-lookup"><span data-stu-id="a363a-242">Experimental features</span></span>

<span data-ttu-id="a363a-243">Для [Экспериментальные функции][] предоставляется только [поддержка сообщества](#community-support).</span><span class="sxs-lookup"><span data-stu-id="a363a-243">[Experimental features][] are limited to [community support](#community-support).</span></span>

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
