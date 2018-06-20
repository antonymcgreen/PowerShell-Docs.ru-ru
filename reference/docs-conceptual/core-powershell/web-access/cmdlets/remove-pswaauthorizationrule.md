---
ms.topic: reference
keywords: powershell,командлет
ms.date: 12/12/2016
title: Remove-PswaAuthorizationRule
ms.openlocfilehash: 6a3720bb9b8df3e1c6bb9f4a6196c9868b85b67d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189039"
---
# <a name="remove-pswaauthorizationrule"></a><span data-ttu-id="c87a0-103">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="c87a0-103">Remove-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="c87a0-104">КРАТКИЙ ОБЗОР</span><span class="sxs-lookup"><span data-stu-id="c87a0-104">SYNOPSIS</span></span>

<span data-ttu-id="c87a0-105">Удаляет указанное правило авторизации из Windows PowerShell® Web Access.</span><span class="sxs-lookup"><span data-stu-id="c87a0-105">Removes a specified authorization rule from Windows PowerShell® Web Access.</span></span>

## <a name="syntax"></a><span data-ttu-id="c87a0-106">СИНТАКСИС</span><span class="sxs-lookup"><span data-stu-id="c87a0-106">SYNTAX</span></span>

### <a name="id"></a><span data-ttu-id="c87a0-107">Id</span><span class="sxs-lookup"><span data-stu-id="c87a0-107">Id</span></span>
```
Remove-PswaAuthorizationRule [-Id] <Int32[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

### <a name="rule"></a><span data-ttu-id="c87a0-108">Правило</span><span class="sxs-lookup"><span data-stu-id="c87a0-108">Rule</span></span>
```
Remove-PswaAuthorizationRule [-Rule] <PswaAuthorizationRule[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="c87a0-109">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c87a0-109">DESCRIPTION</span></span>

<span data-ttu-id="c87a0-110">Удаляет указанное правило авторизации из Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="c87a0-110">Removes a specified authorization rule from Windows PowerShell Web Access.</span></span>

## <a name="parameters"></a><span data-ttu-id="c87a0-111">ПАРАМЕТРЫ</span><span class="sxs-lookup"><span data-stu-id="c87a0-111">PARAMETERS</span></span>

### <a name="-force"></a><span data-ttu-id="c87a0-112">-Force</span><span class="sxs-lookup"><span data-stu-id="c87a0-112">-Force</span></span>

<span data-ttu-id="c87a0-113">Запуск командлета без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="c87a0-113">Runs the cmdlet without prompting for confirmation.</span></span> <span data-ttu-id="c87a0-114">По умолчанию командлет запрашивает подтверждение, прежде чем продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="c87a0-114">By default the cmdlet asks for confirmation before proceeding.</span></span>

|||
|-|-|
| <span data-ttu-id="c87a0-115">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="c87a0-115">Aliases</span></span>                              | <span data-ttu-id="c87a0-116">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-116">none</span></span>                                 |
| <span data-ttu-id="c87a0-117">Требуется?</span><span class="sxs-lookup"><span data-stu-id="c87a0-117">Required?</span></span>                            | <span data-ttu-id="c87a0-118">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-118">false</span></span>                                |
| <span data-ttu-id="c87a0-119">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="c87a0-119">Position?</span></span>                            | <span data-ttu-id="c87a0-120">с именем</span><span class="sxs-lookup"><span data-stu-id="c87a0-120">named</span></span>                                |
| <span data-ttu-id="c87a0-121">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c87a0-121">Default Value</span></span>                        | <span data-ttu-id="c87a0-122">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-122">none</span></span>                                 |
| <span data-ttu-id="c87a0-123">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="c87a0-123">Accept Pipeline Input?</span></span>               | <span data-ttu-id="c87a0-124">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-124">false</span></span>                                |
| <span data-ttu-id="c87a0-125">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="c87a0-125">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="c87a0-126">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-126">false</span></span>                                |

### <a name="-id-ltint32gt"></a><span data-ttu-id="c87a0-127">-Id &lt;Int32\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="c87a0-127">-Id &lt;Int32\[\]&gt;</span></span>

<span data-ttu-id="c87a0-128">Указывает идентификаторы (ID) одного или нескольких удаляемых правил.</span><span class="sxs-lookup"><span data-stu-id="c87a0-128">Specifies the identifiers (IDs) of one or more rules to remove.</span></span>

|||
|-|-|
| <span data-ttu-id="c87a0-129">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="c87a0-129">Aliases</span></span>                              | <span data-ttu-id="c87a0-130">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-130">none</span></span>                                 |
| <span data-ttu-id="c87a0-131">Требуется?</span><span class="sxs-lookup"><span data-stu-id="c87a0-131">Required?</span></span>                            | <span data-ttu-id="c87a0-132">верно</span><span class="sxs-lookup"><span data-stu-id="c87a0-132">true</span></span>                                 |
| <span data-ttu-id="c87a0-133">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="c87a0-133">Position?</span></span>                            | <span data-ttu-id="c87a0-134">2</span><span class="sxs-lookup"><span data-stu-id="c87a0-134">2</span></span>                                    |
| <span data-ttu-id="c87a0-135">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c87a0-135">Default Value</span></span>                        | <span data-ttu-id="c87a0-136">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-136">none</span></span>                                 |
| <span data-ttu-id="c87a0-137">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="c87a0-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="c87a0-138">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="c87a0-138">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="c87a0-139">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="c87a0-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="c87a0-140">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-140">false</span></span>                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a><span data-ttu-id="c87a0-141">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="c87a0-141">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span></span>

<span data-ttu-id="c87a0-142">Указывает правила, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c87a0-142">Specifies the rules to remove.</span></span>

|||
|-|-|
| <span data-ttu-id="c87a0-143">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="c87a0-143">Aliases</span></span>                              | <span data-ttu-id="c87a0-144">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-144">none</span></span>                                 |
| <span data-ttu-id="c87a0-145">Требуется?</span><span class="sxs-lookup"><span data-stu-id="c87a0-145">Required?</span></span>                            | <span data-ttu-id="c87a0-146">верно</span><span class="sxs-lookup"><span data-stu-id="c87a0-146">true</span></span>                                 |
| <span data-ttu-id="c87a0-147">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="c87a0-147">Position?</span></span>                            | <span data-ttu-id="c87a0-148">2</span><span class="sxs-lookup"><span data-stu-id="c87a0-148">2</span></span>                                    |
| <span data-ttu-id="c87a0-149">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c87a0-149">Default Value</span></span>                        | <span data-ttu-id="c87a0-150">отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c87a0-150">none</span></span>                                 |
| <span data-ttu-id="c87a0-151">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="c87a0-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="c87a0-152">True (ByValue)</span><span class="sxs-lookup"><span data-stu-id="c87a0-152">True (ByValue)</span></span>                       |
| <span data-ttu-id="c87a0-153">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="c87a0-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="c87a0-154">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-154">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="c87a0-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c87a0-155">-Confirm</span></span>

<span data-ttu-id="c87a0-156">Запрос на подтверждение перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c87a0-156">Prompts you for confirmation before running the cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="c87a0-157">Требуется?</span><span class="sxs-lookup"><span data-stu-id="c87a0-157">Required?</span></span>                            | <span data-ttu-id="c87a0-158">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-158">false</span></span>                                |
| <span data-ttu-id="c87a0-159">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="c87a0-159">Position?</span></span>                            | <span data-ttu-id="c87a0-160">с именем</span><span class="sxs-lookup"><span data-stu-id="c87a0-160">named</span></span>                                |
| <span data-ttu-id="c87a0-161">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c87a0-161">Default Value</span></span>                        | <span data-ttu-id="c87a0-162">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-162">false</span></span>                                |
| <span data-ttu-id="c87a0-163">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="c87a0-163">Accept Pipeline Input?</span></span>               | <span data-ttu-id="c87a0-164">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-164">false</span></span>                                |
| <span data-ttu-id="c87a0-165">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="c87a0-165">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="c87a0-166">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-166">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="c87a0-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c87a0-167">-WhatIf</span></span>

<span data-ttu-id="c87a0-168">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c87a0-168">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c87a0-169">Командлет не запущен.</span><span class="sxs-lookup"><span data-stu-id="c87a0-169">The cmdlet is not run.</span></span>

|||
|-|-|
| <span data-ttu-id="c87a0-170">Требуется?</span><span class="sxs-lookup"><span data-stu-id="c87a0-170">Required?</span></span>                            | <span data-ttu-id="c87a0-171">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-171">false</span></span>                                |
| <span data-ttu-id="c87a0-172">Указать положение?</span><span class="sxs-lookup"><span data-stu-id="c87a0-172">Position?</span></span>                            | <span data-ttu-id="c87a0-173">с именем</span><span class="sxs-lookup"><span data-stu-id="c87a0-173">named</span></span>                                |
| <span data-ttu-id="c87a0-174">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c87a0-174">Default Value</span></span>                        | <span data-ttu-id="c87a0-175">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-175">false</span></span>                                |
| <span data-ttu-id="c87a0-176">Принимать входные данные конвейера?</span><span class="sxs-lookup"><span data-stu-id="c87a0-176">Accept Pipeline Input?</span></span>               | <span data-ttu-id="c87a0-177">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-177">false</span></span>                                |
| <span data-ttu-id="c87a0-178">Принимать подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="c87a0-178">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="c87a0-179">false</span><span class="sxs-lookup"><span data-stu-id="c87a0-179">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="c87a0-180">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="c87a0-180">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="c87a0-181">Данный командлет поддерживает общие параметры -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer и -OutVariable.</span><span class="sxs-lookup"><span data-stu-id="c87a0-181">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="c87a0-182">Дополнительные сведения см. в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c87a0-182">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="c87a0-183">ВХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="c87a0-183">INPUTS</span></span>

### <a name="int"></a><span data-ttu-id="c87a0-184">int\[\]</span><span class="sxs-lookup"><span data-stu-id="c87a0-184">int\[\]</span></span>

<span data-ttu-id="c87a0-185">Этот командлет принимает массив целых чисел или массив объектов PswaAuthorizationRule.</span><span class="sxs-lookup"><span data-stu-id="c87a0-185">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

### <a name="pswaauthorizationrule"></a><span data-ttu-id="c87a0-186">PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="c87a0-186">PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="c87a0-187">Этот командлет принимает массив целых чисел или массив объектов PswaAuthorizationRule.</span><span class="sxs-lookup"><span data-stu-id="c87a0-187">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="c87a0-188">ВЫХОДНЫЕ ДАННЫЕ</span><span class="sxs-lookup"><span data-stu-id="c87a0-188">OUTPUTS</span></span>

<span data-ttu-id="c87a0-189">Этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c87a0-189">This cmdlet produces no output.</span></span>

## <a name="examples"></a><span data-ttu-id="c87a0-190">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="c87a0-190">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="c87a0-191">ПРИМЕР 1</span><span class="sxs-lookup"><span data-stu-id="c87a0-191">EXAMPLE 1</span></span>

<span data-ttu-id="c87a0-192">Этот пример удаляет правило авторизации с идентификатором *2*.</span><span class="sxs-lookup"><span data-stu-id="c87a0-192">This example removes the authorization rule with an ID of *2*.</span></span>

```
Remove-PswaAuthorizationRule –Id 2
```

### <a name="example-2-example-2-subheading"></a><span data-ttu-id="c87a0-193">ПРИМЕР 2 {#example-2 .subHeading}</span><span class="sxs-lookup"><span data-stu-id="c87a0-193">EXAMPLE 2 {#example-2 .subHeading}</span></span>

<span data-ttu-id="c87a0-194">Этот пример удаляет все правила авторизации, а также требует подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="c87a0-194">This example removes all authorization rules and also requires confirmation by the user.</span></span>

```
Get-PswaAuthorizationRule | Remove-PswaAuthorizationRule -Confirm
```

## <a name="related-topics"></a><span data-ttu-id="c87a0-195">Связанные темы</span><span class="sxs-lookup"><span data-stu-id="c87a0-195">Related topics</span></span>

- [<span data-ttu-id="c87a0-196">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="c87a0-196">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="c87a0-197">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="c87a0-197">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="c87a0-198">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="c87a0-198">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="c87a0-199">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="c87a0-199">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)