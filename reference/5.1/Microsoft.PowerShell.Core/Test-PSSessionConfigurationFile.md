---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: b240a66304a2721b1bae67ed2cca669f564e8f66
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227022"
---
# <span data-ttu-id="21c3d-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21c3d-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="21c3d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="21c3d-104">SYNOPSIS</span></span>
<span data-ttu-id="21c3d-105">Проверяет ключи и значения в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="21c3d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21c3d-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="21c3d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21c3d-107">DESCRIPTION</span></span>

<span data-ttu-id="21c3d-108">Этот командлет проверяет, что файл конфигурации сеанса содержит допустимые ключи, а значения имеют правильный тип.</span><span class="sxs-lookup"><span data-stu-id="21c3d-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="21c3d-109">Для перечисляемых значений командлет проверяет правильность указанных значений.</span><span class="sxs-lookup"><span data-stu-id="21c3d-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="21c3d-110">Командлет возвращает значение, `$True` Если файл проходит все тесты, а `$False` Если нет.</span><span class="sxs-lookup"><span data-stu-id="21c3d-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="21c3d-111">Чтобы найти ошибки, используйте параметр **verbose** .</span><span class="sxs-lookup"><span data-stu-id="21c3d-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="21c3d-112">`Test-PSSessionConfigurationFile` проверяет файлы конфигурации сеанса, например созданные `New-PSSessionConfigurationFile` командлетом.</span><span class="sxs-lookup"><span data-stu-id="21c3d-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="21c3d-113">Сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="21c3d-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="21c3d-114">Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="21c3d-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="21c3d-115">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="21c3d-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="21c3d-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="21c3d-116">EXAMPLES</span></span>

### <span data-ttu-id="21c3d-117">Пример 1. Тестирование файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="21c3d-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="21c3d-118">Пример 2. Тестирование файла конфигурации сеанса конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="21c3d-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="21c3d-119">В этом примере мы протестируем файл конфигурации, используемый в конфигурации **ограниченного** сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="21c3d-120">Значение параметра **path** является результатом выполнения `Get-PSSessionConfiguration` команды, которая получает **ограниченную** конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="21c3d-121">Путь к файлу конфигурации сеанса хранится в значении свойства **конфигфилепас** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="21c3d-122">Пример 3. Тестирование файлов конфигурации всех сеансов</span><span class="sxs-lookup"><span data-stu-id="21c3d-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="21c3d-123">В этом примере функция проверяет все файлы конфигурации сеанса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="21c3d-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="21c3d-124">Функция использует `Get-PSSessionConfiguration` командлет для получения всех конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="21c3d-125">В коде внутри `ForEach-Object` цикла отображается путь к файлу и проверяется каждая из конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="21c3d-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="21c3d-126">Свойство **конфигфилепас** конфигурации сеанса содержит путь к файлу конфигурации сеанса, который используется в конфигурации сеанса, если таковой имеется.</span><span class="sxs-lookup"><span data-stu-id="21c3d-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="21c3d-127">Если значение свойства **ConfigFilePath** заполнено (значение true), команда получает (печатает) значение свойства **ConfigFilePath**.</span><span class="sxs-lookup"><span data-stu-id="21c3d-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="21c3d-128">Затем он использует `Test-PSSessionConfigurationFile` командлет для проверки файла в значении **конфигфилепас** .</span><span class="sxs-lookup"><span data-stu-id="21c3d-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="21c3d-129">Параметр **Verbose** возвращает ошибку файла, если файл не проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="21c3d-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="21c3d-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21c3d-130">PARAMETERS</span></span>

### <span data-ttu-id="21c3d-131">-Path</span><span class="sxs-lookup"><span data-stu-id="21c3d-131">-Path</span></span>

<span data-ttu-id="21c3d-132">Указывает путь и имя файла конфигурации сеанса (. pssc).</span><span class="sxs-lookup"><span data-stu-id="21c3d-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="21c3d-133">Если опустить путь, по умолчанию используется текущая папка.</span><span class="sxs-lookup"><span data-stu-id="21c3d-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="21c3d-134">Подстановочные знаки поддерживаются, но они должны разрешаться в один файл.</span><span class="sxs-lookup"><span data-stu-id="21c3d-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="21c3d-135">Путь к файлу конфигурации сеанса также можно передать в `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="21c3d-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="21c3d-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="21c3d-136">CommonParameters</span></span>

<span data-ttu-id="21c3d-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21c3d-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21c3d-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="21c3d-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21c3d-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="21c3d-139">INPUTS</span></span>

### <span data-ttu-id="21c3d-140">System.String</span><span class="sxs-lookup"><span data-stu-id="21c3d-140">System.String</span></span>

<span data-ttu-id="21c3d-141">Путь к файлу конфигурации сеанса можно передать в `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="21c3d-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="21c3d-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="21c3d-142">OUTPUTS</span></span>

### <span data-ttu-id="21c3d-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="21c3d-143">System.Boolean</span></span>

## <span data-ttu-id="21c3d-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="21c3d-144">NOTES</span></span>

## <span data-ttu-id="21c3d-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="21c3d-145">RELATED LINKS</span></span>

[<span data-ttu-id="21c3d-146">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-146">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-147">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-147">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-148">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-148">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-149">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21c3d-149">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="21c3d-150">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="21c3d-150">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="21c3d-151">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-151">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-152">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-152">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-153">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21c3d-153">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="21c3d-154">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21c3d-154">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="21c3d-155">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="21c3d-155">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="21c3d-156">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="21c3d-156">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="21c3d-157">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="21c3d-157">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)