---
title: Добавление поддержки учетных данных в функции PowerShell
description: Узнайте, как добавлять параметры учетных данных в скрипты, функции и командлеты PowerShell.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: 3e4a3f41ccbca1cf97f2e96fd60f22d89be7bc5a
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354632"
---
# <a name="add-credential-support-to-powershell-functions"></a><span data-ttu-id="185af-103">Добавление поддержки учетных данных в функции PowerShell</span><span class="sxs-lookup"><span data-stu-id="185af-103">Add Credential support to PowerShell functions</span></span>

> [!NOTE]
> <span data-ttu-id="185af-104">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@joshduffney][].</span><span class="sxs-lookup"><span data-stu-id="185af-104">The [original version][] of this article appeared on the blog written by [@joshduffney][].</span></span> <span data-ttu-id="185af-105">Эта статья была изменена для публикации на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="185af-105">This article has been edited for inclusion on this site.</span></span> <span data-ttu-id="185af-106">Группа разработчиков PowerShell благодарит Джоша (Josh) за то, что он поделился с нами этим содержимым.</span><span class="sxs-lookup"><span data-stu-id="185af-106">The PowerShell team thanks Josh for sharing this content with us.</span></span> <span data-ttu-id="185af-107">Посетите его блог [duffney.io][].</span><span class="sxs-lookup"><span data-stu-id="185af-107">Please check out his blog at [duffney.io][].</span></span>

<span data-ttu-id="185af-108">В этой статье показано, как и зачем добавлять параметры учетных данных в функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185af-108">This article shows you how to add credential parameters to PowerShell functions and why you'd want to.</span></span> <span data-ttu-id="185af-109">Параметр учетных данных позволяет выполнять функцию или командлет от лица другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="185af-109">A credential parameter is to allow you to run the function or cmdlet as a different user.</span></span> <span data-ttu-id="185af-110">Чаще всего такая возможность используется для выполнения функции или командлета от лица пользователя с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="185af-110">The most common use is to run the function or cmdlet as an elevated user account.</span></span>

<span data-ttu-id="185af-111">Например, командлет `New-ADUser` имеет параметр учетных данных **Credential** , в котором вы можете указать учетные данные администратора домена при создании учетной записи в домене,</span><span class="sxs-lookup"><span data-stu-id="185af-111">For example, the cmdlet `New-ADUser` has a **Credential** parameter, which you could provide domain admin credentials to create an account in a domain.</span></span> <span data-ttu-id="185af-112">если ваша обычная учетная запись с запущенным сеансом PowerShell не имеет таких прав.</span><span class="sxs-lookup"><span data-stu-id="185af-112">Assuming your normal account running the PowerShell session doesn't have that access already.</span></span>

## <a name="creating-credential-object"></a><span data-ttu-id="185af-113">Создание объекта учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-113">Creating credential object</span></span>

<span data-ttu-id="185af-114">Объект [PSCredential][] представляет набор учетных данных для безопасности, таких как имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="185af-114">The [PSCredential][] object represents a set of security credentials such as a user name and password.</span></span> <span data-ttu-id="185af-115">Объект можно передать в качестве параметра функции, которая выполняется от имени учетной записи пользователя в таком объекте учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-115">The object can be passed as a parameter to a function that runs as the user account in that credential object.</span></span> <span data-ttu-id="185af-116">Существует несколько способов создания объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-116">There are a few ways that you can create a credential object.</span></span> <span data-ttu-id="185af-117">Первый способ заключается в использовании командлета PowerShell `Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="185af-117">The first way to create a credential object is to use the PowerShell cmdlet `Get-Credential`.</span></span> <span data-ttu-id="185af-118">Если запустить его без параметров, отобразится запрос на ввод имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="185af-118">When you run without parameters, it prompts you for a username and password.</span></span> <span data-ttu-id="185af-119">Или же вы можете вызвать командлет с необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="185af-119">Or you can call the cmdlet with some optional parameters.</span></span>

<span data-ttu-id="185af-120">Чтобы предварительно указать имя домена и имя пользователя, вы можете использовать параметр **Credential** или **UserName**.</span><span class="sxs-lookup"><span data-stu-id="185af-120">To specify the domain name and username ahead of time you can use either the **Credential** or **UserName** parameters.</span></span> <span data-ttu-id="185af-121">Если используется параметр **UserName** , вам также необходимо указать значение **Message**.</span><span class="sxs-lookup"><span data-stu-id="185af-121">When you use the **UserName** parameter, you're also required to provide a **Message** value.</span></span> <span data-ttu-id="185af-122">В блоке кода ниже демонстрируется использование этого командлета.</span><span class="sxs-lookup"><span data-stu-id="185af-122">The code below demonstrates using the cmdlet.</span></span> <span data-ttu-id="185af-123">Вы также можете сохранить объект учетных данных в переменной для многократного использования учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-123">You can also store the credential object in a variable so that you can use the credential multiple times.</span></span> <span data-ttu-id="185af-124">В примере ниже объект учетных данных сохраняется в переменной `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="185af-124">In the example below, the credential object is stored in the variable `$Cred`.</span></span>

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

<span data-ttu-id="185af-125">В некоторых случая вы не сможете воспользоваться интерактивным методом для создания объектов учетных данных, который продемонстрирован в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="185af-125">Sometimes, you can't use the interactive method of creating credential objects shown in the previous example.</span></span> <span data-ttu-id="185af-126">Большинство средств автоматизации поддерживают только неинтерактивный метод.</span><span class="sxs-lookup"><span data-stu-id="185af-126">Most automation tools require a non-interactive method.</span></span> <span data-ttu-id="185af-127">Чтобы создать учетные данные без участия пользователя, сначала создайте защищенную строку с паролем.</span><span class="sxs-lookup"><span data-stu-id="185af-127">To create a credential without user interaction, create a secure string containing the password.</span></span> <span data-ttu-id="185af-128">Затем передайте защищенную строку и имя пользователя в метод `System.Management.Automation.PSCredential()`.</span><span class="sxs-lookup"><span data-stu-id="185af-128">Then pass the secure string and user name to the `System.Management.Automation.PSCredential()` method.</span></span>

<span data-ttu-id="185af-129">Используйте следующую команду, чтобы создать защищенную строку с паролем:</span><span class="sxs-lookup"><span data-stu-id="185af-129">Use the following command to create a secure string containing the password:</span></span>

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

<span data-ttu-id="185af-130">Параметры **AsPlainText** и **Force** являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="185af-130">Both the **AsPlainText** and **Force** parameters are required.</span></span> <span data-ttu-id="185af-131">Без этих параметров вы получите предупреждение о том, что вам не следует передавать обычный текст в защищенную строку.</span><span class="sxs-lookup"><span data-stu-id="185af-131">Without those parameters, you receive a message warning that you shouldn't pass plain text into a secure string.</span></span> <span data-ttu-id="185af-132">PowerShell возвращает это предупреждение, так как пароль в формате обычного текста будет записан в разные журналы.</span><span class="sxs-lookup"><span data-stu-id="185af-132">PowerShell returns this warning because the plain text password gets recorded in various logs.</span></span> <span data-ttu-id="185af-133">После создания защищенной строки вам нужно передать ее в метод `PSCredential()` для создания объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-133">Once you have a secure string created, you need to pass it to the `PSCredential()` method to create the credential object.</span></span> <span data-ttu-id="185af-134">В следующем примере переменная `$password` содержит защищенную строку `$Cred` с объектом учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-134">In the following example, the variable `$password` contains the secure string `$Cred` contains the credential object.</span></span>

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

<span data-ttu-id="185af-135">Теперь, когда вы знаете, как создать объект учетных данных, вы можете добавить параметры учетных данных в свои функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185af-135">Now that you know how to create credential objects, you can add credential parameters to your PowerShell functions.</span></span>

## <a name="adding-a-credential-parameter"></a><span data-ttu-id="185af-136">Добавление параметра учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-136">Adding a Credential Parameter</span></span>

<span data-ttu-id="185af-137">Как и с любым другим параметром, начните с его добавления в блок `param` своей функции.</span><span class="sxs-lookup"><span data-stu-id="185af-137">Just like any other parameter, you start off by adding it in the `param` block of your function.</span></span>
<span data-ttu-id="185af-138">Рекомендуется присвоить параметру имя `$Credential`, так как это имя используется существующими командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185af-138">It's recommended that you name the parameter `$Credential` because that's what existing PowerShell cmdlets use.</span></span> <span data-ttu-id="185af-139">Параметр должен иметь тип `[System.Management.Automation.PSCredential]`.</span><span class="sxs-lookup"><span data-stu-id="185af-139">The type of the parameter should be `[System.Management.Automation.PSCredential]`.</span></span>

<span data-ttu-id="185af-140">В следующем примере демонстрируется блок параметра для функции с именем `Get-Something`.</span><span class="sxs-lookup"><span data-stu-id="185af-140">The following example shows the parameter block for a function called `Get-Something`.</span></span> <span data-ttu-id="185af-141">Она имеет два параметра: `$Name` и `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="185af-141">It has two parameters: `$Name` and `$Credential`.</span></span>

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

<span data-ttu-id="185af-142">Кода в этом примере достаточно для создания работающего параметра учетных данных, но вы можете добавить несколько элементов, чтобы сделать его более надежным.</span><span class="sxs-lookup"><span data-stu-id="185af-142">The code in this example is enough to have a working credential parameter, however there are a few things you can add to make it more robust.</span></span>

- <span data-ttu-id="185af-143">Добавьте атрибут проверки `[ValidateNotNull()]`, чтобы проверить значение, передаваемое параметру **Credential**.</span><span class="sxs-lookup"><span data-stu-id="185af-143">Add the `[ValidateNotNull()]` validation attribute to check that the value being passed to **Credential**.</span></span> <span data-ttu-id="185af-144">Если параметр имеет значение NULL, этот атрибут предотвратит выполнение функции с недопустимыми учетными данными.</span><span class="sxs-lookup"><span data-stu-id="185af-144">If the parameter value is null, this attribute prevents the function from executing with invalid credentials.</span></span>

- <span data-ttu-id="185af-145">Добавьте `[System.Management.Automation.Credential()]`.</span><span class="sxs-lookup"><span data-stu-id="185af-145">Add `[System.Management.Automation.Credential()]`.</span></span> <span data-ttu-id="185af-146">Это позволяет передать имя пользователя в формате строки и запросить пароль через интерактивный ввод.</span><span class="sxs-lookup"><span data-stu-id="185af-146">This allows you to pass in a username as a string and have an interactive prompt for the password.</span></span>

- <span data-ttu-id="185af-147">Задайте для параметра `$Credential` значение по умолчанию `[System.Management.Automation.PSCredential]::Empty`.</span><span class="sxs-lookup"><span data-stu-id="185af-147">Set a default value for the `$Credential` parameter to `[System.Management.Automation.PSCredential]::Empty`.</span></span> <span data-ttu-id="185af-148">В вашей функции вы можете передать этот объект `$Credential` существующим командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185af-148">Your function you might be passing this `$Credential` object to existing PowerShell cmdlets.</span></span> <span data-ttu-id="185af-149">Указание значения NULL для командлета, вызываемого в вашей функции, приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="185af-149">Providing a null value to the cmdlet called inside your function causes an error.</span></span> <span data-ttu-id="185af-150">Указание пустого объекта учетных данных позволяет избежать этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="185af-150">Providing an empty credential object avoids this error.</span></span>

> [!TIP]
> <span data-ttu-id="185af-151">Некоторые командлеты, которые принимают параметр учетных данных, не поддерживают `[System.Management.Automation.PSCredential]::Empty`.</span><span class="sxs-lookup"><span data-stu-id="185af-151">Some cmdlets that accept a credential parameter do not support `[System.Management.Automation.PSCredential]::Empty` as they should.</span></span> <span data-ttu-id="185af-152">Временное решение см. в разделе [Работа с устаревшими командлетами](#dealing-with-legacy-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="185af-152">See the [Dealing with Legacy Cmdlets](#dealing-with-legacy-cmdlets) section for a workaround.</span></span>

## <a name="using-credential-parameters"></a><span data-ttu-id="185af-153">Использование параметров учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-153">Using credential parameters</span></span>

<span data-ttu-id="185af-154">В следующем примере кода показано, как использовать параметры учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-154">The following example demonstrates how to use credential parameters.</span></span> <span data-ttu-id="185af-155">В этом примере демонстрируется функция с именем `Set-RemoteRegistryValue`, которая приведена в книге [The Pester Book][].</span><span class="sxs-lookup"><span data-stu-id="185af-155">This example shows a function called `Set-RemoteRegistryValue`, which is out of [The Pester Book][].</span></span> <span data-ttu-id="185af-156">Эта функция определяет параметр учетных данных с помощью техник, описанных в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="185af-156">This function defines the credential parameter using the techniques describe in the previous section.</span></span> <span data-ttu-id="185af-157">Функция вызывает `Invoke-Command` с помощью переменной `$Credential`, создаваемой функцией.</span><span class="sxs-lookup"><span data-stu-id="185af-157">The function calls `Invoke-Command` using the `$Credential` variable created by the function.</span></span> <span data-ttu-id="185af-158">Это позволяет вам изменить пользователя, выполняющего `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="185af-158">This allows you to change the user who's running `Invoke-Command`.</span></span> <span data-ttu-id="185af-159">Так как для значения `$Credential` по умолчанию используются пустые учетные данные, функцию можно выполнять без предоставления учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-159">Because the default value of `$Credential` is an empty credential, the function can run without providing credentials.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

<span data-ttu-id="185af-160">В следующих разделах приведены различные методы по предоставлению учетных данных функции `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="185af-160">The following sections show different methods of providing credentials to `Set-RemoteRegistryValue`.</span></span>

### <a name="prompting-for-credentials"></a><span data-ttu-id="185af-161">Запрос учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-161">Prompting for credentials</span></span>

<span data-ttu-id="185af-162">Использование командлета `Get-Credential` в скобках `()` во время выполнения приводит к тому, что командлет `Get-credential` выполняется первым.</span><span class="sxs-lookup"><span data-stu-id="185af-162">Using `Get-Credential` in parentheses `()` at run time causes the `Get-credential` to run first.</span></span> <span data-ttu-id="185af-163">Появится запрос на ввод имени пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="185af-163">You are prompted for a username and password.</span></span> <span data-ttu-id="185af-164">Вы можете использовать параметр **Credential** или **UserName** командлета `Get-credential`, чтобы указать имя пользователя и домен.</span><span class="sxs-lookup"><span data-stu-id="185af-164">You could use the **Credential** or **UserName** parameters of `Get-credential` to pre-populate the username and domain.</span></span> <span data-ttu-id="185af-165">В следующем примере используется техника, называемая сплаттинг, для передачи параметров функции `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="185af-165">The following example uses a technique called splatting to pass parameters to the `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="185af-166">Дополнительные сведения о сплаттинге см. в [этой статье][].</span><span class="sxs-lookup"><span data-stu-id="185af-166">For more information about splatting, check out the [about_Splatting][] article.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Получение учетных данных во время выполнения](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

<span data-ttu-id="185af-168">Использование `(Get-Credential)` может сделать код громоздким.</span><span class="sxs-lookup"><span data-stu-id="185af-168">Using `(Get-Credential)` seems cumbersome.</span></span> <span data-ttu-id="185af-169">Обычно при использовании параметра **Credential** только с именем пользователя командлет автоматически запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="185af-169">Normally, when you use the **Credential** parameter with only a username, the cmdlet automatically prompts for the password.</span></span> <span data-ttu-id="185af-170">Такое поведение обеспечивается атрибутом `[System.Management.Automation.Credential()]`.</span><span class="sxs-lookup"><span data-stu-id="185af-170">The `[System.Management.Automation.Credential()]` attribute enables this behavior.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Запрос учетных данных](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> <span data-ttu-id="185af-172">При задании показанного значения реестра в этих примерах предполагается, что у вас установлены функции **веб-сервера** Windows.</span><span class="sxs-lookup"><span data-stu-id="185af-172">To set the registry value shown, these examples assume you have the **Web Server** features of Windows installed.</span></span> <span data-ttu-id="185af-173">Выполните `Install-WindowsFeature Web-Server` и `Install-WindowsFeature web-mgmt-tools` при необходимости.</span><span class="sxs-lookup"><span data-stu-id="185af-173">Run `Install-WindowsFeature Web-Server` and `Install-WindowsFeature web-mgmt-tools` if required.</span></span>

### <a name="provide-credentials-in-a-variable"></a><span data-ttu-id="185af-174">Указание учетных данных в переменной</span><span class="sxs-lookup"><span data-stu-id="185af-174">Provide credentials in a variable</span></span>

<span data-ttu-id="185af-175">Вы также можете предварительно указать переменную учетных данных и передать ее параметру **Credential** функции `Set-RemoteRegistryValue`.</span><span class="sxs-lookup"><span data-stu-id="185af-175">You can also populate a credential variable ahead of time and pass it to the **Credential** parameter of `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="185af-176">Используйте этот метод с инструментами непрерывной интеграции и непрерывного развертывания (CI/CD), такими как Jenkins, TeamCity и Octopus Deploy.</span><span class="sxs-lookup"><span data-stu-id="185af-176">Use this method with Continuous Integration / Continuous Deployment (CI/CD) tools such as Jenkins, TeamCity, and Octopus Deploy.</span></span> <span data-ttu-id="185af-177">Пример использования Jenkins можно найти в записи блога Hodge [Автоматизация с помощью Jenkins и PowerShell в Windows — часть 2][].</span><span class="sxs-lookup"><span data-stu-id="185af-177">For an example using Jenkins, check out Hodge's blog post [Automating with Jenkins and PowerShell on Windows - Part 2][].</span></span>

<span data-ttu-id="185af-178">В этом примере используется метод .NET для создания объекта учетных данных и защищенной строки для передачи в пароле.</span><span class="sxs-lookup"><span data-stu-id="185af-178">This example uses the .NET method to create the credential object and a secure string to pass in the password.</span></span>

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

<span data-ttu-id="185af-179">Для этого примера защищенная строка создается с использованием пароля в формате открытого текста.</span><span class="sxs-lookup"><span data-stu-id="185af-179">For this example, the secure string is created using a clear text password.</span></span> <span data-ttu-id="185af-180">Все упомянутые ранее инструменты CI/CD предоставляют защищенный метод для указания пароля во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="185af-180">All of the previously mentioned CI/CD have a secure method of providing that password at run time.</span></span> <span data-ttu-id="185af-181">При использовании таких инструментов замените пароль в формате обычного текста переменной, определенной в используемом инструменте CI/CD.</span><span class="sxs-lookup"><span data-stu-id="185af-181">When using those tools, replace the plain text password with the variable defined within the CI/CD tool you use.</span></span>

### <a name="run-without-credentials"></a><span data-ttu-id="185af-182">Выполнение без учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-182">Run without credentials</span></span>

<span data-ttu-id="185af-183">Так как по умолчанию переменная `$Credential` принимает значение пустого объекта учетных данных, вы можете выполнять команду без учетных данных, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="185af-183">Since `$Credential` defaults to an empty credential object, you can run the command without credentials, as shown in this example:</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a><span data-ttu-id="185af-184">Работа с устаревшими командлетами</span><span class="sxs-lookup"><span data-stu-id="185af-184">Dealing with legacy cmdlets</span></span>

<span data-ttu-id="185af-185">Не все командлеты поддерживают объекты учетных данных или позволяют использовать пустые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="185af-185">Not all cmdlets support credential objects or allow empty credentials.</span></span> <span data-ttu-id="185af-186">Для них требуется указать имя пользователя и пароль в формате строк.</span><span class="sxs-lookup"><span data-stu-id="185af-186">Instead, the cmdlet wants username and password parameters as strings.</span></span> <span data-ttu-id="185af-187">Существует несколько способов обойти такое ограничение.</span><span class="sxs-lookup"><span data-stu-id="185af-187">There are a few ways to work around this limitation.</span></span>

### <a name="using-if-else-to-handle-empty-credentials"></a><span data-ttu-id="185af-188">Использование оператора if-else для обработки пустых учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-188">Using if-else to handle empty credentials</span></span>

<span data-ttu-id="185af-189">В этом сценарии командлет, который вы хотите выполнить, не принимает пустой объект учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-189">In this scenario, the cmdlet you want to run doesn't accept an empty credential object.</span></span> <span data-ttu-id="185af-190">В этом примере параметр **Credential** добавляется к командлету `Invoke-Command`, только если он не пустой.</span><span class="sxs-lookup"><span data-stu-id="185af-190">This example adds the **Credential** parameter to `Invoke-Command` only if it's not empty.</span></span> <span data-ttu-id="185af-191">В противном случае командлет `Invoke-Command` выполняется без параметра **Credential**.</span><span class="sxs-lookup"><span data-stu-id="185af-191">Otherwise, it runs the `Invoke-Command` without the **Credential** parameter.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a><span data-ttu-id="185af-192">Использование сплаттинга для обработки пустых учетных данных</span><span class="sxs-lookup"><span data-stu-id="185af-192">Using splatting to handle empty credentials</span></span>

<span data-ttu-id="185af-193">В этом примере используется сплаттинг параметра для вызова устаревшего командлета.</span><span class="sxs-lookup"><span data-stu-id="185af-193">This example uses parameter splatting to call the legacy cmdlet.</span></span> <span data-ttu-id="185af-194">Объект `$Credential` добавляется условно в хэш-таблицу для сплаттинга и позволяет избежать повторения блока скрипта `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="185af-194">The `$Credential` object is conditionally added to the hash table for splatting and avoids the need to repeat the `Invoke-Command` script block.</span></span> <span data-ttu-id="185af-195">Подробные сведения о сплаттинге в функциях см. в записи блога [Сплаттинг параметров в расширенные функции][].</span><span class="sxs-lookup"><span data-stu-id="185af-195">To learn more about splatting inside functions, see the [Splatting Parameters Inside Advanced Functions][] blog post.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a><span data-ttu-id="185af-196">Работа со строковыми паролями</span><span class="sxs-lookup"><span data-stu-id="185af-196">Working with string passwords</span></span>

<span data-ttu-id="185af-197">Командлет `Invoke-Sqlcmd` является примером командлета, который принимает пароль в формате строки.</span><span class="sxs-lookup"><span data-stu-id="185af-197">The `Invoke-Sqlcmd` cmdlet is an example of a cmdlet that accepts a string as a password.</span></span>
<span data-ttu-id="185af-198">Командлет `Invoke-Sqlcmd` позволяет вам выполнять простые инструкции SQL для вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="185af-198">`Invoke-Sqlcmd` allows you to run simple SQL insert, update, and delete statements.</span></span> <span data-ttu-id="185af-199">Командлет `Invoke-Sqlcmd` требует указания имени пользователя и пароля в формате открытого текста, а не более защищенного объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-199">`Invoke-Sqlcmd` requires a clear-text username and password rather than a more secure credential object.</span></span> <span data-ttu-id="185af-200">В этом примере показано, как извлечь имя пользователя и пароль из объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="185af-200">This example shows how to extract the username and password from a credential object.</span></span>

<span data-ttu-id="185af-201">Функция `Get-AllSQLDatabases` в этом примере вызывает командлет `Invoke-Sqlcmd` для отправки серверу SQL запроса по всем его базам данных.</span><span class="sxs-lookup"><span data-stu-id="185af-201">The `Get-AllSQLDatabases` function in this example calls the `Invoke-Sqlcmd` cmdlet to query a SQL server for all its databases.</span></span> <span data-ttu-id="185af-202">Функция определяет параметр **Credential** с теми же атрибутами, которые были использованы в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="185af-202">The function defines a **Credential** parameter with the same attribute used in the previous examples.</span></span> <span data-ttu-id="185af-203">Так как имя пользователя и пароль существуют в переменной `$Credential`, вы можете извлечь эти значения для использования с командлетом `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="185af-203">Since the username and password exist within the `$Credential` variable, you can extract those values for use with `Invoke-Sqlcmd`.</span></span>

<span data-ttu-id="185af-204">Имя пользователя доступно из свойства **UserName** переменной `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="185af-204">The user name is available from the **UserName** property of the `$Credential` variable.</span></span> <span data-ttu-id="185af-205">Чтобы получить пароль, используйте метод `GetNetworkCredential()` объекта `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="185af-205">To obtain the password, you have to use the `GetNetworkCredential()` method of the `$Credential` object.</span></span> <span data-ttu-id="185af-206">Значения извлекаются в переменные, которые добавляются в хэш-таблицу, используемую для сплаттинга параметров в командлет `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="185af-206">The values are extracted into variables that are added to a hash table used for splatting parameters to `Invoke-Sqlcmd`.</span></span>

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a><span data-ttu-id="185af-207">Дополнительные сведения об управлении командлетами</span><span class="sxs-lookup"><span data-stu-id="185af-207">Continued learning credential management</span></span>

<span data-ttu-id="185af-208">Создание и хранение объектов учетных данных с соблюдением требований безопасности может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="185af-208">Creating and storing credential objects securely can be difficult.</span></span> <span data-ttu-id="185af-209">Приведенные ниже ресурсы помогут вам в работе с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="185af-209">The following resources can help you maintain PowerShell credentials.</span></span>

- <span data-ttu-id="185af-210">[BetterCredentials][]</span><span class="sxs-lookup"><span data-stu-id="185af-210">[BetterCredentials][]</span></span>
- <span data-ttu-id="185af-211">[Хранилище ключей Azure][]</span><span class="sxs-lookup"><span data-stu-id="185af-211">[Azure Key Vault][]</span></span>
- <span data-ttu-id="185af-212">[Проект Vault][]</span><span class="sxs-lookup"><span data-stu-id="185af-212">[Vault Project][]</span></span>
- <span data-ttu-id="185af-213">[Модуль SecretManagement][]</span><span class="sxs-lookup"><span data-stu-id="185af-213">[SecretManagement module][]</span></span>

<!-- link references -->
[Оригинал]: https://duffney.io/addcredentialstopowershellfunctions/
[original version]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Хранилище ключей Azure]: https://azure.microsoft.com/services/key-vault/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[Проект Vault]: https://www.vaultproject.io/
[Vault Project]: https://www.vaultproject.io/
[Сплаттинг параметров в расширенные функции]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Splatting Parameters Inside Advanced Functions]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Автоматизация с помощью Jenkins и PowerShell в Windows — часть 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Модуль SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
[SecretManagement module]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
