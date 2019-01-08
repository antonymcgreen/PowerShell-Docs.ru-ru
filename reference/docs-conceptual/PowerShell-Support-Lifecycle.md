---
title: Жизненный цикл поддержки PowerShell Core
description: Политики, распространяемые на поддержку PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: 2e0ca1b9c133e6f316a40aff13365d0489059165
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403496"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="1fcc1-103">Жизненный цикл поддержки PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="1fcc1-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="1fcc1-104">PowerShell Core — это отдельный набор средств и компонентов, поставляемых, устанавливаемых и настраиваемых отдельно от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="1fcc1-105">Поэтому на PowerShell Core не распространяются лицензионные соглашения Windows 7, 8.1, 10 или Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-105">Therefore, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="1fcc1-106">Однако PowerShell Core поддерживается в рамках традиционных соглашений о поддержке корпорации Майкрософт, включая [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement] и [Microsoft Software Assurance][assurance].</span><span class="sxs-lookup"><span data-stu-id="1fcc1-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="1fcc1-107">Вы также можете оплатить [техническую поддержку][] по PowerShell Core, направив в службу поддержки запрос о своей проблеме.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

<span data-ttu-id="1fcc1-108">Мы также предлагаем [поддержку сообщества][] на GitHub, где вы можете зарегистрировать вопрос, ошибку или запрос функции.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-108">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="1fcc1-109">Кроме того, вы можете обратиться за помощью к другим членам сообщества на сайтах [Microsoft Community][] или Microsoft [PowerShell Tech Community][].</span><span class="sxs-lookup"><span data-stu-id="1fcc1-109">Alternatively, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="1fcc1-110">Мы не можем гарантировать, что там вы оперативно получите решение своей проблемы.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-110">We offer no guarantee there that your issue will be addressed or resolved in a timely manner.</span></span>
<span data-ttu-id="1fcc1-111">Если ваша проблема требует немедленного вмешательства, следует использовать традиционные платные варианты поддержки.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-111">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="1fcc1-112">Жизненный цикл PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="1fcc1-112">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="1fcc1-113">В PowerShell Core внедряется [политика современного жизненного цикла Майкрософт][modern].</span><span class="sxs-lookup"><span data-stu-id="1fcc1-113">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="1fcc1-114">Этот жизненный цикл поддержки предназначен для предоставления клиентам актуальных версий.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-114">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="1fcc1-115">Ветвь версии 6.x продукта PowerShell Core будет обновляться примерно каждые шесть месяцев (то есть 6.0, 6.1, 6.2 и т. д.)</span><span class="sxs-lookup"><span data-stu-id="1fcc1-115">The version 6.x branch of PowerShell Core will be updated approximately once every six months (e.g. 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fcc1-116">Чтобы продолжить получать поддержку, вам нужно обновить продукт в течение шести месяцев после выпуска версии с новым дополнительным номером.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-116">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="1fcc1-117">Например, если PowerShell Core 6.1 выпущена 1 июля 2018 года, для сохранения поддержки вам следует обновиться до PowerShell Core 6.1 к 1 января 2019 года.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-117">For example, if PowerShell Core 6.1 is released on July 1st, 2018, you would be expected to update to PowerShell Core 6.1 by January 1st, 2019 to maintain support.</span></span>

![Жизненный цикл ветви PowerShell Core][lifecycle-chart]

<span data-ttu-id="1fcc1-119">Политика современного жизненного цикла также требует, чтобы корпорация Майкрософт предоставляла клиентам уведомление за 12 месяцев до прекращения поддержки продукта (т. е. PowerShell Core).</span><span class="sxs-lookup"><span data-stu-id="1fcc1-119">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (i.e. PowerShell Core).</span></span>

<span data-ttu-id="1fcc1-120">В конечном счете, мы планируем реализовать для PowerShell Core подход "долгосрочного обслуживания", чтобы нам требовалось лишь проводить обслуживание и выпускать обновления для системы безопасности, чтобы обеспечить поддержку определенной ветви или версии 6.x.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-120">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach where we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="1fcc1-121">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="1fcc1-121">Supported platforms</span></span>

<span data-ttu-id="1fcc1-122">См. ниже таблицу, чтобы узнать, какая платформа используемой версии PowerShell Core официально поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-122">Please see the following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="1fcc1-123">Наше сообщество также предоставило пакеты для некоторых платформ, но они не поддерживаются официально.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-123">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="1fcc1-124">Эти пакеты, отмечены как `Community` в таблице.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-124">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="1fcc1-125">Отмеченные как `Experimental` платформы официально не поддерживаются, но доступны для экспериментов с возможностью обратной связи.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-125">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="1fcc1-126">6.0</span><span class="sxs-lookup"><span data-stu-id="1fcc1-126">6.0</span></span>         | <span data-ttu-id="1fcc1-127">6.1</span><span class="sxs-lookup"><span data-stu-id="1fcc1-127">6.1</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="1fcc1-128">Windows 7, 8.1 и 10</span><span class="sxs-lookup"><span data-stu-id="1fcc1-128">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="1fcc1-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-129">Supported</span></span>   | <span data-ttu-id="1fcc1-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-130">Supported</span></span>   |
| <span data-ttu-id="1fcc1-131">Windows Server 2008 R2, 2012 R2, 2016</span><span class="sxs-lookup"><span data-stu-id="1fcc1-131">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="1fcc1-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-132">Supported</span></span>   | <span data-ttu-id="1fcc1-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-133">Supported</span></span>   |
| <span data-ttu-id="1fcc1-134">[Windows Server Semi-Annual Channel][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="1fcc1-134">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="1fcc1-135">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-135">Supported</span></span>   | <span data-ttu-id="1fcc1-136">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-136">Supported</span></span>   |
| <span data-ttu-id="1fcc1-137">Ubuntu 14.04 и 16.04</span><span class="sxs-lookup"><span data-stu-id="1fcc1-137">Ubuntu 14.04 and, 16.04</span></span>                           | <span data-ttu-id="1fcc1-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-138">Supported</span></span>   | <span data-ttu-id="1fcc1-139">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-139">Supported</span></span>   |
| <span data-ttu-id="1fcc1-140">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="1fcc1-140">Ubuntu 18.04</span></span>                                      |             | <span data-ttu-id="1fcc1-141">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-141">Supported</span></span>   |
| <span data-ttu-id="1fcc1-142">Ubuntu 18.10 (с помощью snap-пакета)</span><span class="sxs-lookup"><span data-stu-id="1fcc1-142">Ubuntu 18.10 (via Snap Package)</span></span>                   |             | <span data-ttu-id="1fcc1-143">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-143">Community</span></span>   |
| <span data-ttu-id="1fcc1-144">Debian 8.7+ и 9</span><span class="sxs-lookup"><span data-stu-id="1fcc1-144">Debian 8.7+, and 9</span></span>                                | <span data-ttu-id="1fcc1-145">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-145">Supported</span></span>   | <span data-ttu-id="1fcc1-146">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-146">Supported</span></span>   |
| <span data-ttu-id="1fcc1-147">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="1fcc1-147">CentOS 7</span></span>                                          | <span data-ttu-id="1fcc1-148">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-148">Supported</span></span>   | <span data-ttu-id="1fcc1-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-149">Supported</span></span>   |
| <span data-ttu-id="1fcc1-150">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="1fcc1-150">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="1fcc1-151">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-151">Supported</span></span>   | <span data-ttu-id="1fcc1-152">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-152">Supported</span></span>   |
| <span data-ttu-id="1fcc1-153">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="1fcc1-153">OpenSUSE 42.3</span></span>                                     | <span data-ttu-id="1fcc1-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-154">Supported</span></span>   | <span data-ttu-id="1fcc1-155">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-155">Supported</span></span>   |
| <span data-ttu-id="1fcc1-156">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="1fcc1-156">Fedora 27</span></span>                                         | <span data-ttu-id="1fcc1-157">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-157">Supported</span></span>   | <span data-ttu-id="1fcc1-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-158">Supported</span></span>   |
| <span data-ttu-id="1fcc1-159">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="1fcc1-159">Fedora 28</span></span>                                         |             | <span data-ttu-id="1fcc1-160">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-160">Supported</span></span>   |
| <span data-ttu-id="1fcc1-161">macOS 10.12+</span><span class="sxs-lookup"><span data-stu-id="1fcc1-161">macOS 10.12+</span></span>                                      | <span data-ttu-id="1fcc1-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-162">Supported</span></span>   | <span data-ttu-id="1fcc1-163">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="1fcc1-163">Supported</span></span>   |
| <span data-ttu-id="1fcc1-164">Arch</span><span class="sxs-lookup"><span data-stu-id="1fcc1-164">Arch</span></span>                                              | <span data-ttu-id="1fcc1-165">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-165">Community</span></span>   | <span data-ttu-id="1fcc1-166">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-166">Community</span></span>   |
| <span data-ttu-id="1fcc1-167">Raspbian</span><span class="sxs-lookup"><span data-stu-id="1fcc1-167">Raspbian</span></span>                                          | <span data-ttu-id="1fcc1-168">В экспериментальном режиме</span><span class="sxs-lookup"><span data-stu-id="1fcc1-168">Experimental</span></span>| <span data-ttu-id="1fcc1-169">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-169">Community</span></span>   |
| <span data-ttu-id="1fcc1-170">Kali</span><span class="sxs-lookup"><span data-stu-id="1fcc1-170">Kali</span></span>                                              | <span data-ttu-id="1fcc1-171">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-171">Community</span></span>   | <span data-ttu-id="1fcc1-172">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-172">Community</span></span>   |
| <span data-ttu-id="1fcc1-173">AppImage (работает на нескольких платформах Linux)</span><span class="sxs-lookup"><span data-stu-id="1fcc1-173">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="1fcc1-174">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-174">Community</span></span>   | <span data-ttu-id="1fcc1-175">Сообщество</span><span class="sxs-lookup"><span data-stu-id="1fcc1-175">Community</span></span>   |
| [<span data-ttu-id="1fcc1-176">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="1fcc1-176">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="1fcc1-177">См. примечание</span><span class="sxs-lookup"><span data-stu-id="1fcc1-177">See note</span></span>    | <span data-ttu-id="1fcc1-178">См. примечание</span><span class="sxs-lookup"><span data-stu-id="1fcc1-178">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="1fcc1-179">Snap-пакеты будут использоваться в экспериментальном режиме в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-179">Snap packages will be experimental for a period.</span></span>  <span data-ttu-id="1fcc1-180">Когда мы будем уверены в том, что snap-пакеты не вызывают новых проблем, поддержка будет распространена на дистрибутив, в котором вы запускаете пакет.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-180">After, we are confident that Snap does not introduce new support issues, the support will follow the distribution you are running the package on.</span></span>

## <a name="platform-which-are-out-of-support"></a><span data-ttu-id="1fcc1-181">Неподдерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="1fcc1-181">Platform which are out of support</span></span>

<span data-ttu-id="1fcc1-182">По истечении срока использования платформы, как определено владельцем платформы, в PowerShell Core прекращается поддержка для этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-182">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to provide support for that platform version.</span></span> <span data-ttu-id="1fcc1-183">Предыдущие выпуски пакетов останутся доступными для клиентов, которым требуется доступ, но официальная поддержка и обновления больше не будет предоставляться.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-183">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="1fcc1-184">Таким образом, поддержка следующих версий прекращается владельцами дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-184">Therefore, support for the following versions was ended by the distribution owners and are not supported.</span></span>

| <span data-ttu-id="1fcc1-185">ОС</span><span class="sxs-lookup"><span data-stu-id="1fcc1-185">OS</span></span>       | <span data-ttu-id="1fcc1-186">Версия</span><span class="sxs-lookup"><span data-stu-id="1fcc1-186">Version</span></span> | <span data-ttu-id="1fcc1-187">Завершение срока службы</span><span class="sxs-lookup"><span data-stu-id="1fcc1-187">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="1fcc1-188">Fedora</span><span class="sxs-lookup"><span data-stu-id="1fcc1-188">Fedora</span></span>   | <span data-ttu-id="1fcc1-189">24</span><span class="sxs-lookup"><span data-stu-id="1fcc1-189">24</span></span>      | [<span data-ttu-id="1fcc1-190">Август 2017 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-190">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="1fcc1-191">Fedora</span><span class="sxs-lookup"><span data-stu-id="1fcc1-191">Fedora</span></span>   | <span data-ttu-id="1fcc1-192">25</span><span class="sxs-lookup"><span data-stu-id="1fcc1-192">25</span></span>      | [<span data-ttu-id="1fcc1-193">Декабрь 2017 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-193">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="1fcc1-194">Fedora</span><span class="sxs-lookup"><span data-stu-id="1fcc1-194">Fedora</span></span>   | <span data-ttu-id="1fcc1-195">26</span><span class="sxs-lookup"><span data-stu-id="1fcc1-195">26</span></span>      | [<span data-ttu-id="1fcc1-196">Май 2018 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-196">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="1fcc1-197">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1fcc1-197">openSUSE</span></span> | <span data-ttu-id="1fcc1-198">42.1</span><span class="sxs-lookup"><span data-stu-id="1fcc1-198">42.1</span></span>    | [<span data-ttu-id="1fcc1-199">Май 2017 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-199">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="1fcc1-200">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1fcc1-200">openSUSE</span></span> | <span data-ttu-id="1fcc1-201">42.2</span><span class="sxs-lookup"><span data-stu-id="1fcc1-201">42.2</span></span>    | [<span data-ttu-id="1fcc1-202">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-202">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="1fcc1-203">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1fcc1-203">Ubuntu</span></span>   | <span data-ttu-id="1fcc1-204">16.10</span><span class="sxs-lookup"><span data-stu-id="1fcc1-204">16.10</span></span>   | [<span data-ttu-id="1fcc1-205">Июль 2017 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-205">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="1fcc1-206">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1fcc1-206">Ubuntu</span></span>   | <span data-ttu-id="1fcc1-207">17.04</span><span class="sxs-lookup"><span data-stu-id="1fcc1-207">17.04</span></span>   | [<span data-ttu-id="1fcc1-208">Январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-208">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="1fcc1-209">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1fcc1-209">Ubuntu</span></span>   | <span data-ttu-id="1fcc1-210">17.10</span><span class="sxs-lookup"><span data-stu-id="1fcc1-210">17.10</span></span>   | [<span data-ttu-id="1fcc1-211">Июль 2018 г.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-211">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |

## <a name="notes-on-licensing"></a><span data-ttu-id="1fcc1-212">Замечания по лицензированию</span><span class="sxs-lookup"><span data-stu-id="1fcc1-212">Notes on licensing</span></span>

<span data-ttu-id="1fcc1-213">PowerShell Core выпускается по [Лицензия MIT][].</span><span class="sxs-lookup"><span data-stu-id="1fcc1-213">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="1fcc1-214">Согласно этой лицензии и в отсутствие соглашения о платной подписке пользователи ограничены лишь [поддержку сообщества][].</span><span class="sxs-lookup"><span data-stu-id="1fcc1-214">Under this license, and in the absence of a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="1fcc1-215">В рамках поддержки сообщества корпорация Майкрософт не предоставляет никаких гарантий оперативного реагирования или выпуска исправлений.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-215">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="1fcc1-216">Модуль Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fcc1-216">Windows PowerShell Module</span></span>

<span data-ttu-id="1fcc1-217">Поддержка для PowerShell Core не распространяется на другие модули продукта, если только они не поддерживают PowerShell Core явным образом.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-217">Support for PowerShell Core does not extend to other product modules unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="1fcc1-218">Например, использование модуля `ActiveDirectory`, который поставляется в составе Windows Server, является неподдерживаемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-218">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="1fcc1-219">Однако в некоторых случаях модули, которые не поддерживают PowerShell Core явным образом, могут быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-219">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="1fcc1-220">Установив модуль [`WindowsPSModulePath`][] можно добавить `PSModulePath` Windows PowerShell в `PSModulePath` PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-220">By installing the [`WindowsPSModulePath`][] module, you can append the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="1fcc1-221">Сначала установите модуль `WindowsPSModulePath` из коллекции PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1fcc1-221">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="1fcc1-222">После установки модуля запустите командлет `Add-WindowsPSModulePath`, чтобы добавить `PSModulePath` Windows PowerShell в PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="1fcc1-222">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

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
