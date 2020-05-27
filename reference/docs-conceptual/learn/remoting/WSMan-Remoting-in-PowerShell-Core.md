---
title: Удаленное взаимодействие с WS-Management (WSMan) в PowerShell Core
description: Удаленное взаимодействие в PowerShell Core с помощью WSMan
ms.date: 08/06/2018
ms.openlocfilehash: 7b090e1463808ab10758bbd417d52fcc16c31366
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564519"
---
# <a name="ws-management-wsman-remoting-in-powershell-core"></a><span data-ttu-id="0d824-103">Удаленное взаимодействие с WS-Management (WSMan) в PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="0d824-103">WS-Management (WSMan) Remoting in PowerShell Core</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="0d824-104">Инструкции по созданию конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="0d824-104">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="0d824-105">Пакет PowerShell Core для Windows включает подключаемый модуль WinRM (`pwrshplugin.dll`) и сценарий установки (`Install-PowerShellRemoting.ps1`) в `$PSHome`.</span><span class="sxs-lookup"><span data-stu-id="0d824-105">The PowerShell Core package for Windows includes a WinRM plug-in (`pwrshplugin.dll`) and an installation script (`Install-PowerShellRemoting.ps1`) in `$PSHome`.</span></span>
<span data-ttu-id="0d824-106">Эти файлы позволяют PowerShell принимать входящие удаленные подключения PowerShell, когда указана его конечная точка.</span><span class="sxs-lookup"><span data-stu-id="0d824-106">These files enable PowerShell to accept incoming PowerShell remote connections when its endpoint is specified.</span></span>

### <a name="motivation"></a><span data-ttu-id="0d824-107">Причины для использования</span><span class="sxs-lookup"><span data-stu-id="0d824-107">Motivation</span></span>

<span data-ttu-id="0d824-108">Установка PowerShell может устанавливать удаленные сеансы PowerShell с компьютерами, используя `New-PSSession` и `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="0d824-108">An installation of PowerShell can establish PowerShell sessions to remote computers using `New-PSSession` and `Enter-PSSession`.</span></span>
<span data-ttu-id="0d824-109">Чтобы включить прием входящих удаленных подключений PowerShell, пользователю нужно создать конечную точку удаленного взаимодействия WinRM.</span><span class="sxs-lookup"><span data-stu-id="0d824-109">To enable it to accept incoming PowerShell remote connections, the user must create a WinRM remoting endpoint.</span></span>
<span data-ttu-id="0d824-110">Это сценарий, требующий явного согласия, в котором пользователь запускает Install-PowerShellRemoting.ps1 для создания конечной точки WinRM.</span><span class="sxs-lookup"><span data-stu-id="0d824-110">This is an explicit opt-in scenario where the user runs Install-PowerShellRemoting.ps1 to create the WinRM endpoint.</span></span>
<span data-ttu-id="0d824-111">Сценарий установки — это временное решение, пока в `Enable-PSRemoting` не будет добавлена дополнительная функциональность для выполнения данной задачи.</span><span class="sxs-lookup"><span data-stu-id="0d824-111">The installation script is a short-term solution until we add additional functionality to `Enable-PSRemoting` to perform the same action.</span></span>
<span data-ttu-id="0d824-112">Дополнительные сведения см. в описании вопроса [1193](https://github.com/PowerShell/PowerShell/issues/1193).</span><span class="sxs-lookup"><span data-stu-id="0d824-112">For more details, please see issue [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span></span>

### <a name="script-actions"></a><span data-ttu-id="0d824-113">Элемент "Действия скрипта"</span><span class="sxs-lookup"><span data-stu-id="0d824-113">Script Actions</span></span>

<span data-ttu-id="0d824-114">Сценарий</span><span class="sxs-lookup"><span data-stu-id="0d824-114">The script</span></span>

1. <span data-ttu-id="0d824-115">Создает каталог для подключаемого модуля в расположении `$env:windir\System32\PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="0d824-115">Creates a directory for the plug-in within `$env:windir\System32\PowerShell`</span></span>
1. <span data-ttu-id="0d824-116">Копирует туда pwrshplugin.dll.</span><span class="sxs-lookup"><span data-stu-id="0d824-116">Copies pwrshplugin.dll to that location</span></span>
1. <span data-ttu-id="0d824-117">Создает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0d824-117">Generates a configuration file</span></span>
1. <span data-ttu-id="0d824-118">Регистрирует этот подключаемый модуль в службе WinRM.</span><span class="sxs-lookup"><span data-stu-id="0d824-118">Registers that plug-in with WinRM</span></span>

### <a name="registration"></a><span data-ttu-id="0d824-119">Регистрация</span><span class="sxs-lookup"><span data-stu-id="0d824-119">Registration</span></span>

<span data-ttu-id="0d824-120">Сценарий следует запускать в сеансе PowerShell с правами администратора, и выполняется он в двух режимах.</span><span class="sxs-lookup"><span data-stu-id="0d824-120">The script must be executed within an Administrator-level PowerShell session and runs in two modes.</span></span>

#### <a name="executed-by-the-instance-of-powershell-that-it-will-register"></a><span data-ttu-id="0d824-121">Выполнение экземпляром PowerShell, где он будет зарегистрирован</span><span class="sxs-lookup"><span data-stu-id="0d824-121">Executed by the instance of PowerShell that it will register</span></span>

```powershell
Install-PowerShellRemoting.ps1
```

#### <a name="executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register"></a><span data-ttu-id="0d824-122">Выполнение экземпляром PowerShell, отличным от того, где он будет зарегистрирован</span><span class="sxs-lookup"><span data-stu-id="0d824-122">Executed by another instance of PowerShell on behalf of the instance that it will register</span></span>

```powershell
<path to powershell>\Install-PowerShellRemoting.ps1 -PowerShellHome "<absolute path to the instance's $PSHOME>"
```

<span data-ttu-id="0d824-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="0d824-123">For Example:</span></span>

```powershell
Set-Location -Path 'C:\Program Files\PowerShell\6.0.0\'
.\Install-PowerShellRemoting.ps1 -PowerShellHome "C:\Program Files\PowerShell\6.0.0\"
```

<span data-ttu-id="0d824-124">**Примечание**. Сценарий регистрации удаленного взаимодействия перезапускает WinRM, поэтому сразу после его запуска все существующие сеансы PSRP завершаются.</span><span class="sxs-lookup"><span data-stu-id="0d824-124">**NOTE:** The remoting registration script will restart WinRM, so all existing PSRP sessions will terminate immediately after the script is run.</span></span> <span data-ttu-id="0d824-125">Если запустить его во время удаленного сеанса, соединение будет разорвано.</span><span class="sxs-lookup"><span data-stu-id="0d824-125">If run during a remote session, this will terminate the connection.</span></span>

## <a name="how-to-connect-to-the-new-endpoint"></a><span data-ttu-id="0d824-126">Подключение к новой конечной точке</span><span class="sxs-lookup"><span data-stu-id="0d824-126">How to Connect to the New Endpoint</span></span>

<span data-ttu-id="0d824-127">Создайте сеанс PowerShell с новой конечной точкой PowerShell, указав `-ConfigurationName "some endpoint name"`.</span><span class="sxs-lookup"><span data-stu-id="0d824-127">Create a PowerShell session to the new PowerShell endpoint by specifying `-ConfigurationName "some endpoint name"`.</span></span> <span data-ttu-id="0d824-128">Чтобы подключиться к экземпляру PowerShell из примера выше, используйте одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="0d824-128">To connect to the PowerShell instance from the example above, use either:</span></span>

```powershell
New-PSSession ... -ConfigurationName "powershell.6.0.0"
Enter-PSSession ... -ConfigurationName "powershell.6.0.0"
```

<span data-ttu-id="0d824-129">Обратите внимание, что вызовы `New-PSSession` и `Enter-PSSession`, которые не указывают `-ConfigurationName`, ориентируются на конечную точку PowerShell по умолчанию — `microsoft.powershell`.</span><span class="sxs-lookup"><span data-stu-id="0d824-129">Note that `New-PSSession` and `Enter-PSSession` invocations that do not specify `-ConfigurationName` will target the default PowerShell endpoint, `microsoft.powershell`.</span></span>
