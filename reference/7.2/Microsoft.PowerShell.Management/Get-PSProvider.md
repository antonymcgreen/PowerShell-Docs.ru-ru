---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 20820d2d194f41d43048c9617b63b9acb3fbb4f8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604575"
---
# <span data-ttu-id="61796-102">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="61796-102">Get-PSProvider</span></span>

## <span data-ttu-id="61796-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="61796-103">SYNOPSIS</span></span>
<span data-ttu-id="61796-104">Возвращает сведения об указанном поставщике PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61796-104">Gets information about the specified PowerShell provider.</span></span>

## <span data-ttu-id="61796-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61796-105">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="61796-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61796-106">DESCRIPTION</span></span>

<span data-ttu-id="61796-107">`Get-PSProvider`Командлет получает поставщиков PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="61796-107">The `Get-PSProvider` cmdlet gets the PowerShell providers in the current session.</span></span>
<span data-ttu-id="61796-108">Можно получить определенный диск или все диски в сеансе.</span><span class="sxs-lookup"><span data-stu-id="61796-108">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="61796-109">Поставщики PowerShell позволяют обращаться к различным хранилищам данных, как будто они являются дисками файловой системы.</span><span class="sxs-lookup"><span data-stu-id="61796-109">PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="61796-110">Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="61796-110">For information about PowerShell providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="61796-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="61796-111">EXAMPLES</span></span>

### <span data-ttu-id="61796-112">Пример 1. Отображение списка всех доступных поставщиков</span><span class="sxs-lookup"><span data-stu-id="61796-112">Example 1: Display a list of all available providers</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="61796-113">Эта команда отображает список всех доступных поставщиков PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61796-113">This command displays a list of all available PowerShell providers.</span></span>

### <span data-ttu-id="61796-114">Пример 2. Отображение списка всех поставщиков PowerShell, начинающихся с указанных букв</span><span class="sxs-lookup"><span data-stu-id="61796-114">Example 2: Display a list of all PowerShell providers that begin with specified letters</span></span>

```powershell
Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="61796-115">Эта команда отображает список всех поставщиков PowerShell с именами, начинающимися с буквы f или r.</span><span class="sxs-lookup"><span data-stu-id="61796-115">This command displays a list of all PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="61796-116">Пример 3. Поиск оснасток или модулей, которые добавляют поставщики в сеанс</span><span class="sxs-lookup"><span data-stu-id="61796-116">Example 3: Find snap-ins or module that added providers to your session</span></span>

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="61796-117">Эти команды находят оснастки или модули PowerShell, которые добавляют поставщиков в ваш сеанс.</span><span class="sxs-lookup"><span data-stu-id="61796-117">These commands find the PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="61796-118">Все элементы PowerShell, включая поставщики, создаются в оснастке или модуле.</span><span class="sxs-lookup"><span data-stu-id="61796-118">All PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="61796-119">Эти команды используют свойства PSSnapin и Module объекта **провидеринфо** , который `Get-PSProvider` возвращает.</span><span class="sxs-lookup"><span data-stu-id="61796-119">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that `Get-PSProvider` returns.</span></span>
<span data-ttu-id="61796-120">Значения этих свойств указывают на имя оснастки или модуля, который добавил поставщика.</span><span class="sxs-lookup"><span data-stu-id="61796-120">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="61796-121">Первая команда возвращает сведения о всех поставщиках в рамках сеанса и форматирует их в виде таблицы, содержащей значения свойств Name, Module и PSSnapin.</span><span class="sxs-lookup"><span data-stu-id="61796-121">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="61796-122">Вторая команда использует `Where-Object` командлет для получения поставщиков, поступающих от оснастки **Microsoft. PowerShell. Security** .</span><span class="sxs-lookup"><span data-stu-id="61796-122">The second command uses the `Where-Object` cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="61796-123">Пример 4. разрешение пути к свойству Home поставщика файловой системы</span><span class="sxs-lookup"><span data-stu-id="61796-123">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

<span data-ttu-id="61796-124">В этом примере показано, что символ тильды (~) представляет значение свойства **Home** поставщика FileSystem.</span><span class="sxs-lookup"><span data-stu-id="61796-124">This example shows that the tilde symbol (~) represents the value of the **Home** property of the FileSystem provider.</span></span>
<span data-ttu-id="61796-125">Значение свойства **Home** является необязательным, но для поставщика **FileSystem** оно определяется как `$env:homedrive\$env:homepath` или `$home` .</span><span class="sxs-lookup"><span data-stu-id="61796-125">The **Home** property value is optional, but for the **FileSystem** provider, it is defined as `$env:homedrive\$env:homepath` or `$home`.</span></span>

## <span data-ttu-id="61796-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61796-126">PARAMETERS</span></span>

### <span data-ttu-id="61796-127">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="61796-127">-PSProvider</span></span>

<span data-ttu-id="61796-128">Указывает имя или имена поставщиков PowerShell, о которых этот командлет получает сведения.</span><span class="sxs-lookup"><span data-stu-id="61796-128">Specifies the name or names of the PowerShell providers about which this cmdlet gets information.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="61796-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="61796-129">CommonParameters</span></span>

<span data-ttu-id="61796-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61796-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61796-131">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="61796-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="61796-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="61796-132">INPUTS</span></span>

### <span data-ttu-id="61796-133">String[]</span><span class="sxs-lookup"><span data-stu-id="61796-133">String[]</span></span>

<span data-ttu-id="61796-134">В этот командлет можно передать одну или несколько строк имени поставщика.</span><span class="sxs-lookup"><span data-stu-id="61796-134">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="61796-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="61796-135">OUTPUTS</span></span>

### <span data-ttu-id="61796-136">System. Management. Automation. Провидеринфо</span><span class="sxs-lookup"><span data-stu-id="61796-136">System.Management.Automation.ProviderInfo</span></span>

<span data-ttu-id="61796-137">Этот командлет возвращает объекты, которые представляют поставщиков PowerShell в сеансе.</span><span class="sxs-lookup"><span data-stu-id="61796-137">This cmdlet returns objects that represent the PowerShell providers in the session.</span></span>

## <span data-ttu-id="61796-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="61796-138">NOTES</span></span>

## <span data-ttu-id="61796-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="61796-139">RELATED LINKS</span></span>

