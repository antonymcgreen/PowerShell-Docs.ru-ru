---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Использование подсистемы Windows PowerShell 2.0
ms.openlocfilehash: e00fb71c7fc32f5b48bc17ef5b25f910a846c893
ms.sourcegitcommit: 1748b2bdfae81d98097962c6c25c25df4bced1d8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "84262619"
---
# <a name="using-the-windows-powershell-20-engine"></a><span data-ttu-id="8b669-103">Использование подсистемы Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="8b669-103">Using the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="8b669-104">Windows PowerShell предназначена для обратной совместимости с предыдущими версиями оболочки.</span><span class="sxs-lookup"><span data-stu-id="8b669-104">Windows PowerShell is designed to be backward compatible with previous versions.</span></span> <span data-ttu-id="8b669-105">Командлеты, поставщики, оснастки, модули и сценарии, написанные для Windows PowerShell 2.0, выполняются в более новых версиях Windows PowerShell без изменений.</span><span class="sxs-lookup"><span data-stu-id="8b669-105">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in newer versions Windows PowerShell.</span></span> <span data-ttu-id="8b669-106">Однако в Microsoft .NET Framework 4 изменена политика активации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8b669-106">However, Microsoft .NET Framework 4 changed the runtime activation policy.</span></span>
<span data-ttu-id="8b669-107">Основные программы Windows PowerShell, написанные для Windows PowerShell 2.0 и скомпилированные с помощью CLR 2.0, не могут выполняться без изменения в новых версиях Windows PowerShell, скомпилированных с помощью CLR 4.0 (или более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="8b669-107">Windows PowerShell host programs written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in new versions Windows PowerShell that are compiled with CLR 4.0 (or higher).</span></span>

<span data-ttu-id="8b669-108">Подсистема Windows PowerShell 2.0 предназначена для использования только в том случае, если выполнение существующего сценария или существующей основной программы невозможно из-за несовместимости с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="8b669-108">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 5.1.</span></span> <span data-ttu-id="8b669-109">Примерами являются более старые версии модулей Exchange или SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b669-109">Examples of this include older versions of Exchange or SQL Server modules.</span></span> <span data-ttu-id="8b669-110">Такие ситуации довольно редки.</span><span class="sxs-lookup"><span data-stu-id="8b669-110">Such cases are expected to be rare.</span></span>

<span data-ttu-id="8b669-111">Многие программы, требующие использования подсистемы Windows PowerShell 2.0, запускают ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="8b669-111">Many programs that require the Windows PowerShell 2.0 Engine start it automatically.</span></span> <span data-ttu-id="8b669-112">Эти инструкции предназначены для редких случаев, когда подсистему необходимо запустить вручную.</span><span class="sxs-lookup"><span data-stu-id="8b669-112">These instructions are included for the rare situations in which you need to start the engine manually.</span></span>

## <a name="deprecation-and-security-concerns"></a><span data-ttu-id="8b669-113">Прекращение поддержки и соображения безопасности</span><span class="sxs-lookup"><span data-stu-id="8b669-113">Deprecation and security concerns</span></span>

<span data-ttu-id="8b669-114">Поддержка Windows PowerShell 2.0 была прекращена в августе 2017 г.</span><span class="sxs-lookup"><span data-stu-id="8b669-114">Windows PowerShell 2.0 was deprecated in August, 2017.</span></span> <span data-ttu-id="8b669-115">Дополнительные сведения см. в [объявлении][] в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b669-115">For more information, see the [announcement][] on the PowerShell blog.</span></span>

<span data-ttu-id="8b669-116">В Windows PowerShell 2.0 отсутствует целый ряд функций усиления защиты и обеспечения безопасности, добавленных в версии 3, 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="8b669-116">Windows PowerShell 2.0 is missing a significant amount of the hardening and security features added in versions 3, 4, and 5.</span></span> <span data-ttu-id="8b669-117">Настоятельно рекомендуется не использовать эту версию продукта.</span><span class="sxs-lookup"><span data-stu-id="8b669-117">We highly, highly recommend that users not use it if they can help it.</span></span> <span data-ttu-id="8b669-118">Дополнительные сведения см. [A Comparison of Shell and Scripting Language Security][] и в [этой записи блога][blueteam].</span><span class="sxs-lookup"><span data-stu-id="8b669-118">For more information, see [A Comparison of Shell and Scripting Language Security][] and [PowerShell ♥ the Blue Team][blueteam].</span></span>

## <a name="installing-and-enabling-required-programs"></a><span data-ttu-id="8b669-119">Установка и включение требуемых программ</span><span class="sxs-lookup"><span data-stu-id="8b669-119">Installing and Enabling Required Programs</span></span>

<span data-ttu-id="8b669-120">Перед запуском подсистемы Windows PowerShell 2.0 включите подсистему Windows PowerShell 2.0 и Microsoft .NET Framework 3.5 с пакетом обновления 1.</span><span class="sxs-lookup"><span data-stu-id="8b669-120">Before starting the Windows PowerShell 2.0 Engine, enable the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 with Service Pack 1.</span></span> <span data-ttu-id="8b669-121">Инструкции см. в статье [Установка Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="8b669-121">For instructions, see [Installing Windows PowerShell][].</span></span>

<span data-ttu-id="8b669-122">Системы, где установлена Windows Management Framework 3.0 или более поздние версии, имеют все необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="8b669-122">Systems on which Windows Management Framework 3.0 or higher is installed have all of the required components.</span></span> <span data-ttu-id="8b669-123">Никакая дополнительная настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="8b669-123">No further configuration is necessary.</span></span> <span data-ttu-id="8b669-124">Дополнительные сведения об установке Windows Management Framework см. в статье [Установка и настройка WMF][].</span><span class="sxs-lookup"><span data-stu-id="8b669-124">For information about installing Windows Management Framework, see [Install and configure WMF][].</span></span>

## <a name="how-to-start-the-windows-powershell-20-engine"></a><span data-ttu-id="8b669-125">Запуск подсистемы Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="8b669-125">How to start the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="8b669-126">При запуске Windows PowerShell по умолчанию открывается самая новая версия.</span><span class="sxs-lookup"><span data-stu-id="8b669-126">When you start Windows PowerShell the newest version starts by default.</span></span> <span data-ttu-id="8b669-127">Для запуска Windows PowerShell с подсистемой Windows PowerShell 2.0 используйте параметр Version в `PowerShell.exe`.</span><span class="sxs-lookup"><span data-stu-id="8b669-127">To start Windows PowerShell with the Windows PowerShell 2.0 Engine, use the Version parameter of `PowerShell.exe`.</span></span> <span data-ttu-id="8b669-128">Команду можно выполнить в любой командной строке, включая Windows PowerShell и Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="8b669-128">You can run the command at any command prompt, including Windows PowerShell and Cmd.exe.</span></span>

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a><span data-ttu-id="8b669-129">Запуск удаленного сеанса с помощью подсистемы Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="8b669-129">How to start a remote session with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="8b669-130">Чтобы запустить подсистему Windows PowerShell 2.0 в удаленном сеансе, создайте конфигурацию сеанса (которая также называется _конечной точкой_) на удаленном компьютере, которая загружает подсистему Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="8b669-130">To run the Windows PowerShell 2.0 Engine in a remote session, create a session configuration (also known as an _endpoint_) on the remote computer that loads the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="8b669-131">Конфигурация сеанса сохраняется на удаленном компьютере; любой авторизованный пользователь может использовать ее для создания сеансов на основе Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="8b669-131">The session configuration is saved on the remote computer and can be used by any authorized user to create sessions that use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="8b669-132">Это сложная задача, которая обычно выполняется системным администратором.</span><span class="sxs-lookup"><span data-stu-id="8b669-132">This is an advanced task that is typically performed by a system administrator.</span></span>

<span data-ttu-id="8b669-133">Следующая процедура использует параметр **PSVersion** командлета [Register-PSSessionConfiguration][] для создания конфигурации сеанса с подсистемой Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="8b669-133">The following procedure uses the **PSVersion** parameter of the [Register-PSSessionConfiguration][] cmdlet to create a session configuration that uses the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="8b669-134">Можно также использовать параметр **PowerShellVersion** командлета [New-PSSessionConfigurationFile][], чтобы создать файл конфигурации для сеанса, который загружает подсистему Windows PowerShell 2.0, и параметр **PSVersion** командлета [Set-PSSessionConfiguration][], чтобы изменить конфигурацию сеанса для использования подсистемы Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="8b669-134">You can also use the **PowerShellVersion** parameter of the [New-PSSessionConfigurationFile][] cmdlet to create a session configuration file for a session that loads the Windows PowerShell 2.0 Engine and you can use the **PSVersion** parameter of the [Set-PSSessionConfiguration][] parameter to change a session configuration to use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="8b669-135">Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files][].</span><span class="sxs-lookup"><span data-stu-id="8b669-135">For more information about session configuration files, see [about_Session_Configuration_Files][].</span></span>
<span data-ttu-id="8b669-136">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations][].</span><span class="sxs-lookup"><span data-stu-id="8b669-136">For information about session configurations, including setup and security, see [about_Session_Configurations][].</span></span>

### <a name="to-start-a-remote-windows-powershell-20-session"></a><span data-ttu-id="8b669-137">Запуск удаленного сеанса Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="8b669-137">To start a remote Windows PowerShell 2.0 session</span></span>

1. <span data-ttu-id="8b669-138">Для создания конфигурации сеанса, требующей подсистемы Windows PowerShell 2.0, используйте параметр **PSVersion** командлета `Register-PSSessionConfiguration` со значением `2.0`.</span><span class="sxs-lookup"><span data-stu-id="8b669-138">To create a session configuration that requires the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet with a value of `2.0`.</span></span>
   <span data-ttu-id="8b669-139">Выполните команду на компьютере на "стороне сервера" или на принимающей стороне подключения.</span><span class="sxs-lookup"><span data-stu-id="8b669-139">Run this command on the computer at the "server side" or receiving end of the connection.</span></span>

   <span data-ttu-id="8b669-140">Следующий пример команды создает конфигурацию сеанса PS2 на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="8b669-140">The following sample command creates the PS2 session configuration on the Server01 computer.</span></span> <span data-ttu-id="8b669-141">Чтобы выполнить эту команду, запустите Windows PowerShell с параметром **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8b669-141">To run this command, start Windows PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. <span data-ttu-id="8b669-142">Чтобы создать на компьютере Server01 сеанс, использующий конфигурацию сеанса PS2, примените параметр **ConfigurationName** для командлетов, создающих удаленный сеанс, таких как New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="8b669-142">To create a session on the Server01 computer that uses the PS2 session configuration, use the **ConfigurationName** parameter of cmdlets that create a remote session, such as the \`New-PSSession cmdlet.</span></span>

   <span data-ttu-id="8b669-143">При запуске сеанса, использующего конфигурацию, подсистема Windows PowerShell 2.0 автоматически загружается в него.</span><span class="sxs-lookup"><span data-stu-id="8b669-143">When a session that uses the session configuration starts, the Windows PowerShell 2.0 Engine is automatically loaded into the session.</span></span>

   <span data-ttu-id="8b669-144">Следующая команда запускает сеанс на компьютере Server01, который использует конфигурацию PS2.</span><span class="sxs-lookup"><span data-stu-id="8b669-144">The following command starts a session on the Server01 computer that uses the PS2 session configuration.</span></span> <span data-ttu-id="8b669-145">Сеанс сохраняется в переменную `$s`.</span><span class="sxs-lookup"><span data-stu-id="8b669-145">The command saves the session in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a><span data-ttu-id="8b669-146">Запуск фонового задания с помощью подсистемы Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="8b669-146">How to start a background job with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="8b669-147">Чтобы запустить фоновое задание с помощью подсистемы Windows PowerShell 2.0, используйте параметр **PSVersion** командлета [Start-Job][].</span><span class="sxs-lookup"><span data-stu-id="8b669-147">To start a background job with the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the [Start-Job][] cmdlet.</span></span>

<span data-ttu-id="8b669-148">Следующая команда запускает фоновое задание с помощью подсистемы Windows PowerShell 2.0:</span><span class="sxs-lookup"><span data-stu-id="8b669-148">The following command starts a background job with the Windows PowerShell 2.0 Engine</span></span>

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

<span data-ttu-id="8b669-149">Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs][].</span><span class="sxs-lookup"><span data-stu-id="8b669-149">For more information about background jobs, see [about_Jobs][].</span></span>

<!-- link references -->
[объявлении]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[announcement]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/ (Сравнение безопасности оболочки и языка сценариев)
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Установка Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Installing Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Установка и настройка WMF]: wmf/setup/install-configure.md
[Install and configure WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfiguration
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
