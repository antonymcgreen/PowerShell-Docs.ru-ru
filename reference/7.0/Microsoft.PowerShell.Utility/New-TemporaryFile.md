---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: c4bfe6b4ed04ae638421c18f5095403057dc03c9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225837"
---
# <span data-ttu-id="e508b-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="e508b-103">New-TemporaryFile</span></span>

## <span data-ttu-id="e508b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e508b-104">SYNOPSIS</span></span>
<span data-ttu-id="e508b-105">Создает временный файл.</span><span class="sxs-lookup"><span data-stu-id="e508b-105">Creates a temporary file.</span></span>

## <span data-ttu-id="e508b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e508b-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e508b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e508b-107">DESCRIPTION</span></span>

<span data-ttu-id="e508b-108">Этот командлет создает временные файлы, которые можно использовать в скриптах.</span><span class="sxs-lookup"><span data-stu-id="e508b-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="e508b-109">`New-TemporaryFile`Командлет создает пустой файл с `.tmp` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="e508b-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="e508b-110">Этот командлет называет файл `tmp<NNNN>.tmp` , где `<NNNN>` — случайное шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="e508b-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="e508b-111">Командлет создает файл во **временной** папке.</span><span class="sxs-lookup"><span data-stu-id="e508b-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="e508b-112">Этот командлет использует метод [path. жеттемппас ()](/dotnet/api/system.io.path.gettemppath) для поиска **временной** папки.</span><span class="sxs-lookup"><span data-stu-id="e508b-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="e508b-113">Этот метод проверяет наличие переменных среды в следующем порядке и использует первый найденный путь:</span><span class="sxs-lookup"><span data-stu-id="e508b-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="e508b-114">На платформах Windows:</span><span class="sxs-lookup"><span data-stu-id="e508b-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="e508b-115">Путь, заданный переменной среды TMP.</span><span class="sxs-lookup"><span data-stu-id="e508b-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="e508b-116">Путь, заданный переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="e508b-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="e508b-117">Путь, заданный переменной среды USERPROFILE.</span><span class="sxs-lookup"><span data-stu-id="e508b-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="e508b-118">Каталог Windows.</span><span class="sxs-lookup"><span data-stu-id="e508b-118">The Windows directory.</span></span>

- <span data-ttu-id="e508b-119">На платформах, отличных от Windows: использует путь, заданный переменной среды TMPDIR.</span><span class="sxs-lookup"><span data-stu-id="e508b-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="e508b-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="e508b-120">EXAMPLES</span></span>

### <span data-ttu-id="e508b-121">Пример 1. Создание временного файла</span><span class="sxs-lookup"><span data-stu-id="e508b-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="e508b-122">Эта команда создает `.tmp` файл во временной папке, а затем сохраняет ссылку на файл в `$TempFile` переменной.</span><span class="sxs-lookup"><span data-stu-id="e508b-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="e508b-123">Этот файл можно использовать позже в скрипте.</span><span class="sxs-lookup"><span data-stu-id="e508b-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="e508b-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e508b-124">PARAMETERS</span></span>

### <span data-ttu-id="e508b-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e508b-125">-Confirm</span></span>

<span data-ttu-id="e508b-126">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e508b-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e508b-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e508b-127">-WhatIf</span></span>

<span data-ttu-id="e508b-128">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e508b-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e508b-129">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e508b-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e508b-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e508b-130">CommonParameters</span></span>

<span data-ttu-id="e508b-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e508b-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e508b-132">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e508b-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e508b-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e508b-133">INPUTS</span></span>

## <span data-ttu-id="e508b-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e508b-134">OUTPUTS</span></span>

### <span data-ttu-id="e508b-135">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="e508b-135">System.IO.FileInfo</span></span>

<span data-ttu-id="e508b-136">Этот командлет возвращает объект **FileInfo** , представляющий временный файл.</span><span class="sxs-lookup"><span data-stu-id="e508b-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="e508b-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e508b-137">NOTES</span></span>

## <span data-ttu-id="e508b-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e508b-138">RELATED LINKS</span></span>
