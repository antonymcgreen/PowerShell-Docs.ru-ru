---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228365"
---
# <span data-ttu-id="a6383-103">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a6383-103">Get-PSProvider</span></span>

## <span data-ttu-id="a6383-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a6383-104">SYNOPSIS</span></span>
<span data-ttu-id="a6383-105">Получает сведения об указанном поставщике Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6383-105">Gets information about the specified Windows PowerShell provider.</span></span>

## <span data-ttu-id="a6383-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6383-106">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a6383-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6383-107">DESCRIPTION</span></span>
<span data-ttu-id="a6383-108">Командлет **Get-psprovider** получает поставщиков Windows PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6383-108">The **Get-PSProvider** cmdlet gets the Windows PowerShell providers in the current session.</span></span>
<span data-ttu-id="a6383-109">Можно получить определенный диск или все диски в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6383-109">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="a6383-110">Поставщики Windows PowerShell позволяют обращаться к различным хранилищам данных так же, как к дискам файловой системы.</span><span class="sxs-lookup"><span data-stu-id="a6383-110">Windows PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="a6383-111">Сведения о поставщиках Windows PowerShell см. в разделе "about_Providers".</span><span class="sxs-lookup"><span data-stu-id="a6383-111">For information about Windows PowerShell providers, see about_Providers.</span></span>

## <span data-ttu-id="a6383-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a6383-112">EXAMPLES</span></span>

### <span data-ttu-id="a6383-113">Пример 1. Отображение списка всех доступных поставщиков</span><span class="sxs-lookup"><span data-stu-id="a6383-113">Example 1: Display a list of all available providers</span></span>

```
PS C:\> Get-PSProvider
```

<span data-ttu-id="a6383-114">Эта команда выводит список доступных поставщиков Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6383-114">This command displays a list of all available Windows PowerShell providers.</span></span>

### <span data-ttu-id="a6383-115">Пример 2. Отображение списка всех поставщиков Windows PowerShell, начинающихся с указанных букв</span><span class="sxs-lookup"><span data-stu-id="a6383-115">Example 2: Display a list of all Windows PowerShell providers that begin with specified letters</span></span>

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="a6383-116">Эта команда отображает список всех поставщиков Windows PowerShell с именами, начинающимися с буквы f или r.</span><span class="sxs-lookup"><span data-stu-id="a6383-116">This command displays a list of all Windows PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="a6383-117">Пример 3. Поиск оснасток или модулей, которые добавляют поставщики в сеанс</span><span class="sxs-lookup"><span data-stu-id="a6383-117">Example 3: Find snap-ins or module that added providers to your session</span></span>

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

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

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="a6383-118">Эти команды обнаруживают оснастки или модули Windows PowerShell, которые добавили поставщиков в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="a6383-118">These commands find the Windows PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="a6383-119">Источником всех элементов Windows PowerShell, включая поставщиков, являются оснастки или модули.</span><span class="sxs-lookup"><span data-stu-id="a6383-119">All Windows PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="a6383-120">Эти команды используют свойства PSSnapin и Module объекта **провидеринфо** , возвращаемого командлетом **Get-psprovider** .</span><span class="sxs-lookup"><span data-stu-id="a6383-120">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that **Get-PSProvider** returns.</span></span>
<span data-ttu-id="a6383-121">Значения этих свойств указывают на имя оснастки или модуля, который добавил поставщика.</span><span class="sxs-lookup"><span data-stu-id="a6383-121">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="a6383-122">Первая команда возвращает сведения о всех поставщиках в рамках сеанса и форматирует их в виде таблицы, содержащей значения свойств Name, Module и PSSnapin.</span><span class="sxs-lookup"><span data-stu-id="a6383-122">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="a6383-123">Вторая команда использует командлет Where-Object для получения поставщиков, которые поступают из оснастки **Microsoft. PowerShell. Security** .</span><span class="sxs-lookup"><span data-stu-id="a6383-123">The second command uses the Where-Object cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="a6383-124">Пример 4. разрешение пути к свойству Home поставщика файловой системы</span><span class="sxs-lookup"><span data-stu-id="a6383-124">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

<span data-ttu-id="a6383-125">В этом примере показано, что символ тильды (~) представляет значение свойства Home поставщика FileSystem.</span><span class="sxs-lookup"><span data-stu-id="a6383-125">This example shows that the tilde symbol (~) represents the value of the Home property of the FileSystem provider.</span></span>
<span data-ttu-id="a6383-126">Значение свойства Home является необязательным, но для поставщика FileSystem оно определяется как $env: хомедриве \$ env: хомепас или $Home.</span><span class="sxs-lookup"><span data-stu-id="a6383-126">The Home property value is optional, but for the FileSystem provider, it is defined as $env:homedrive\$env:homepath or $home.</span></span>

## <span data-ttu-id="a6383-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6383-127">PARAMETERS</span></span>

### <span data-ttu-id="a6383-128">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a6383-128">-PSProvider</span></span>
<span data-ttu-id="a6383-129">Указывает имя или имена поставщиков Windows PowerShell, о которых этот командлет получает сведения.</span><span class="sxs-lookup"><span data-stu-id="a6383-129">Specifies the name or names of the Windows PowerShell providers about which this cmdlet gets information.</span></span>

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

### <span data-ttu-id="a6383-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a6383-130">CommonParameters</span></span>
<span data-ttu-id="a6383-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6383-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6383-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6383-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6383-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a6383-133">INPUTS</span></span>

### <span data-ttu-id="a6383-134">String[]</span><span class="sxs-lookup"><span data-stu-id="a6383-134">String[]</span></span>

<span data-ttu-id="a6383-135">В этот командлет можно передать одну или несколько строк имени поставщика.</span><span class="sxs-lookup"><span data-stu-id="a6383-135">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="a6383-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a6383-136">OUTPUTS</span></span>

### <span data-ttu-id="a6383-137">System. Management. Automation. Провидеринфо</span><span class="sxs-lookup"><span data-stu-id="a6383-137">System.Management.Automation.ProviderInfo</span></span>
<span data-ttu-id="a6383-138">Этот командлет возвращает объекты, которые представляют поставщиков Windows PowerShell в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6383-138">This cmdlet returns objects that represent the Windows PowerShell providers in the session.</span></span>

## <span data-ttu-id="a6383-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a6383-139">NOTES</span></span>

## <span data-ttu-id="a6383-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a6383-140">RELATED LINKS</span></span>

## <span data-ttu-id="a6383-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a6383-141">RELATED LINKS</span></span>
