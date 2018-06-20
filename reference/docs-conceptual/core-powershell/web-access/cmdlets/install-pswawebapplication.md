---
ms.topic: reference
keywords: powershell,командлет
ms.date: 12/12/2016
title: Install-PswaWebApplication
ms.openlocfilehash: 68455d9490f7d5c33c1a928ac262a76a78ad7128
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189607"
---
# <a name="install-pswawebapplication"></a><span data-ttu-id="e95a9-103">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="e95a9-103">Install-PswaWebApplication</span></span>

## <a name="synopsis"></a><span data-ttu-id="e95a9-104">КРАТКИЙ ОБЗОР</span><span class="sxs-lookup"><span data-stu-id="e95a9-104">SYNOPSIS</span></span>

<span data-ttu-id="e95a9-105">Настраивает веб-приложение Windows PowerShell® Web Access в IIS.</span><span class="sxs-lookup"><span data-stu-id="e95a9-105">Configures the Windows PowerShell® Web Access web application in IIS.</span></span>

## <a name="syntax"></a><span data-ttu-id="e95a9-106">СИНТАКСИС</span><span class="sxs-lookup"><span data-stu-id="e95a9-106">SYNTAX</span></span>

### <a name="default"></a><span data-ttu-id="e95a9-107">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-107">Default</span></span>
```
Install-PswaWebApplication [[-WebApplicationName] <String> ] [-UseTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="e95a9-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="e95a9-108">DESCRIPTION</span></span>

<span data-ttu-id="e95a9-109">Командлет **Install-PswaWebApplication** настраивает веб-приложение Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="e95a9-109">The **Install-PswaWebApplication** cmdlet configures Windows PowerShell Web Access web application.</span></span> <span data-ttu-id="e95a9-110">Этот командлет устанавливает веб-приложение, связывает его с веб-сайтом и при необходимости создает тестовый сертификат SSL с помощью параметра **useTestCertificate**.</span><span class="sxs-lookup"><span data-stu-id="e95a9-110">This cmdlet installs the web application, associates it with a web site, and optionally creates a test SSL certificate using the **useTestCertificate** parameter.</span></span> <span data-ttu-id="e95a9-111">Для обеспечения безопасности веб-администраторам не следует использовать тестовый сертификат для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="e95a9-111">For security reasons web administrators should not use a test certificate for production environments.</span></span>

## <a name="parameters"></a><span data-ttu-id="e95a9-112">ПАРАМЕТРЫ</span><span class="sxs-lookup"><span data-stu-id="e95a9-112">PARAMETERS</span></span>

### <a name="-usetestcertificate"></a><span data-ttu-id="e95a9-113">-UseTestCertificate</span><span class="sxs-lookup"><span data-stu-id="e95a9-113">-UseTestCertificate</span></span>

<span data-ttu-id="e95a9-114">Указывает, что создается тестовый сертификат.</span><span class="sxs-lookup"><span data-stu-id="e95a9-114">Specifies that a test certificate is created.</span></span> <span data-ttu-id="e95a9-115">Если этот параметр имеет значение true, то командлет создает тестовый сертификат и настраивает веб-приложение Windows PowerShell Web Access для использования сертификата для HTTPS-запросов.</span><span class="sxs-lookup"><span data-stu-id="e95a9-115">If this parameter is set to true, then this cmdlet creates a test certificate and configures the Windows PowerShell Web Access web application to use the certificate for HTTPS requests.</span></span> <span data-ttu-id="e95a9-116">Если этот параметр имеет значение false, то ни сертификат, ни привязка не создаются.</span><span class="sxs-lookup"><span data-stu-id="e95a9-116">If this parameter is set to false, then no certificate or binding is created.</span></span> <span data-ttu-id="e95a9-117">Задайте значение false, если для Windows PowerShell Web Access используется другой сертификат.</span><span class="sxs-lookup"><span data-stu-id="e95a9-117">Set this value to false if another certificate is used for Windows PowerShell Web Access.</span></span>

|||
|-|-|
| <span data-ttu-id="e95a9-118">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="e95a9-118">Aliases</span></span>                              | <span data-ttu-id="e95a9-119">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e95a9-119">none</span></span>                                 |
| <span data-ttu-id="e95a9-120">Требуется?</span><span class="sxs-lookup"><span data-stu-id="e95a9-120">Required?</span></span>                            | <span data-ttu-id="e95a9-121">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-121">false</span></span>                                |
| <span data-ttu-id="e95a9-122">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="e95a9-122">Position?</span></span>                            | <span data-ttu-id="e95a9-123">с именем</span><span class="sxs-lookup"><span data-stu-id="e95a9-123">named</span></span>                                |
| <span data-ttu-id="e95a9-124">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-124">Default Value</span></span>                        | <span data-ttu-id="e95a9-125">верно</span><span class="sxs-lookup"><span data-stu-id="e95a9-125">true</span></span>                                 |
| <span data-ttu-id="e95a9-126">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="e95a9-126">Accept Pipeline Input?</span></span>               | <span data-ttu-id="e95a9-127">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-127">false</span></span>                                |
| <span data-ttu-id="e95a9-128">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="e95a9-128">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="e95a9-129">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-129">false</span></span>                                |

### <a name="-webapplicationnameltstringgt"></a><span data-ttu-id="e95a9-130">-WebApplicationName&lt;строка&gt;</span><span class="sxs-lookup"><span data-stu-id="e95a9-130">-WebApplicationName&lt;String&gt;</span></span>

<span data-ttu-id="e95a9-131">Указывает имя веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="e95a9-131">Specifies the name for your web application.</span></span> <span data-ttu-id="e95a9-132">Отображается как последняя часть URL-адреса Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="e95a9-132">This is displayed as the last part of the Windows PowerShell Web Access URL.</span></span>

|||
|-|-|
| <span data-ttu-id="e95a9-133">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="e95a9-133">Aliases</span></span>                              | <span data-ttu-id="e95a9-134">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e95a9-134">none</span></span>                                 |
| <span data-ttu-id="e95a9-135">Требуется?</span><span class="sxs-lookup"><span data-stu-id="e95a9-135">Required?</span></span>                            | <span data-ttu-id="e95a9-136">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-136">false</span></span>                                |
| <span data-ttu-id="e95a9-137">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="e95a9-137">Position?</span></span>                            | <span data-ttu-id="e95a9-138">1</span><span class="sxs-lookup"><span data-stu-id="e95a9-138">1</span></span>                                    |
| <span data-ttu-id="e95a9-139">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-139">Default Value</span></span>                        | <span data-ttu-id="e95a9-140">pswa</span><span class="sxs-lookup"><span data-stu-id="e95a9-140">pswa</span></span>                                 |
| <span data-ttu-id="e95a9-141">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="e95a9-141">Accept Pipeline Input?</span></span>               | <span data-ttu-id="e95a9-142">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-142">false</span></span>                                |
| <span data-ttu-id="e95a9-143">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="e95a9-143">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="e95a9-144">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-144">false</span></span>                                |

### <a name="-websitenameltstringgt"></a><span data-ttu-id="e95a9-145">-WebSiteName&lt;строка&gt;</span><span class="sxs-lookup"><span data-stu-id="e95a9-145">-WebSiteName&lt;String&gt;</span></span>

<span data-ttu-id="e95a9-146">Задает имя веб-сайта веб-сервера (IIS) для установки этого веб-приложения Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="e95a9-146">Specifies the name of the Web Server (IIS) website on which to install this Windows PowerShell Web Access web application.</span></span>

|||
|-|-|
| <span data-ttu-id="e95a9-147">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="e95a9-147">Aliases</span></span>                              | <span data-ttu-id="e95a9-148">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e95a9-148">none</span></span>                                 |
| <span data-ttu-id="e95a9-149">Требуется?</span><span class="sxs-lookup"><span data-stu-id="e95a9-149">Required?</span></span>                            | <span data-ttu-id="e95a9-150">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-150">false</span></span>                                |
| <span data-ttu-id="e95a9-151">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="e95a9-151">Position?</span></span>                            | <span data-ttu-id="e95a9-152">с именем</span><span class="sxs-lookup"><span data-stu-id="e95a9-152">named</span></span>                                |
| <span data-ttu-id="e95a9-153">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-153">Default Value</span></span>                        | <span data-ttu-id="e95a9-154">Веб-сайт по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-154">Default Web Site</span></span>                     |
| <span data-ttu-id="e95a9-155">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="e95a9-155">Accept Pipeline Input?</span></span>               | <span data-ttu-id="e95a9-156">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-156">false</span></span>                                |
| <span data-ttu-id="e95a9-157">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="e95a9-157">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="e95a9-158">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-158">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="e95a9-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e95a9-159">-Confirm</span></span>

<span data-ttu-id="e95a9-160">Запрос на подтверждение перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e95a9-160">Prompts you for confirmation before running the cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="e95a9-161">Требуется?</span><span class="sxs-lookup"><span data-stu-id="e95a9-161">Required?</span></span>                            | <span data-ttu-id="e95a9-162">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-162">false</span></span>                                |
| <span data-ttu-id="e95a9-163">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="e95a9-163">Position?</span></span>                            | <span data-ttu-id="e95a9-164">с именем</span><span class="sxs-lookup"><span data-stu-id="e95a9-164">named</span></span>                                |
| <span data-ttu-id="e95a9-165">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-165">Default Value</span></span>                        | <span data-ttu-id="e95a9-166">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-166">false</span></span>                                |
| <span data-ttu-id="e95a9-167">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="e95a9-167">Accept Pipeline Input?</span></span>               | <span data-ttu-id="e95a9-168">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-168">false</span></span>                                |
| <span data-ttu-id="e95a9-169">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="e95a9-169">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="e95a9-170">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-170">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="e95a9-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e95a9-171">-WhatIf</span></span>

<span data-ttu-id="e95a9-172">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e95a9-172">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e95a9-173">Командлет не запущен.</span><span class="sxs-lookup"><span data-stu-id="e95a9-173">The cmdlet is not run.</span></span>

|||
|-|-|
| <span data-ttu-id="e95a9-174">Требуется?</span><span class="sxs-lookup"><span data-stu-id="e95a9-174">Required?</span></span>                            | <span data-ttu-id="e95a9-175">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-175">false</span></span>                                |
| <span data-ttu-id="e95a9-176">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="e95a9-176">Position?</span></span>                            | <span data-ttu-id="e95a9-177">с именем</span><span class="sxs-lookup"><span data-stu-id="e95a9-177">named</span></span>                                |
| <span data-ttu-id="e95a9-178">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e95a9-178">Default Value</span></span>                        | <span data-ttu-id="e95a9-179">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-179">false</span></span>                                |
| <span data-ttu-id="e95a9-180">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="e95a9-180">Accept Pipeline Input?</span></span>               | <span data-ttu-id="e95a9-181">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-181">false</span></span>                                |
| <span data-ttu-id="e95a9-182">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="e95a9-182">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="e95a9-183">false</span><span class="sxs-lookup"><span data-stu-id="e95a9-183">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="e95a9-184">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="e95a9-184">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="e95a9-185">Данный командлет поддерживает общие параметры -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer и -OutVariable.</span><span class="sxs-lookup"><span data-stu-id="e95a9-185">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="e95a9-186">Дополнительные сведения см. в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e95a9-186">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="e95a9-187">ВХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="e95a9-187">INPUTS</span></span>

<span data-ttu-id="e95a9-188">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="e95a9-188">This cmdlet takes no input.</span></span>

## <a name="outputs"></a><span data-ttu-id="e95a9-189">ВЫХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="e95a9-189">OUTPUTS</span></span>

<span data-ttu-id="e95a9-190">Этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e95a9-190">This cmdlet produces no output.</span></span>

## <a name="examples"></a><span data-ttu-id="e95a9-191">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="e95a9-191">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="e95a9-192">ПРИМЕР 1</span><span class="sxs-lookup"><span data-stu-id="e95a9-192">EXAMPLE 1</span></span>

<span data-ttu-id="e95a9-193">В этом примере выполняется установка веб-приложения PSWA с использованием значений по умолчанию для параметров **WebApplicationName** (*pswa*) и **WebSiteName** (*веб-сайт по умолчанию*).</span><span class="sxs-lookup"><span data-stu-id="e95a9-193">This example installs the PSWA web application using the default values for the **WebApplicationName** (*pswa*) and **WebSiteName** (*Default Web Site*) parameters .</span></span>

```
Install-PswaWebApplication
```

### <a name="example-2"></a><span data-ttu-id="e95a9-194">ПРИМЕР 2</span><span class="sxs-lookup"><span data-stu-id="e95a9-194">EXAMPLE 2</span></span>

<span data-ttu-id="e95a9-195">В этом примере выполняется установка веб-приложения PSWA с тестовым сертификатом и со значениями по умолчанию для параметров **WebApplicationName** и **WebSiteName**.</span><span class="sxs-lookup"><span data-stu-id="e95a9-195">This example installs the PSWA web application with a test certificate, and using the default values for the **WebApplicationName** and **WebSiteName** parameters.</span></span>

```
Install-PswaWebApplication -UseTestCertificate
```

## <a name="related-topics"></a><span data-ttu-id="e95a9-196">Связанные темы</span><span class="sxs-lookup"><span data-stu-id="e95a9-196">Related topics</span></span>

- [<span data-ttu-id="e95a9-197">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="e95a9-197">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="e95a9-198">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="e95a9-198">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="e95a9-199">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="e95a9-199">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)
- [<span data-ttu-id="e95a9-200">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="e95a9-200">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)