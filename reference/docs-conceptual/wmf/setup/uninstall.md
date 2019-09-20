---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Удаление WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147864"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="1d0a1-103">Инструкции по удалению</span><span class="sxs-lookup"><span data-stu-id="1d0a1-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="1d0a1-104">Использование командной строки</span><span class="sxs-lookup"><span data-stu-id="1d0a1-104">Using Command Prompt</span></span>

1. <span data-ttu-id="1d0a1-105">Откройте окно **Командная строка**.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="1d0a1-106">Запустите [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) (Автономное средство запуска Центра обновления Windows), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1d0a1-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="1d0a1-107">В Windows Server 2012 R2 и Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="1d0a1-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="1d0a1-108">В Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="1d0a1-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="1d0a1-109">В Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1):</span><span class="sxs-lookup"><span data-stu-id="1d0a1-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="1d0a1-110">Использование панели управления</span><span class="sxs-lookup"><span data-stu-id="1d0a1-110">Using Control Panel</span></span>

1. <span data-ttu-id="1d0a1-111">Откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="1d0a1-112">Откройте **Программы** и выберите **Удаление программы**.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="1d0a1-113">Щелкните **Просмотр установленных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="1d0a1-114">Выберите **Windows Management Framework 5.0** в списке установленных обновлений.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="1d0a1-115">Это соответствует *KB3134758*, *KB3134759* или *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="1d0a1-116">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-116">Click **Uninstall.**</span></span>
