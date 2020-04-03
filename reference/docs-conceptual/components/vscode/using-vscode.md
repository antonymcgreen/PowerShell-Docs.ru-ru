---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 8644aa7c648d649651ca679238e0b79ff35ac579
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500913"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="50ccb-103">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ccb-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="50ccb-104">[Visual Studio Code](https://code.visualstudio.com/) — это кросс-платформенный редактор сценариев (Windows, macOS и Linux), созданный корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50ccb-104">[Visual Studio Code](https://code.visualstudio.com/) is a cross-platform (Windows, macOS, and Linux) script editor by Microsoft.</span></span> <span data-ttu-id="50ccb-105">Наряду с [расширением PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell) он предоставляет широкие интерактивные возможности редактирования сценариев, упрощая написание надежных сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-105">Together with the [the PowerShell extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span>

<span data-ttu-id="50ccb-106">Редактор Visual Studio Code с расширением PowerShell рекомендуется использовать для написания сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>
<span data-ttu-id="50ccb-107">Он поддерживает следующие версии PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50ccb-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="50ccb-108">PowerShell 7 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="50ccb-108">PowerShell 7 and up</span></span>
- <span data-ttu-id="50ccb-109">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="50ccb-109">PowerShell Core 6</span></span>
- <span data-ttu-id="50ccb-110">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="50ccb-110">Windows PowerShell 5.1</span></span>

<span data-ttu-id="50ccb-111">Перед запуском убедитесь, что оболочка PowerShell установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="50ccb-111">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="50ccb-112">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="50ccb-112">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="50ccb-113">[Установка PowerShell в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="50ccb-113">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="50ccb-114">[Установка PowerShell в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="50ccb-114">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="50ccb-115">[Установка PowerShell в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="50ccb-115">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="50ccb-116">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="50ccb-116">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!NOTE]
> <span data-ttu-id="50ccb-117">Visual Studio Code отличается от [Visual Studio](https://visualstudio.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="50ccb-117">Visual Studio Code is not the same as [Visual Studio](https://visualstudio.microsoft.com/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50ccb-118">[Windows PowerShell ISE][ise] также доступна для Windows, но ее возможности больше не в активной разработке и она не работает с PowerShell 7 и Windows PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="50ccb-118">The [Windows PowerShell ISE][ise] is also still available for Windows, however, it is no longer in active feature development and does not work with PowerShell 7 and up or PowerShell Core 6.</span></span>
> <span data-ttu-id="50ccb-119">Как компонент доставки Windows эта среда по-прежнему официально поддерживается для внесения наиболее важных исправлений, связанных с безопасностью и обслуживанием.</span><span class="sxs-lookup"><span data-stu-id="50ccb-119">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span> <span data-ttu-id="50ccb-120">Пока что мы не планируем удалять ISE из Windows.</span><span class="sxs-lookup"><span data-stu-id="50ccb-120">We currently have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="50ccb-121">Редактирование с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50ccb-121">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="50ccb-122">Установите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="50ccb-122">Install Visual Studio Code.</span></span> <span data-ttu-id="50ccb-123">Дополнительные сведения см. в статье [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview) (Настройка Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="50ccb-123">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

    <span data-ttu-id="50ccb-124">Доступны инструкции по установке на каждой платформе:</span><span class="sxs-lookup"><span data-stu-id="50ccb-124">There are installation instructions for each platform:</span></span>

    - <span data-ttu-id="50ccb-125">**Windows**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="50ccb-125">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>
    - <span data-ttu-id="50ccb-126">**macOS**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="50ccb-126">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>
    - <span data-ttu-id="50ccb-127">**Linux**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="50ccb-127">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>

1. <span data-ttu-id="50ccb-128">Установите расширение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-128">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="50ccb-129">Запустите приложение Visual Studio Code, введя `code` в консоли или `code-insiders`, если вы установили Visual Studio Code Insiders.</span><span class="sxs-lookup"><span data-stu-id="50ccb-129">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="50ccb-130">Запустите **Quick Open** в Windows или Linux, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50ccb-130">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="50ccb-131">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50ccb-131">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="50ccb-132">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-132">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="50ccb-133">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-133">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="50ccb-134">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50ccb-134">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="50ccb-135">Откроется примерно следующий экран Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="50ccb-135">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. <span data-ttu-id="50ccb-137">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50ccb-137">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="50ccb-138">После установки кнопка **Установить** изменяется на **Reload** (Перезагрузить). Нажмите кнопку **Reload** (Перезагрузить).</span><span class="sxs-lookup"><span data-stu-id="50ccb-138">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="50ccb-139">После перезагрузки Visual Studio Code можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="50ccb-139">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="50ccb-140">Например, чтобы создать файл, выберите **Файл > Создать**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="50ccb-141">Чтобы сохранить его, выберите **Файл > Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="50ccb-142">Чтобы закрыть файл, щелкните `X` рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="50ccb-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="50ccb-143">Чтобы завершить работу с Visual Studio Code, выберите элементы **Файл > Выйти**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-143">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="50ccb-144">Установка расширения PowerShell в системах с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="50ccb-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="50ccb-145">Некоторые системы настроены таким образом, что требуется проверка всех подписей кода и, следовательно, одобрение службы редактора PowerShell вручную для запуска в системе.</span><span class="sxs-lookup"><span data-stu-id="50ccb-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="50ccb-146">Обновление групповой политики, которое изменяет политику выполнения, является вероятной причиной того, что после установки расширения PowerShell вы сталкиваетесь со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="50ccb-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="50ccb-147">Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для Visual Studio Code, откройте командную строку PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="50ccb-147">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="50ccb-148">Вы увидите подсказку **Не удается проверить издателя. Вы действительно хотите запустить эту программу?**</span><span class="sxs-lookup"><span data-stu-id="50ccb-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span>
<span data-ttu-id="50ccb-149">Введите `A` для запуска файла.</span><span class="sxs-lookup"><span data-stu-id="50ccb-149">Type `A` to run the file.</span></span> <span data-ttu-id="50ccb-150">Затем откройте Visual Studio Code и убедитесь, что расширение PowerShell работает правильно.</span><span class="sxs-lookup"><span data-stu-id="50ccb-150">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="50ccb-151">Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="50ccb-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="50ccb-152">Расширение PowerShell для Visual Studio Code не поддерживает запуск в ограниченном языковом режиме.</span><span class="sxs-lookup"><span data-stu-id="50ccb-152">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="50ccb-153">Дополнительные сведения см. в разделе GitHub о [поддерживаемом отслеживании проблем](https://github.com/PowerShell/vscode-powershell/issues/606).</span><span class="sxs-lookup"><span data-stu-id="50ccb-153">Please see the [GitHub issue tracking that support](https://github.com/PowerShell/vscode-powershell/issues/606) for more information.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="50ccb-154">Использование более ранней версии расширения PowerShell для Windows PowerShell версий 3 и 4</span><span class="sxs-lookup"><span data-stu-id="50ccb-154">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="50ccb-155">Хотя текущее расширение PowerShell [не поддерживают версии 3 и 4](https://github.com/PowerShell/vscode-powershell/issues/1310), вы по-прежнему можете использовать последнюю версию расширения, которую они поддерживают.</span><span class="sxs-lookup"><span data-stu-id="50ccb-155">Although the current PowerShell extension [stopped supporting v3 and v4](https://github.com/PowerShell/vscode-powershell/issues/1310), you can still use the last version of the extension that did.</span></span>

> [!NOTE]
> <span data-ttu-id="50ccb-156">Дополнительные исправления для этой старой версии расширения не будут внесены.</span><span class="sxs-lookup"><span data-stu-id="50ccb-156">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="50ccb-157">Она предоставляется без изменений, но доступна для вас, если вы все еще используете Windows PowerShell версии 3 или 4.</span><span class="sxs-lookup"><span data-stu-id="50ccb-157">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="50ccb-158">Сначала откройте панель расширений и найдите `PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-158">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="50ccb-159">Затем щелкните значок шестеренки и выберите команду **Install another version...** (Установить другую версию...).</span><span class="sxs-lookup"><span data-stu-id="50ccb-159">Then click the gear and select **Install another version...**.</span></span>

![Install another version... (Установить другую версию...)](media/using-vscode/install-another-version.png)

<span data-ttu-id="50ccb-161">Затем выберите версию **`2020.1.0`** .</span><span class="sxs-lookup"><span data-stu-id="50ccb-161">Then select the **`2020.1.0`** version.</span></span> <span data-ttu-id="50ccb-162">Эта версия расширения — последняя версия, которую поддерживает Windows PowerShell версий 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="50ccb-162">This version of the extension was the last version to support v3 and v4.</span></span>

<span data-ttu-id="50ccb-163">Кроме того, добавьте следующий параметр, чтобы версия расширения не обновлялась автоматически:</span><span class="sxs-lookup"><span data-stu-id="50ccb-163">Also, add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="50ccb-164">В ближайшем будущем в Visual Studio Code может появиться изменение, которое прервет поддержку этой версии расширения.</span><span class="sxs-lookup"><span data-stu-id="50ccb-164">Although this will work in the forseeable future, Visual Studio Code could implement a change that breaks this version of the extension.</span></span>
<span data-ttu-id="50ccb-165">В связи с этим и отсутствием поддержки мы настоятельно рекомендуем:</span><span class="sxs-lookup"><span data-stu-id="50ccb-165">Because of this, and lack of support, we highly recommend either:</span></span>

- <span data-ttu-id="50ccb-166">скачать PowerShell 7, которая доступна для параллельной установки с другими версиями Windows PowerShell и наилучшим образом подходит для расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-166">Downloading PowerShell 7 - which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>
- <span data-ttu-id="50ccb-167">выполнить обновление до Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="50ccb-167">Upgrading to Windows PowerShell 5.1</span></span>

<span data-ttu-id="50ccb-168">Подробные сведения о месте установки см. в разделе [Редактирование с помощью Visual Studio Code](#editing-with-visual-studio-code) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="50ccb-168">The [Editing with Visual Studio Code](#editing-with-visual-studio-code) section in this article links to where to install these.</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="50ccb-169">Выбор версии PowerShell для использования с расширением</span><span class="sxs-lookup"><span data-stu-id="50ccb-169">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="50ccb-170">Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать конкретную версию PowerShell с расширением PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-170">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="50ccb-171">Выберите версию, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="50ccb-171">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="50ccb-172">Откройте **палитру команд** в Windows и Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>).</span><span class="sxs-lookup"><span data-stu-id="50ccb-172">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="50ccb-173">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50ccb-173">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="50ccb-174">Выполните поиск по слову **Сеанс**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-174">Search for **Session**.</span></span>
1. <span data-ttu-id="50ccb-175">Щелкните **PowerShell: Show Session Menu** (PowerShell: показать меню сеансов).</span><span class="sxs-lookup"><span data-stu-id="50ccb-175">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="50ccb-176">Выберите версию PowerShell, которую хотите использовать, из списка, например **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-176">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50ccb-177">Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти расположения установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-177">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="50ccb-178">Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="50ccb-178">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="50ccb-179">Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="50ccb-179">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="50ccb-180">Есть еще один способ перехода в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="50ccb-180">There's another way to get to the session menu.</span></span> <span data-ttu-id="50ccb-181">В правом нижнем углу открытого файла PowerShell в редакторе виден зеленый номер версии.</span><span class="sxs-lookup"><span data-stu-id="50ccb-181">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="50ccb-182">Щелкнув его, вы перейдете в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="50ccb-182">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="50ccb-183">Добавление собственных путей PowerShell в меню сеансов</span><span class="sxs-lookup"><span data-stu-id="50ccb-183">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="50ccb-184">В меню сеанса можно добавить другие пути к исполнимому файлу PowerShell с помощью [параметра Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-184">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="50ccb-185">Добавьте элемент в список `powershell.powerShellAdditionalExePaths` или создайте список, если его нет в `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="50ccb-185">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

<span data-ttu-id="50ccb-186">Каждый элемент должен иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="50ccb-186">Each item must have:</span></span>

- <span data-ttu-id="50ccb-187">`exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-187">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="50ccb-188">`versionName`: Текст, который будет отображаться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="50ccb-188">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="50ccb-189">Вы можете задать используемую версию PowerShell по умолчанию, задав параметр `powershell.powerShellDefaultVersion` для текста, отображаемого в меню сеансов (`versionName` в последнем параметре):</span><span class="sxs-lookup"><span data-stu-id="50ccb-189">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

<span data-ttu-id="50ccb-190">Задав этот параметр, перезапустите Visual Studio Code или перезагрузите текущее окно Visual Studio Code через**Палитру команд**, введя **Разработчик: Reload Window** (Разработчик: перезагрузить окно).</span><span class="sxs-lookup"><span data-stu-id="50ccb-190">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="50ccb-191">Открыв меню сеансов, вы увидите дополнительные версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-191">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="50ccb-192">Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-192">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="50ccb-193">Параметры конфигурации для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50ccb-193">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="50ccb-194">Прежде всего, если вы не знаете, как изменить параметры в Visual Studio Code, мы рекомендуем просмотреть [документацию по параметрам Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).</span><span class="sxs-lookup"><span data-stu-id="50ccb-194">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend looking at [Visual Studio Code's settings documentation](https://code.visualstudio.com/docs/getstarted/settings).</span></span>

<span data-ttu-id="50ccb-195">Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-195">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="50ccb-196">Если вы не хотите, чтобы эти параметры влияли на файлы всех типов, Visual Studio Code также позволяет задавать конфигурации для каждого языка отдельно.</span><span class="sxs-lookup"><span data-stu-id="50ccb-196">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="50ccb-197">Создать параметр для конкретного языка можно, поместив параметры в поле `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-197">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="50ccb-198">Пример:</span><span class="sxs-lookup"><span data-stu-id="50ccb-198">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="50ccb-199">Дополнительные сведения о кодировке файлов в Visual Studio Code см. в статье [Основные сведения о кодировке файлов в VSCode и PowerShell](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="50ccb-199">For more information about file encoding in Visual Studio Code, see [Understanding file encoding](understanding-file-encoding.md).</span></span>
>
> <span data-ttu-id="50ccb-200">Также ознакомьтесь со статьей [Репликация функций интегрированной среды скриптов в Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) для получения других советов по настройке Visual Studio Code для редактирования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-200">Also check out the [How to replicate the ISE experience in Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="50ccb-201">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50ccb-201">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="50ccb-202">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="50ccb-202">No-workspace debugging</span></span>

<span data-ttu-id="50ccb-203">Начиная с Visual Studio Code версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-203">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="50ccb-204">Откройте файл сценария PowerShell с помощью команды **Файл > Открыть файл...** , установите точку останова на строке, нажмите клавишу <kbd>F9</kbd>, а затем — клавишу <kbd>F5</kbd> для запуска отладки.</span><span class="sxs-lookup"><span data-stu-id="50ccb-204">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="50ccb-205">Откроется панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="50ccb-205">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="50ccb-206">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="50ccb-206">Workspace debugging</span></span>

<span data-ttu-id="50ccb-207">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**. Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="50ccb-207">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="50ccb-208">Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, нажав клавишу <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50ccb-208">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="50ccb-209">Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.</span><span class="sxs-lookup"><span data-stu-id="50ccb-209">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="50ccb-210">Мы вернемся к этому чуть позже.</span><span class="sxs-lookup"><span data-stu-id="50ccb-210">We'll get to those in a moment.</span></span>

<span data-ttu-id="50ccb-211">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="50ccb-211">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="50ccb-212">Откройте представление **Отладка** в Windows или Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>).</span><span class="sxs-lookup"><span data-stu-id="50ccb-212">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="50ccb-213">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50ccb-213">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="50ccb-214">Щелкните ссылку create a launch.json file (создать файл launch.json).</span><span class="sxs-lookup"><span data-stu-id="50ccb-214">Click the "create a launch.json file" link.</span></span>
  1. <span data-ttu-id="50ccb-215">Visual Studio Code предлагает вам **выбрать среду**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-215">Visual Studio Code prompts you to **Select Environment**.</span></span> <span data-ttu-id="50ccb-216">Выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-216">Choose **PowerShell**.</span></span>
  1. <span data-ttu-id="50ccb-217">Наконец, выберите тип отладки, который вы хотите использовать:</span><span class="sxs-lookup"><span data-stu-id="50ccb-217">Lastly, choose the type of debugging you'd like to use:</span></span>

- <span data-ttu-id="50ccb-218">**Launch Current File** (Запуск текущего файла) — запуск и отладка файла в текущем активном окне редактора.</span><span class="sxs-lookup"><span data-stu-id="50ccb-218">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
- <span data-ttu-id="50ccb-219">**Launch Script** (Запуск скрипта) — запуск и отладка указанного файла или команды.</span><span class="sxs-lookup"><span data-stu-id="50ccb-219">**Launch Script** - Launch and debug the specified file or command</span></span>
- <span data-ttu-id="50ccb-220">**Interactive Session** (Интерактивный сеанс) — команды отладки, выполняемые из интегрированной консоли.</span><span class="sxs-lookup"><span data-stu-id="50ccb-220">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
- <span data-ttu-id="50ccb-221">**Attach (Подключение)**  — подключение отладчика к выполняемому хост-процессу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-221">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="50ccb-222">В результате Visual Studio Code создает каталог и файл `.vscode\launch.json` в корневой папке рабочей области.</span><span class="sxs-lookup"><span data-stu-id="50ccb-222">The result is that Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="50ccb-223">Именно там хранится ваша конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="50ccb-223">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="50ccb-224">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="50ccb-224">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="50ccb-225">Содержимое файла `launch.json`:</span><span class="sxs-lookup"><span data-stu-id="50ccb-225">The contents of the `launch.json` file are:</span></span>

```json
{
  "version": "0.2.0",
  "configurations": [
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Launch (current file)",
          "script": "${file}",
          "args": [],
          "cwd": "${file}"
      },
      {
          "type": "PowerShell",
          "request": "attach",
          "name": "PowerShell Attach to Host Process",
          "processId": "${command.PickPSHostProcess}",
          "runspaceId": 1
      },
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Interactive Session",
          "cwd": "${workspaceRoot}"
      }
  ]
}
```

<span data-ttu-id="50ccb-226">Этот файл представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="50ccb-226">This file represents the common debug scenarios.</span></span> <span data-ttu-id="50ccb-227">При открытии его в редакторе отображается кнопка **Добавить конфигурацию...**</span><span class="sxs-lookup"><span data-stu-id="50ccb-227">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="50ccb-228">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ccb-228">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="50ccb-229">Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий).</span><span class="sxs-lookup"><span data-stu-id="50ccb-229">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="50ccb-230">С помощью этой конфигурации можно указать файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой именно файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="50ccb-230">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="50ccb-231">После задания конфигурации отладки вы можете указать конфигурацию, используемую во время сеанса отладки,</span><span class="sxs-lookup"><span data-stu-id="50ccb-231">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="50ccb-232">выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-232">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="50ccb-233">Полезные ресурсы</span><span class="sxs-lookup"><span data-stu-id="50ccb-233">Useful resources</span></span>

<span data-ttu-id="50ccb-234">Существует несколько видео и записей блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="50ccb-234">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="50ccb-235">Видео</span><span class="sxs-lookup"><span data-stu-id="50ccb-235">Videos</span></span>

- [<span data-ttu-id="50ccb-236">Использование Visual Studio Code в качестве редактора PowerShell по умолчанию</span><span class="sxs-lookup"><span data-stu-id="50ccb-236">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="50ccb-237">Visual Studio Code: подробный обзор отладки сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ccb-237">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="50ccb-238">Записи блога</span><span class="sxs-lookup"><span data-stu-id="50ccb-238">Blog posts</span></span>

- <span data-ttu-id="50ccb-239">[Расширение PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="50ccb-239">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="50ccb-240">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="50ccb-240">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="50ccb-241">[Руководство по отладке Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="50ccb-241">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="50ccb-242">[Отладка PowerShell в Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="50ccb-242">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="50ccb-243">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="50ccb-243">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="50ccb-244">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="50ccb-244">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="50ccb-245">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="50ccb-245">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="50ccb-246">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="50ccb-246">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="50ccb-247">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="50ccb-247">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="50ccb-248">Расширение PowerShell для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50ccb-248">PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="50ccb-249">Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="50ccb-249">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>

<span data-ttu-id="50ccb-250">Если вы заинтересованы в участии, запрос на вытягивание очень важен.</span><span class="sxs-lookup"><span data-stu-id="50ccb-250">If you're interested in contributing, Pull Request are greatly appreciated.</span></span> <span data-ttu-id="50ccb-251">Чтобы приступить к работе, следуйте указаниям в [документации для разработчиков на сайте GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md).</span><span class="sxs-lookup"><span data-stu-id="50ccb-251">Follow along with the [developer documentation on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md) to get started.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="50ccb-252">Устранение проблем с расширением PowerShell для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="50ccb-252">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="50ccb-253">Если у вас возникли проблемы с использованием Visual Studio Code для разработки сценариев PowerShell, ознакомьтесь с [руководством по устранению проблем на сайте GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="50ccb-253">If you experience any issues using Visual Studio Code for PowerShell script development, please take a look at the [troubleshooting guide on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
