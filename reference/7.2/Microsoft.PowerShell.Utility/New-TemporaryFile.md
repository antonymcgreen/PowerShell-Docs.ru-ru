---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 1c66cd3b1cc2fccc58cd75c367b41c445deb1e72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600176"
---
# <span data-ttu-id="5eeb7-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="5eeb7-102">New-TemporaryFile</span></span>

## <span data-ttu-id="5eeb7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5eeb7-103">SYNOPSIS</span></span>
<span data-ttu-id="5eeb7-104">Создает временный файл.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-104">Creates a temporary file.</span></span>

## <span data-ttu-id="5eeb7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5eeb7-105">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5eeb7-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5eeb7-106">DESCRIPTION</span></span>

<span data-ttu-id="5eeb7-107">Этот командлет создает временные файлы, которые можно использовать в скриптах.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-107">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="5eeb7-108">`New-TemporaryFile`Командлет создает пустой файл с `.tmp` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-108">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="5eeb7-109">Этот командлет называет файл `tmp<NNNN>.tmp` , где `<NNNN>` — случайное шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-109">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="5eeb7-110">Командлет создает файл во **временной** папке.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-110">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="5eeb7-111">Этот командлет использует метод [path. жеттемппас ()](/dotnet/api/system.io.path.gettemppath) для поиска **временной** папки.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-111">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="5eeb7-112">Этот метод проверяет наличие переменных среды в следующем порядке и использует первый найденный путь:</span><span class="sxs-lookup"><span data-stu-id="5eeb7-112">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="5eeb7-113">На платформах Windows:</span><span class="sxs-lookup"><span data-stu-id="5eeb7-113">On Windows platforms:</span></span>

  1. <span data-ttu-id="5eeb7-114">Путь, заданный переменной среды TMP.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-114">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="5eeb7-115">Путь, заданный переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-115">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="5eeb7-116">Путь, заданный переменной среды USERPROFILE.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-116">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="5eeb7-117">Каталог Windows.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-117">The Windows directory.</span></span>

- <span data-ttu-id="5eeb7-118">На платформах, отличных от Windows: использует путь, заданный переменной среды TMPDIR.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-118">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="5eeb7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="5eeb7-119">EXAMPLES</span></span>

### <span data-ttu-id="5eeb7-120">Пример 1. Создание временного файла</span><span class="sxs-lookup"><span data-stu-id="5eeb7-120">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="5eeb7-121">Эта команда создает `.tmp` файл во временной папке, а затем сохраняет ссылку на файл в `$TempFile` переменной.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-121">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="5eeb7-122">Этот файл можно использовать позже в скрипте.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-122">You can use this file later in your script.</span></span>

## <span data-ttu-id="5eeb7-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5eeb7-123">PARAMETERS</span></span>

### <span data-ttu-id="5eeb7-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5eeb7-124">-Confirm</span></span>

<span data-ttu-id="5eeb7-125">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5eeb7-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5eeb7-126">-WhatIf</span></span>

<span data-ttu-id="5eeb7-127">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5eeb7-128">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5eeb7-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5eeb7-129">CommonParameters</span></span>

<span data-ttu-id="5eeb7-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5eeb7-131">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5eeb7-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5eeb7-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5eeb7-132">INPUTS</span></span>

## <span data-ttu-id="5eeb7-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5eeb7-133">OUTPUTS</span></span>

### <span data-ttu-id="5eeb7-134">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="5eeb7-134">System.IO.FileInfo</span></span>

<span data-ttu-id="5eeb7-135">Этот командлет возвращает объект **FileInfo** , представляющий временный файл.</span><span class="sxs-lookup"><span data-stu-id="5eeb7-135">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="5eeb7-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5eeb7-136">NOTES</span></span>

## <span data-ttu-id="5eeb7-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5eeb7-137">RELATED LINKS</span></span>

