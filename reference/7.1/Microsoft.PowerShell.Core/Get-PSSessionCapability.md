---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: 891c62692ce694e7e7238814a4dc30da59f7c98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229501"
---
# <span data-ttu-id="e3698-103">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="e3698-103">Get-PSSessionCapability</span></span>

## <span data-ttu-id="e3698-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e3698-104">SYNOPSIS</span></span>
<span data-ttu-id="e3698-105">Возвращает возможности конкретного пользователя в конфигурации ограниченного сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3698-105">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="e3698-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3698-106">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="e3698-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3698-107">DESCRIPTION</span></span>

<span data-ttu-id="e3698-108">Командлет **Get-PSSessionCapability** Возвращает возможности конкретного пользователя в конфигурации с ограниченным сеансом.</span><span class="sxs-lookup"><span data-stu-id="e3698-108">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="e3698-109">Используйте этот командлет для аудита настроенных конфигураций сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e3698-109">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="e3698-110">Начиная с Windows PowerShell 5,0, можно использовать свойство **RoleDefinitions** в файле конфигурации сеанса (. pssc).</span><span class="sxs-lookup"><span data-stu-id="e3698-110">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="e3698-111">Использование этого свойства позволяет предоставлять пользователям различные возможности для одной ограниченной конечной точки на основе членства в группе.</span><span class="sxs-lookup"><span data-stu-id="e3698-111">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="e3698-112">Командлет **Get-PSSessionCapability** сокращает сложность при аудите этих конечных точек, позволяя определить точные возможности, предоставленные пользователю.</span><span class="sxs-lookup"><span data-stu-id="e3698-112">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="e3698-113">По умолчанию командлет **Get-PSSessionCapability** возвращает список команд, которые указанный пользователь может запускать в указанной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e3698-113">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="e3698-114">Это эквивалентно пользователю, выполняющему **команду Get-Command** в указанной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e3698-114">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="e3698-115">При запуске с параметром *Full* этот командлет возвращает объект **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="e3698-115">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="e3698-116">Этот объект содержит сведения о пространстве выполнения PowerShell, с которым будет взаимодействовать указанный пользователь для указанной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e3698-116">This object contains details about the PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="e3698-117">Он содержит такие сведения, как языковой режим, политика выполнения и переменные среды.</span><span class="sxs-lookup"><span data-stu-id="e3698-117">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="e3698-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="e3698-118">EXAMPLES</span></span>

### <span data-ttu-id="e3698-119">Пример 1. получение команд, доступных пользователю</span><span class="sxs-lookup"><span data-stu-id="e3698-119">Example 1: Get commands available for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="e3698-120">В этом примере возвращаются команды, доступные пользователю, Контосо\усер при подключении к ограниченной конечной точке Endpoint1 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3698-120">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="e3698-121">Пример 2. Получение сведений о пространстве выполнения для пользователя</span><span class="sxs-lookup"><span data-stu-id="e3698-121">Example 2: Get details about a runspace for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="e3698-122">В этом примере возвращаются сведения о пространстве выполнения, с которым будет взаимодействовать пользователь, Контосо\усер при подключении к ограниченной конечной точке Endpoint1.</span><span class="sxs-lookup"><span data-stu-id="e3698-122">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="e3698-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3698-123">PARAMETERS</span></span>

### <span data-ttu-id="e3698-124">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e3698-124">-ConfigurationName</span></span>

<span data-ttu-id="e3698-125">Задает проверяемую конфигурацию ограниченного сеанса (конечную точку).</span><span class="sxs-lookup"><span data-stu-id="e3698-125">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3698-126">-Full</span><span class="sxs-lookup"><span data-stu-id="e3698-126">-Full</span></span>

<span data-ttu-id="e3698-127">Указывает, что этот командлет возвращает все начальное состояние сеанса для указанного пользователя в заданной ограниченной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e3698-127">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3698-128">-Username</span><span class="sxs-lookup"><span data-stu-id="e3698-128">-Username</span></span>

<span data-ttu-id="e3698-129">Указывает пользователя, возможности которого проверяются.</span><span class="sxs-lookup"><span data-stu-id="e3698-129">Specifies the user whose capabilities you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3698-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e3698-130">CommonParameters</span></span>

<span data-ttu-id="e3698-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3698-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3698-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3698-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3698-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e3698-133">INPUTS</span></span>

## <span data-ttu-id="e3698-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e3698-134">OUTPUTS</span></span>

### <span data-ttu-id="e3698-135">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="e3698-135">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="e3698-136">System.Management.Automation.FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="e3698-136">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="e3698-137">System.Management.Automation.Runspaces.IniТиалсессионстате</span><span class="sxs-lookup"><span data-stu-id="e3698-137">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="e3698-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e3698-138">NOTES</span></span>

## <span data-ttu-id="e3698-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e3698-139">RELATED LINKS</span></span>

[<span data-ttu-id="e3698-140">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="e3698-140">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)

