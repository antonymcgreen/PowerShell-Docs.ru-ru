---
ms.date: 12/05/2019
keywords: powershell,командлет
title: Запуск Windows PowerShell
description: В этой статье описываются способы запуска различных версий PowerShell.
ms.openlocfilehash: 47da7d85c9f7e6966a7f7e809c77979cd24cf129
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664019"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="32731-104">Запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32731-104">Starting Windows PowerShell</span></span>

<span data-ttu-id="32731-105">Windows PowerShell — это обработчик скриптов `.DLL`, который внедрен в несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="32731-105">Windows PowerShell is a scripting engine `.DLL` that's embedded into multiple hosts.</span></span> <span data-ttu-id="32731-106">Самый распространенный запускаемый узел — интерактивная командная строка `powershell.exe` и интерактивная среда скриптов `powershell_ise.exe`.</span><span class="sxs-lookup"><span data-stu-id="32731-106">The most common hosts you'll start are the interactive command-line `powershell.exe` and the Interactive Scripting Environment `powershell_ise.exe`.</span></span>

<span data-ttu-id="32731-107">Информацию о запуске Windows PowerShell&reg; в Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012 и Windows 8 см. в статье [Общие задачи управления и навигации в Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="32731-107">To start Windows PowerShell&reg; on Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span></span>

## <a name="powershell-core-has-renamed-binary"></a><span data-ttu-id="32731-108">В PowerShell Core есть переименованный двоичный файл</span><span class="sxs-lookup"><span data-stu-id="32731-108">PowerShell Core has renamed binary</span></span>

<span data-ttu-id="32731-109">PowerShell Core, или PowerShell, имеет версию 6 и выше с открытым исходным кодом и использует .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32731-109">PowerShell Core, referred to as PowerShell, is version 6 and higher that's open source and uses .NET Core.</span></span> <span data-ttu-id="32731-110">Поддерживаемые версии доступны в Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="32731-110">Supported versions are available on Windows, macOS, and Linux.</span></span>

<span data-ttu-id="32731-111">Начиная с PowerShell 6 двоичный файл PowerShell был переименован в `pwsh.exe` для Windows и `pwsh` для macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="32731-111">Beginning in PowerShell 6, the PowerShell binary was renamed `pwsh.exe` for Windows and `pwsh` for macOS and Linux.</span></span> <span data-ttu-id="32731-112">Вы можете запустить предварительную версию PowerShell с помощью `pwsh-preview`.</span><span class="sxs-lookup"><span data-stu-id="32731-112">You can start PowerShell preview versions using `pwsh-preview`.</span></span> <span data-ttu-id="32731-113">Дополнительные сведения см. в разделе [Новые возможности в PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) и [Сведения о pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span><span class="sxs-lookup"><span data-stu-id="32731-113">For more information, see [What's New in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) and [About pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span></span>

<span data-ttu-id="32731-114">Чтобы найти справку по командлетам и документацию по установке для PowerShell 7, воспользуйтесь следующими ссылками:</span><span class="sxs-lookup"><span data-stu-id="32731-114">To find cmdlet reference and installation documentation for PowerShell 7, use the following links:</span></span>

| <span data-ttu-id="32731-115">Документ</span><span class="sxs-lookup"><span data-stu-id="32731-115">Document</span></span> | <span data-ttu-id="32731-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="32731-116">Link</span></span> |
| ----- | ----- |
| <span data-ttu-id="32731-117">Справка по командлетам</span><span class="sxs-lookup"><span data-stu-id="32731-117">Cmdlet reference</span></span> | [<span data-ttu-id="32731-118">Обозреватель модулей PowerShell</span><span class="sxs-lookup"><span data-stu-id="32731-118">PowerShell Module Browser</span></span>](/powershell/module/) |
| <span data-ttu-id="32731-119">Установка в Windows</span><span class="sxs-lookup"><span data-stu-id="32731-119">Windows installation</span></span> | [<span data-ttu-id="32731-120">Установка PowerShell Core в Windows</span><span class="sxs-lookup"><span data-stu-id="32731-120">Installing PowerShell Core on Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows) |
| <span data-ttu-id="32731-121">Установка в macOS</span><span class="sxs-lookup"><span data-stu-id="32731-121">macOS installation</span></span> | [<span data-ttu-id="32731-122">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="32731-122">Installing PowerShell Core on macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos) |
| <span data-ttu-id="32731-123">Установка в Linux</span><span class="sxs-lookup"><span data-stu-id="32731-123">Linux installation</span></span> | [<span data-ttu-id="32731-124">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="32731-124">Installing PowerShell Core on Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux) |

<span data-ttu-id="32731-125">Сведения о других версиях PowerShell см. в [документации по использованию PowerShell](../how-to-use-docs.md).</span><span class="sxs-lookup"><span data-stu-id="32731-125">To view content for other PowerShell versions, see [How to use the PowerShell documentation](../how-to-use-docs.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="32731-126">Запуск Windows PowerShell в более ранних версиях Windows</span><span class="sxs-lookup"><span data-stu-id="32731-126">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="32731-127">В этом разделе объясняется, как запустить Windows PowerShell и интегрированную среду скриптов Windows PowerShell (ISE) в Windows&reg; 7, Windows Server&reg; 2008 R2 и Windows Server&reg; 2008.</span><span class="sxs-lookup"><span data-stu-id="32731-127">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows&reg; 7, Windows Server&reg; 2008 R2, and Windows Server&reg; 2008.</span></span> <span data-ttu-id="32731-128">Кроме того, здесь поясняется, как включить дополнительный компонент Windows PowerShell ISE в Windows PowerShell 2.0 в ОС Windows Server&reg; 2008 R2 и Windows Server&reg; 2008.</span><span class="sxs-lookup"><span data-stu-id="32731-128">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server&reg; 2008 R2 and Windows Server&reg; 2008.</span></span>

<span data-ttu-id="32731-129">Используйте любой из следующих методов для запуска установленной версии Windows PowerShell 3.0 или Windows PowerShell 4.0, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="32731-129">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="32731-130">Из меню "Пуск"</span><span class="sxs-lookup"><span data-stu-id="32731-130">From the Start Menu</span></span>

- <span data-ttu-id="32731-131">Нажмите кнопку **Пуск** , введите **PowerShell** и выберите **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="32731-131">Click **Start** , type **PowerShell** , and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="32731-132">В меню **Пуск** выберите **Пуск** , **Все программы** , **Стандартные** , откройте папку **Windows PowerShell** и щелкните **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="32731-132">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="32731-133">В командной строке</span><span class="sxs-lookup"><span data-stu-id="32731-133">At the Command Prompt</span></span>

<span data-ttu-id="32731-134">В **cmd.exe** , Windows PowerShell или интегрированной среде сценариев Windows PowerShell для запуска Windows PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="32731-134">In **cmd.exe** , Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="32731-135">Можно также использовать параметры программы `powershell.exe` для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="32731-135">You can also use the parameters of the `powershell.exe` program to customize the session.</span></span> <span data-ttu-id="32731-136">Дополнительные сведения см. в статье [Справка по командной строке PowerShell.exe](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span><span class="sxs-lookup"><span data-stu-id="32731-136">For more information, see [PowerShell.exe Command-Line Help](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="32731-137">С правами администратора (Запуск от имени администратора)</span><span class="sxs-lookup"><span data-stu-id="32731-137">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="32731-138">Нажмите кнопку **Пуск** , введите **PowerShell** , щелкните правой кнопкой мыши **Windows PowerShell** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="32731-138">Click **Start** , type **PowerShell** , right-click **Windows PowerShell** , and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="32731-139">Запуск интегрированной среды сценариев Windows PowerShell в более ранних версиях Windows</span><span class="sxs-lookup"><span data-stu-id="32731-139">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="32731-140">Используйте один из следующих методов для запуска интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32731-140">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="32731-141">Из меню "Пуск"</span><span class="sxs-lookup"><span data-stu-id="32731-141">From the Start Menu</span></span>

- <span data-ttu-id="32731-142">Нажмите кнопку **Пуск** , введите **Интегрированная среда сценариев** и выберите **Интегрированная среда сценариев Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="32731-142">Click **Start** , type **ISE** , and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="32731-143">В меню **Пуск** выберите **Пуск** , **Все программы** , **Стандартные** , откройте папку **Windows PowerShell** и щелкните **Интегрированная среда сценариев Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="32731-143">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="32731-144">В командной строке</span><span class="sxs-lookup"><span data-stu-id="32731-144">At the Command Prompt</span></span>

<span data-ttu-id="32731-145">В `cmd.exe`, Windows PowerShell или интегрированной среде сценариев Windows PowerShell для запуска Windows PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="32731-145">In `cmd.exe`, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="32731-146">или</span><span class="sxs-lookup"><span data-stu-id="32731-146">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="32731-147">С правами администратора (Запуск от имени администратора)</span><span class="sxs-lookup"><span data-stu-id="32731-147">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="32731-148">Нажмите кнопку **Пуск** , введите **Интегрированная среда сценариев** , щелкните правой кнопкой мыши **Интегрированная среда сценариев Windows PowerShell** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="32731-148">Click **Start** , type **ISE** , right-click **Windows PowerShell ISE** , and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="32731-149">Включение интегрированной среды сценариев Windows PowerShell в более ранних версиях Windows</span><span class="sxs-lookup"><span data-stu-id="32731-149">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="32731-150">При использовании Windows PowerShell 4.0 и Windows PowerShell 3.0 интегрированная среда сценариев Windows PowerShell по умолчанию включена во всех версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="32731-150">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="32731-151">Если она еще не включена, Windows Management Framework 4.0 или Windows Management Framework 3.0 включает ее.</span><span class="sxs-lookup"><span data-stu-id="32731-151">If it isn't already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="32731-152">При использовании Windows PowerShell 2.0 интегрированная среда сценариев Windows PowerShell по умолчанию включена в Windows 7.</span><span class="sxs-lookup"><span data-stu-id="32731-152">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="32731-153">В Windows Server 2008 R2 и Windows Server 2008 эта функция является дополнительной.</span><span class="sxs-lookup"><span data-stu-id="32731-153">However, on Windows Server 2008 R2 and Windows Server 2008, it's an optional feature.</span></span>

<span data-ttu-id="32731-154">Чтобы включить интегрированную среду сценариев Windows PowerShell для Windows PowerShell 2.0 в Windows Server 2008 R2 или Windows Server 2008, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="32731-154">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="32731-155">Включение интегрированной среды сценариев Windows PowerShell Windows PowerShell (ISE)</span><span class="sxs-lookup"><span data-stu-id="32731-155">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="32731-156">Запустите диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="32731-156">Start Server Manager.</span></span>
2. <span data-ttu-id="32731-157">Щелкните **Компоненты** и выберите **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="32731-157">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="32731-158">В меню "Выберите компоненты" щелкните интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32731-158">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="32731-159">Запуск 32-разрядной версии Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32731-159">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="32731-160">При установке Windows PowerShell на 64-разрядном компьютере в дополнение к 64-разрядной версии устанавливается **Windows PowerShell (x86)** — 32-разрядная версия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32731-160">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)** , a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="32731-161">При открытии Windows PowerShell по умолчанию запускается 64-разрядная версия.</span><span class="sxs-lookup"><span data-stu-id="32731-161">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="32731-162">Однако в некоторых случаях нужно запустить **Windows PowerShell (x86)** , например при использовании модуля, которому требуется 32-разрядная версия, или при удаленном подключении к 32-разрядному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="32731-162">However, you might occasionally need to run **Windows PowerShell (x86)** , such as when you're using a module that requires the 32-bit version or when you're connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="32731-163">Для запуска 32-разрядной версии Windows PowerShell воспользуйтесь любой из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="32731-163">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-serverreg-2012-r2"></a><span data-ttu-id="32731-164">В Windows Server&reg; 2012 R2</span><span class="sxs-lookup"><span data-stu-id="32731-164">In Windows Server&reg; 2012 R2</span></span>

- <span data-ttu-id="32731-165">На экране **Пуск** щелкните **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-165">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="32731-166">Щелкните плитку **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="32731-166">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="32731-167">Выберите пункт **Windows PowerShell (x86)** в меню **Сервис\*\*\*\*диспетчера сервера**.</span><span class="sxs-lookup"><span data-stu-id="32731-167">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-168">На рабочем столе переместите курсор в правый верхний угол, щелкните элемент **Поиск** , введите **PowerShell x86** и выберите **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="32731-168">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-169">В командной строке введите следующее: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="32731-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-serverreg-2012"></a><span data-ttu-id="32731-170">В Windows Server&reg; 2012</span><span class="sxs-lookup"><span data-stu-id="32731-170">In Windows Server&reg; 2012</span></span>

- <span data-ttu-id="32731-171">На экране **Пуск** введите **PowerShell** и выберите **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-171">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-172">Выберите пункт **Windows PowerShell (x86)** в меню **Сервис\*\*\*\*диспетчера сервера**.</span><span class="sxs-lookup"><span data-stu-id="32731-172">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-173">На рабочем столе переместите курсор в правый верхний угол, щелкните элемент **Поиск** , введите **PowerShell** и выберите **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="32731-173">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-174">В командной строке введите следующее: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="32731-174">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-81"></a><span data-ttu-id="32731-175">В Windows&reg; 8.1</span><span class="sxs-lookup"><span data-stu-id="32731-175">In Windows&reg; 8.1</span></span>

- <span data-ttu-id="32731-176">На экране **Пуск** щелкните **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-176">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="32731-177">Щелкните плитку **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="32731-177">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="32731-178">Если вы используете [средства удаленного администрирования сервера](https://go.microsoft.com/fwlink/?LinkID=304145) для Windows 8.1, можно также открыть Windows PowerShell x86 из меню **Сервис** диспетчера сервера.</span><span class="sxs-lookup"><span data-stu-id="32731-178">If you're running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="32731-179">Выберите **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-179">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-180">На рабочем столе переместите курсор в правый верхний угол, щелкните элемент **Поиск** , введите **PowerShell x86** и выберите **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="32731-180">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-181">В командной строке введите следующее: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="32731-181">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-8"></a><span data-ttu-id="32731-182">В Windows&reg; 8</span><span class="sxs-lookup"><span data-stu-id="32731-182">In Windows&reg; 8</span></span>

- <span data-ttu-id="32731-183">На экране **Пуск** переместите курсор в правый верхний угол, щелкните **Параметры** , **Плитки** , а затем переместите ползунок **Показать средства администрирования** в значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="32731-183">On the **Start** screen, move the cursor to the upper right corner, click **Settings** , click **Tiles** , and then move the **Show Administrative Tools** slider to **Yes**.</span></span> <span data-ttu-id="32731-184">Введите **PowerShell** и выберите **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-184">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-185">Если вы используете [средства удаленного администрирования сервера](https://www.microsoft.com/download/details.aspx?id=28972) для Windows 8, можно также открыть Windows PowerShell x86 из меню **Сервис** диспетчера сервера.</span><span class="sxs-lookup"><span data-stu-id="32731-185">If you're running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="32731-186">Выберите **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-186">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-187">На экране **Пуск** или рабочем столе введите **PowerShell (x86)** и выберите **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="32731-187">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="32731-188">В командной строке введите следующее: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="32731-188">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
