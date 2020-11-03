---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 406675d8bde1b6b9a28913c09d5374393705f93b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229357"
---
# <span data-ttu-id="21991-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="21991-103">New-TemporaryFile</span></span>

## <span data-ttu-id="21991-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="21991-104">SYNOPSIS</span></span>
<span data-ttu-id="21991-105">Создает временный файл.</span><span class="sxs-lookup"><span data-stu-id="21991-105">Creates a temporary file.</span></span>

## <span data-ttu-id="21991-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21991-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="21991-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21991-107">DESCRIPTION</span></span>

<span data-ttu-id="21991-108">Этот командлет создает временные файлы, которые можно использовать в скриптах.</span><span class="sxs-lookup"><span data-stu-id="21991-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="21991-109">`New-TemporaryFile`Командлет создает пустой файл с `.tmp` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="21991-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="21991-110">Этот командлет называет файл `tmp<NNNN>.tmp` , где `<NNNN>` — случайное шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="21991-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="21991-111">Командлет создает файл во **временной** папке.</span><span class="sxs-lookup"><span data-stu-id="21991-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="21991-112">Этот командлет использует метод [path. жеттемппас ()](/dotnet/api/system.io.path.gettemppath) для поиска **временной** папки.</span><span class="sxs-lookup"><span data-stu-id="21991-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="21991-113">Этот метод проверяет наличие переменных среды в следующем порядке и использует первый найденный путь:</span><span class="sxs-lookup"><span data-stu-id="21991-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="21991-114">На платформах Windows:</span><span class="sxs-lookup"><span data-stu-id="21991-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="21991-115">Путь, заданный переменной среды TMP.</span><span class="sxs-lookup"><span data-stu-id="21991-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="21991-116">Путь, заданный переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="21991-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="21991-117">Путь, заданный переменной среды USERPROFILE.</span><span class="sxs-lookup"><span data-stu-id="21991-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="21991-118">Каталог Windows.</span><span class="sxs-lookup"><span data-stu-id="21991-118">The Windows directory.</span></span>

- <span data-ttu-id="21991-119">На платформах, отличных от Windows: использует путь, заданный переменной среды TMPDIR.</span><span class="sxs-lookup"><span data-stu-id="21991-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="21991-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="21991-120">EXAMPLES</span></span>

### <span data-ttu-id="21991-121">Пример 1. Создание временного файла</span><span class="sxs-lookup"><span data-stu-id="21991-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="21991-122">Эта команда создает `.tmp` файл во временной папке, а затем сохраняет ссылку на файл в `$TempFile` переменной.</span><span class="sxs-lookup"><span data-stu-id="21991-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="21991-123">Этот файл можно использовать позже в скрипте.</span><span class="sxs-lookup"><span data-stu-id="21991-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="21991-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21991-124">PARAMETERS</span></span>

### <span data-ttu-id="21991-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="21991-125">-Confirm</span></span>

<span data-ttu-id="21991-126">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="21991-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="21991-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="21991-127">-WhatIf</span></span>

<span data-ttu-id="21991-128">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="21991-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="21991-129">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="21991-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="21991-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="21991-130">CommonParameters</span></span>

<span data-ttu-id="21991-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21991-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21991-132">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="21991-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="21991-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="21991-133">INPUTS</span></span>

## <span data-ttu-id="21991-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="21991-134">OUTPUTS</span></span>

### <span data-ttu-id="21991-135">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="21991-135">System.IO.FileInfo</span></span>

<span data-ttu-id="21991-136">Этот командлет возвращает объект **FileInfo** , представляющий временный файл.</span><span class="sxs-lookup"><span data-stu-id="21991-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="21991-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="21991-137">NOTES</span></span>

## <span data-ttu-id="21991-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="21991-138">RELATED LINKS</span></span>

