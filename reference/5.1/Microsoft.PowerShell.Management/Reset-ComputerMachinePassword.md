---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227909"
---
# <span data-ttu-id="610c6-103">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="610c6-103">Reset-ComputerMachinePassword</span></span>

## <span data-ttu-id="610c6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="610c6-104">SYNOPSIS</span></span>
<span data-ttu-id="610c6-105">Сбрасывает пароль учетной записи компьютера для компьютера.</span><span class="sxs-lookup"><span data-stu-id="610c6-105">Resets the machine account password for the computer.</span></span>

## <span data-ttu-id="610c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="610c6-106">SYNTAX</span></span>

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="610c6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="610c6-107">DESCRIPTION</span></span>
<span data-ttu-id="610c6-108">Командлет **Reset-компутермачинепассворд** изменяет пароль учетной записи компьютера, используемый компьютерами для проверки подлинности на контроллерах домена в домене.</span><span class="sxs-lookup"><span data-stu-id="610c6-108">The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.</span></span>
<span data-ttu-id="610c6-109">Этот командлет можно использовать для сброса пароля локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="610c6-109">You can use it to reset the password of the local computer.</span></span>

## <span data-ttu-id="610c6-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="610c6-110">EXAMPLES</span></span>

### <span data-ttu-id="610c6-111">Пример 1. Сброс пароля для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="610c6-111">Example 1: Reset the password for the local computer</span></span>

```
PS C:\> Reset-ComputerMachinePassword
```

<span data-ttu-id="610c6-112">Эта команда сбрасывает пароль компьютера для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="610c6-112">This command resets the computer password for the local computer.</span></span>
<span data-ttu-id="610c6-113">Команда выполняется с использованием учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="610c6-113">The command runs with the credentials of the current user.</span></span>

### <span data-ttu-id="610c6-114">Пример 2. Сброс пароля для локального компьютера с помощью указанного контроллера домена</span><span class="sxs-lookup"><span data-stu-id="610c6-114">Example 2: Reset the password for the local computer by using a specified domain controller</span></span>

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

<span data-ttu-id="610c6-115">Эта команда сбрасывает пароль компьютера локального компьютера с помощью контроллера домена DC01.</span><span class="sxs-lookup"><span data-stu-id="610c6-115">This command resets the computer password of the local computer by using the DC01 domain controller.</span></span>
<span data-ttu-id="610c6-116">Параметр *Credential* используется для указания учетной записи пользователя, имеющей разрешение на сброс пароля компьютера в домене.</span><span class="sxs-lookup"><span data-stu-id="610c6-116">It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.</span></span>

### <span data-ttu-id="610c6-117">Пример 3. Сброс пароля на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="610c6-117">Example 3: Reset the password on a remote computer</span></span>

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

<span data-ttu-id="610c6-118">Эта команда использует командлет Invoke-Command для выполнения команды **Reset-компутермачинепассворд** на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="610c6-118">This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.</span></span>

<span data-ttu-id="610c6-119">Подробнее об удаленных командах в Windows PowerShell см. в разделе about_Remote, а также в разделе, посвященном командлету **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="610c6-119">For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command** .</span></span>

## <span data-ttu-id="610c6-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="610c6-120">PARAMETERS</span></span>

### <span data-ttu-id="610c6-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="610c6-121">-Credential</span></span>
<span data-ttu-id="610c6-122">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="610c6-122">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="610c6-123">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="610c6-123">The default is the current user.</span></span>

<span data-ttu-id="610c6-124">Введите имя пользователя, например User01 или Domain01\User01, либо укажите объект **PSCredential** , например формируемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="610c6-124">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="610c6-125">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="610c6-125">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="610c6-126">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="610c6-126">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610c6-127">-Server</span><span class="sxs-lookup"><span data-stu-id="610c6-127">-Server</span></span>
<span data-ttu-id="610c6-128">Указывает имя контроллера домена для использования, когда этот командлет задает пароль учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="610c6-128">Specifies the name of a domain controller to use when this cmdlet sets the computer account password.</span></span>

<span data-ttu-id="610c6-129">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="610c6-129">This parameter is optional.</span></span>
<span data-ttu-id="610c6-130">Если он не указан, команда выполняется текущим контроллером домена.</span><span class="sxs-lookup"><span data-stu-id="610c6-130">If you omit this parameter, a domain controller is chosen to service the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610c6-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="610c6-131">-Confirm</span></span>
<span data-ttu-id="610c6-132">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="610c6-132">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610c6-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="610c6-133">-WhatIf</span></span>
<span data-ttu-id="610c6-134">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="610c6-134">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="610c6-135">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="610c6-135">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="610c6-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="610c6-136">CommonParameters</span></span>
<span data-ttu-id="610c6-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="610c6-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="610c6-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="610c6-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="610c6-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="610c6-139">INPUTS</span></span>

### <span data-ttu-id="610c6-140">Нет</span><span class="sxs-lookup"><span data-stu-id="610c6-140">None</span></span>
<span data-ttu-id="610c6-141">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="610c6-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="610c6-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="610c6-142">OUTPUTS</span></span>

### <span data-ttu-id="610c6-143">Нет</span><span class="sxs-lookup"><span data-stu-id="610c6-143">None</span></span>
<span data-ttu-id="610c6-144">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="610c6-144">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="610c6-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="610c6-145">NOTES</span></span>

## <span data-ttu-id="610c6-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="610c6-146">RELATED LINKS</span></span>

## <span data-ttu-id="610c6-147">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="610c6-147">RELATED LINKS</span></span>
