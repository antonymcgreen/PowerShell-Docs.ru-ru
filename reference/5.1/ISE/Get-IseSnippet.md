---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229717"
---
# <span data-ttu-id="a71ea-103">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a71ea-103">Get-IseSnippet</span></span>

## <span data-ttu-id="a71ea-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a71ea-104">SYNOPSIS</span></span>
<span data-ttu-id="a71ea-105">Возвращает фрагменты кода, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="a71ea-105">Gets snippets that the user created.</span></span>

## <span data-ttu-id="a71ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a71ea-106">SYNTAX</span></span>

```
Get-IseSnippet [<CommonParameters>]
```

## <span data-ttu-id="a71ea-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a71ea-107">DESCRIPTION</span></span>

<span data-ttu-id="a71ea-108">`Get-IseSnippet`Командлет возвращает файлы ps1xml, содержащие многократно используемые текстовые фрагменты, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="a71ea-108">The `Get-IseSnippet` cmdlet gets the PS1XML files that contain reusable text snippets that the user created.</span></span> <span data-ttu-id="a71ea-109">Он работает только в интегрированной среде сценариев (ISE) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a71ea-109">It works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="a71ea-110">При использовании `New-IseSnippet` командлета для создания фрагмента кода `New-IseSnippet` создает `<SnippetTitle>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге.</span><span class="sxs-lookup"><span data-stu-id="a71ea-110">When you use the `New-IseSnippet` cmdlet to create a snippet, `New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
<span data-ttu-id="a71ea-111">`Get-IseSnippet` Возвращает файлы фрагментов кода в каталоге фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="a71ea-111">`Get-IseSnippet` gets the snippet files in the Snippets directory.</span></span>

<span data-ttu-id="a71ea-112">Этот командлет не получает встроенные фрагменты кода или фрагменты кода, которые импортируются из модулей с помощью `Import-IseSnippet` командлета.</span><span class="sxs-lookup"><span data-stu-id="a71ea-112">This cmdlet does not get built-in snippets or snippets that are imported from modules through the `Import-IseSnippet` cmdlet.</span></span>

<span data-ttu-id="a71ea-113">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a71ea-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a71ea-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="a71ea-114">EXAMPLES</span></span>

### <span data-ttu-id="a71ea-115">Пример 1. получение всех определяемых пользователем фрагментов кода</span><span class="sxs-lookup"><span data-stu-id="a71ea-115">Example 1: Get all user-defined snippets</span></span>

<span data-ttu-id="a71ea-116">Этот пример получает все фрагменты кода, определяемые пользователем, в каталоге фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="a71ea-116">This example gets all user-define snippets in the Snippets directory.</span></span>

```powershell
Get-IseSnippet
```

### <span data-ttu-id="a71ea-117">Пример 2. копирование всех пользовательских фрагментов данных с удаленных компьютеров в общий каталог</span><span class="sxs-lookup"><span data-stu-id="a71ea-117">Example 2: Copy all user-defined snippets from remote computers to a shared directory</span></span>

<span data-ttu-id="a71ea-118">В этом примере все созданные пользователем фрагменты кода копируются из группы удаленных компьютеров в каталог общих фрагментов.</span><span class="sxs-lookup"><span data-stu-id="a71ea-118">This example copies all of the user-created snippets from a group of remote computers to a shared Snippets directory.</span></span>

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

<span data-ttu-id="a71ea-119">`Invoke-Command` выполняется `Get-IseSnippet` на компьютерах в `Servers.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="a71ea-119">`Invoke-Command` runs `Get-IseSnippet` on the computers in the `Servers.txt` file.</span></span> <span data-ttu-id="a71ea-120">Оператор конвейера ( `|` ) отправляет файлы фрагментов в `Copy-Item` командлет, который копирует их в каталог, указанный параметром **Destination** .</span><span class="sxs-lookup"><span data-stu-id="a71ea-120">A pipeline operator (`|`) sends the snippet files to the `Copy-Item` cmdlet, which copies them to the directory that is specified by the **Destination** parameter.</span></span>

### <span data-ttu-id="a71ea-121">Пример 3. Отображение заголовка и текста каждого фрагмента кода на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="a71ea-121">Example 3: Display the title and text of each snippet on a local computer</span></span>

<span data-ttu-id="a71ea-122">В этом примере `Get-IseSnippet` `Select-Xml` командлеты и используются для вывода заголовка и текста каждого фрагмента кода на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a71ea-122">This example uses the `Get-IseSnippet` and `Select-Xml` cmdlets to display the title and text of each snippet on the local computer.</span></span>

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### <span data-ttu-id="a71ea-123">Пример 4. Отображение заголовка и описания всех фрагментов кода в сеансе</span><span class="sxs-lookup"><span data-stu-id="a71ea-123">Example 4: Display the title and description of all snippets in the session</span></span>

<span data-ttu-id="a71ea-124">В этом примере отображаются заголовок и описание всех фрагментов в сеансе, включая встроенные фрагменты кода, пользовательские фрагменты и импортированные фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="a71ea-124">This example displays the title and description of all snippets in the session, including built-in snippets, user-defined snippets, and imported snippets.</span></span>

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

<span data-ttu-id="a71ea-125">`$PSISE`Переменная представляет собой хостную программу интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a71ea-125">The `$PSISE` variable represents the Windows PowerShell ISE host program.</span></span> <span data-ttu-id="a71ea-126">Свойство **CurrentPowerShellTab** `$PSISE` переменной представляет текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="a71ea-126">The **CurrentPowerShellTab** property of the `$PSISE` variable represent the current session.</span></span> <span data-ttu-id="a71ea-127">Свойство **Snippets** представляет фрагменты кода в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a71ea-127">The **Snippets** property represents snippets in the current session.</span></span>

<span data-ttu-id="a71ea-128">`$PSISE.CurrentPowerShellTab.Snippets`Команда возвращает объект **Microsoft. PowerShell. host. ISE. ISESnippet** , представляющий фрагмент, в отличие от `Get-IseSnippet` командлета.</span><span class="sxs-lookup"><span data-stu-id="a71ea-128">The `$PSISE.CurrentPowerShellTab.Snippets` command returns a **Microsoft.PowerShell.Host.ISE.ISESnippet** object that represents a snippet, unlike the `Get-IseSnippet` cmdlet.</span></span> <span data-ttu-id="a71ea-129">`Get-IseSnippet` Возвращает объект File (System. IO. FileInfo), представляющий файл фрагмента.</span><span class="sxs-lookup"><span data-stu-id="a71ea-129">`Get-IseSnippet` returns a file object (System.Io.FileInfo) that represents a snippet file.</span></span>

<span data-ttu-id="a71ea-130">`Format-Table`Командлет отображает свойства **Дисплайтитле** и **Description** фрагментов кода в таблице.</span><span class="sxs-lookup"><span data-stu-id="a71ea-130">The `Format-Table` cmdlet displays the **DisplayTitle** and **Description** properties of the snippets in a table.</span></span>

## <span data-ttu-id="a71ea-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a71ea-131">PARAMETERS</span></span>

### <span data-ttu-id="a71ea-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a71ea-132">CommonParameters</span></span>

<span data-ttu-id="a71ea-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a71ea-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a71ea-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a71ea-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a71ea-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a71ea-135">INPUTS</span></span>

## <span data-ttu-id="a71ea-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a71ea-136">OUTPUTS</span></span>

### <span data-ttu-id="a71ea-137">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="a71ea-137">System.IO.FileInfo</span></span>

<span data-ttu-id="a71ea-138">Этот командлет возвращает файловый объект, представляющий файл фрагмента.</span><span class="sxs-lookup"><span data-stu-id="a71ea-138">This cmdlet returns a file object that represents the snippet file.</span></span>

## <span data-ttu-id="a71ea-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a71ea-139">NOTES</span></span>

* <span data-ttu-id="a71ea-140">`New-IseSnippet`Командлет сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="a71ea-140">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="a71ea-141">Таким образом, Windows PowerShell не может добавить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted** .</span><span class="sxs-lookup"><span data-stu-id="a71ea-141">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="a71ea-142">В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a71ea-142">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="a71ea-143">Чтобы использовать неподписанные пользовательские фрагменты кода, `Get-IseSnippet` возвращаемые командлетом, измените политику выполнения, а затем перезапустите интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a71ea-143">To use unsigned user-created snippets that the `Get-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="a71ea-144">Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="a71ea-144">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="a71ea-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a71ea-145">RELATED LINKS</span></span>

[<span data-ttu-id="a71ea-146">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a71ea-146">New-IseSnippet</span></span>](New-IseSnippet.md)

[<span data-ttu-id="a71ea-147">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a71ea-147">Import-IseSnippet</span></span>](Import-IseSnippet.md)
