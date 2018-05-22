---
ms.topic: reference
keywords: powershell,командлет
ms.date: 12/12/2016
title: Uninstall-PswaWebApplication
ms.openlocfilehash: b2a3e4d584fd04ee49e1e6408dba39fd8bc555dc
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="uninstall-pswawebapplication"></a><span data-ttu-id="1651f-103">Uninstall-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="1651f-103">Uninstall-PswaWebApplication</span></span>

## <a name="synopsis"></a><span data-ttu-id="1651f-104">КРАТКИЙ ОБЗОР</span><span class="sxs-lookup"><span data-stu-id="1651f-104">SYNOPSIS</span></span>

<span data-ttu-id="1651f-105">Удаляет веб-приложение Windows PowerShell® Web Access.</span><span class="sxs-lookup"><span data-stu-id="1651f-105">Uninstalls the Windows PowerShell® web application.</span></span>

## <a name="syntax"></a><span data-ttu-id="1651f-106">СИНТАКСИС</span><span class="sxs-lookup"><span data-stu-id="1651f-106">SYNTAX</span></span>

### <a name="default"></a><span data-ttu-id="1651f-107">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-107">Default</span></span>
```
Uninstall-PswaWebApplication [[-WebApplicationName] <String> ] [-DeleteTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="1651f-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="1651f-108">DESCRIPTION</span></span>

<span data-ttu-id="1651f-109">Командлет **Uninstall-PswaWebApplication** удаляет веб-приложение Windows PowerShell и веб-сайт с сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="1651f-109">The **Uninstall-PswaWebApplication** cmdlet uninstalls the Windows PowerShell web application and removes the website from IIS.</span></span> <span data-ttu-id="1651f-110">Командлет не удаляет службы IIS или другие установленные компоненты, так как они требуются для работы Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1651f-110">The cmdlet does not uninstall IIS, or any other features installed because they were required for Windows PowerShell to run.</span></span>

## <a name="parameters"></a><span data-ttu-id="1651f-111">ПАРАМЕТРЫ</span><span class="sxs-lookup"><span data-stu-id="1651f-111">PARAMETERS</span></span>

### <a name="-deletetestcertificate"></a><span data-ttu-id="1651f-112">-DeleteTestCertificate</span><span class="sxs-lookup"><span data-stu-id="1651f-112">-DeleteTestCertificate</span></span>

<span data-ttu-id="1651f-113">Указывает, что тестовые сертификаты, созданные командлетом **Install\_PswaWebApplication** (с параметром **UseTestCertificate**), удаляются.</span><span class="sxs-lookup"><span data-stu-id="1651f-113">Indicates that the test certificates created by the **Install\_PswaWebApplication** cmdlet (with the **UseTestCertificate** parameter) is deleted.</span></span>
<span data-ttu-id="1651f-114">Удаляется только тестовый сертификат с тем же именем, что и созданный командлетом **Install-PswaWebApplication**.</span><span class="sxs-lookup"><span data-stu-id="1651f-114">Only the test certificate with the same name as the one created by the **Install-PswaWebApplication** cmdlet is removed.</span></span>

|||
|-|-|
| <span data-ttu-id="1651f-115">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="1651f-115">Aliases</span></span>                              | <span data-ttu-id="1651f-116">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1651f-116">none</span></span>                                 |
| <span data-ttu-id="1651f-117">Требуется?</span><span class="sxs-lookup"><span data-stu-id="1651f-117">Required?</span></span>                            | <span data-ttu-id="1651f-118">false</span><span class="sxs-lookup"><span data-stu-id="1651f-118">false</span></span>                                |
| <span data-ttu-id="1651f-119">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="1651f-119">Position?</span></span>                            | <span data-ttu-id="1651f-120">с именем</span><span class="sxs-lookup"><span data-stu-id="1651f-120">named</span></span>                                |
| <span data-ttu-id="1651f-121">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-121">Default Value</span></span>                        | <span data-ttu-id="1651f-122">верно</span><span class="sxs-lookup"><span data-stu-id="1651f-122">true</span></span>                                 |
| <span data-ttu-id="1651f-123">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="1651f-123">Accept Pipeline Input?</span></span>               | <span data-ttu-id="1651f-124">false</span><span class="sxs-lookup"><span data-stu-id="1651f-124">false</span></span>                                |
| <span data-ttu-id="1651f-125">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="1651f-125">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="1651f-126">false</span><span class="sxs-lookup"><span data-stu-id="1651f-126">false</span></span>                                |

### <a name="-webapplicationname-ltstringgt"></a><span data-ttu-id="1651f-127">-WebApplicationName &lt;строка&gt;</span><span class="sxs-lookup"><span data-stu-id="1651f-127">-WebApplicationName &lt;String&gt;</span></span>

<span data-ttu-id="1651f-128">Указывает имя удаляемого веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="1651f-128">Specifies the name of the web application to uninstall.</span></span>

|||
|-|-|
| <span data-ttu-id="1651f-129">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="1651f-129">Aliases</span></span>                              | <span data-ttu-id="1651f-130">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1651f-130">none</span></span>                                 |
| <span data-ttu-id="1651f-131">Требуется?</span><span class="sxs-lookup"><span data-stu-id="1651f-131">Required?</span></span>                            | <span data-ttu-id="1651f-132">false</span><span class="sxs-lookup"><span data-stu-id="1651f-132">false</span></span>                                |
| <span data-ttu-id="1651f-133">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="1651f-133">Position?</span></span>                            | <span data-ttu-id="1651f-134">1</span><span class="sxs-lookup"><span data-stu-id="1651f-134">1</span></span>                                    |
| <span data-ttu-id="1651f-135">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-135">Default Value</span></span>                        | <span data-ttu-id="1651f-136">pswa</span><span class="sxs-lookup"><span data-stu-id="1651f-136">pswa</span></span>                                 |
| <span data-ttu-id="1651f-137">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="1651f-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="1651f-138">false</span><span class="sxs-lookup"><span data-stu-id="1651f-138">false</span></span>                                |
| <span data-ttu-id="1651f-139">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="1651f-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="1651f-140">false</span><span class="sxs-lookup"><span data-stu-id="1651f-140">false</span></span>                                |

### <a name="-websitename-ltstringgt"></a><span data-ttu-id="1651f-141">-WebSiteName &lt;строка&gt;</span><span class="sxs-lookup"><span data-stu-id="1651f-141">-WebSiteName &lt;String&gt;</span></span>

<span data-ttu-id="1651f-142">Задает имя веб-сайта, на котором установлено веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="1651f-142">Specifies the name of the web site where the web application is installed.</span></span>

|||
|-|-|
| <span data-ttu-id="1651f-143">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="1651f-143">Aliases</span></span>                              | <span data-ttu-id="1651f-144">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1651f-144">none</span></span>                                 |
| <span data-ttu-id="1651f-145">Требуется?</span><span class="sxs-lookup"><span data-stu-id="1651f-145">Required?</span></span>                            | <span data-ttu-id="1651f-146">false</span><span class="sxs-lookup"><span data-stu-id="1651f-146">false</span></span>                                |
| <span data-ttu-id="1651f-147">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="1651f-147">Position?</span></span>                            | <span data-ttu-id="1651f-148">с именем</span><span class="sxs-lookup"><span data-stu-id="1651f-148">named</span></span>                                |
| <span data-ttu-id="1651f-149">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-149">Default Value</span></span>                        | <span data-ttu-id="1651f-150">Веб-сайт по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-150">Default Web Site</span></span>                     |
| <span data-ttu-id="1651f-151">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="1651f-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="1651f-152">false</span><span class="sxs-lookup"><span data-stu-id="1651f-152">false</span></span>                                |
| <span data-ttu-id="1651f-153">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="1651f-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="1651f-154">false</span><span class="sxs-lookup"><span data-stu-id="1651f-154">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="1651f-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1651f-155">-Confirm</span></span>

<span data-ttu-id="1651f-156">Запрос на подтверждение перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1651f-156">Prompts you for confirmation before running the cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="1651f-157">Требуется?</span><span class="sxs-lookup"><span data-stu-id="1651f-157">Required?</span></span>                            | <span data-ttu-id="1651f-158">false</span><span class="sxs-lookup"><span data-stu-id="1651f-158">false</span></span>                                |
| <span data-ttu-id="1651f-159">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="1651f-159">Position?</span></span>                            | <span data-ttu-id="1651f-160">с именем</span><span class="sxs-lookup"><span data-stu-id="1651f-160">named</span></span>                                |
| <span data-ttu-id="1651f-161">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-161">Default Value</span></span>                        | <span data-ttu-id="1651f-162">false</span><span class="sxs-lookup"><span data-stu-id="1651f-162">false</span></span>                                |
| <span data-ttu-id="1651f-163">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="1651f-163">Accept Pipeline Input?</span></span>               | <span data-ttu-id="1651f-164">false</span><span class="sxs-lookup"><span data-stu-id="1651f-164">false</span></span>                                |
| <span data-ttu-id="1651f-165">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="1651f-165">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="1651f-166">false</span><span class="sxs-lookup"><span data-stu-id="1651f-166">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="1651f-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1651f-167">-WhatIf</span></span>

<span data-ttu-id="1651f-168">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1651f-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1651f-169">Командлет не запущен.</span><span class="sxs-lookup"><span data-stu-id="1651f-169">The cmdlet is not run.</span></span>

|||
|-|-|
| <span data-ttu-id="1651f-170">Требуется?</span><span class="sxs-lookup"><span data-stu-id="1651f-170">Required?</span></span>                            | <span data-ttu-id="1651f-171">false</span><span class="sxs-lookup"><span data-stu-id="1651f-171">false</span></span>                                |
| <span data-ttu-id="1651f-172">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="1651f-172">Position?</span></span>                            | <span data-ttu-id="1651f-173">с именем</span><span class="sxs-lookup"><span data-stu-id="1651f-173">named</span></span>                                |
| <span data-ttu-id="1651f-174">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1651f-174">Default Value</span></span>                        | <span data-ttu-id="1651f-175">false</span><span class="sxs-lookup"><span data-stu-id="1651f-175">false</span></span>                                |
| <span data-ttu-id="1651f-176">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="1651f-176">Accept Pipeline Input?</span></span>               | <span data-ttu-id="1651f-177">false</span><span class="sxs-lookup"><span data-stu-id="1651f-177">false</span></span>                                |
| <span data-ttu-id="1651f-178">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="1651f-178">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="1651f-179">false</span><span class="sxs-lookup"><span data-stu-id="1651f-179">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="1651f-180">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="1651f-180">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="1651f-181">Данный командлет поддерживает общие параметры -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer и -OutVariable.</span><span class="sxs-lookup"><span data-stu-id="1651f-181">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="1651f-182">Дополнительные сведения см. в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1651f-182">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="1651f-183">ВХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="1651f-183">INPUTS</span></span>

<span data-ttu-id="1651f-184">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="1651f-184">This cmdlet takes no input.</span></span>

## <a name="outputs"></a><span data-ttu-id="1651f-185">ВЫХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="1651f-185">OUTPUTS</span></span>

<span data-ttu-id="1651f-186">Этот командлет не возвращает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1651f-186">This cmdlet returns no output.</span></span>

## <a name="examples"></a><span data-ttu-id="1651f-187">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="1651f-187">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="1651f-188">ПРИМЕР 1</span><span class="sxs-lookup"><span data-stu-id="1651f-188">EXAMPLE 1</span></span>

<span data-ttu-id="1651f-189">Эта команда удаляет веб-приложение Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1651f-189">This command uninstalls the Windows PowerShell Web Application.</span></span>
<span data-ttu-id="1651f-190">С помощью этого командлета можно удалить веб-приложение Windows PowerShell, если оно установлено с использованием значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1651f-190">You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values.</span></span>

```PowerShell
Uninstall-PswaWebApplication
```

### <a name="example-2"></a><span data-ttu-id="1651f-191">ПРИМЕР 2</span><span class="sxs-lookup"><span data-stu-id="1651f-191">EXAMPLE 2</span></span>

<span data-ttu-id="1651f-192">Эта команда удаляет веб-приложение Windows PowerShell, а также тестовый сертификат, связанный с приложением.</span><span class="sxs-lookup"><span data-stu-id="1651f-192">This command uninstalls the Windows PowerShell Web Application, and deletes the test certificate associated with the application.</span></span>
<span data-ttu-id="1651f-193">С помощью этого командлета можно удалить веб-приложение Windows PowerShell, если оно установлено с использованием значений по умолчанию, включая создание сертификата.</span><span class="sxs-lookup"><span data-stu-id="1651f-193">You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values and created a test certificate.</span></span>

```PowerShell
Uninstall-PswaWebApplication -DeleteTestCertificate
```

### <a name="example-3-example-3-subheading"></a><span data-ttu-id="1651f-194">ПРИМЕР 3 {#example-3 .subHeading}</span><span class="sxs-lookup"><span data-stu-id="1651f-194">EXAMPLE 3 {#example-3 .subHeading}</span></span>

<span data-ttu-id="1651f-195">Эта команда удаляет веб-приложение Windows PowerShell, если во время установки были указаны настраиваемый веб-сайт и приложение.</span><span class="sxs-lookup"><span data-stu-id="1651f-195">This command uninstalls the Windows PowerShell Web Application when a custom website and application were specified during the install.</span></span>
<span data-ttu-id="1651f-196">Эта команда удаляет веб-сайт с именем *MySite* и приложение с именем *TestApplication* и указывает, что тестовые сертификаты, связанные с приложением, также удаляются.</span><span class="sxs-lookup"><span data-stu-id="1651f-196">The command removes the website named *MySite* and the application named *TestApplication* and specifies that the test certificates associated with the application are also deleted.</span></span>

```
Uninstall-PswaWebApplication -WebApplicationName TestApplication -WebsiteName MySite -DeleteTestCertificate
```

## <a name="related-topics"></a><span data-ttu-id="1651f-197">Связанные темы</span><span class="sxs-lookup"><span data-stu-id="1651f-197">Related topics</span></span>

- [<span data-ttu-id="1651f-198">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="1651f-198">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="1651f-199">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="1651f-199">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="1651f-200">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="1651f-200">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="1651f-201">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="1651f-201">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)
- [<span data-ttu-id="1651f-202">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="1651f-202">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)