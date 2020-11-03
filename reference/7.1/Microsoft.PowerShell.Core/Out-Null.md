---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: ff70c7dd5314fd1f123299e8f4ed14c70c7d7c9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229374"
---
# <span data-ttu-id="2fbb3-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="2fbb3-103">Out-Null</span></span>

## <span data-ttu-id="2fbb3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2fbb3-104">SYNOPSIS</span></span>
<span data-ttu-id="2fbb3-105">Скрывает выходные данные вместо отправки их в конвейер или отображения.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="2fbb3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2fbb3-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="2fbb3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fbb3-107">DESCRIPTION</span></span>

<span data-ttu-id="2fbb3-108">Командлет **out-NULL** отправляет свои выходные данные в значение null, фактически удаляя его из конвейера и предотвращая Отображение выходных данных на экране.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="2fbb3-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="2fbb3-109">EXAMPLES</span></span>

### <span data-ttu-id="2fbb3-110">Пример 1. Удаление выходных данных</span><span class="sxs-lookup"><span data-stu-id="2fbb3-110">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="2fbb3-111">Эта команда возвращает элементы в текущем расположении или каталоге, но выходные данные не передаются через конвейер и не отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-111">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="2fbb3-112">Это полезно для скрытия выходных данных, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-112">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="2fbb3-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2fbb3-113">PARAMETERS</span></span>

### <span data-ttu-id="2fbb3-114">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2fbb3-114">-InputObject</span></span>

<span data-ttu-id="2fbb3-115">Указывает объект, который будет отправлен в NULL (удален из конвейера).</span><span class="sxs-lookup"><span data-stu-id="2fbb3-115">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="2fbb3-116">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-116">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2fbb3-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2fbb3-117">CommonParameters</span></span>

<span data-ttu-id="2fbb3-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2fbb3-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2fbb3-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2fbb3-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2fbb3-120">INPUTS</span></span>

### <span data-ttu-id="2fbb3-121">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="2fbb3-121">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2fbb3-122">В этот командлет можно передать по конвейеру любой объект.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-122">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="2fbb3-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2fbb3-123">OUTPUTS</span></span>

### <span data-ttu-id="2fbb3-124">Нет</span><span class="sxs-lookup"><span data-stu-id="2fbb3-124">None</span></span>

<span data-ttu-id="2fbb3-125">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-125">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2fbb3-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2fbb3-126">NOTES</span></span>

* <span data-ttu-id="2fbb3-127">Командлеты, которые содержат команду **out** (командлеты **out** ), не имеют параметров для имен или путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-127">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="2fbb3-128">Чтобы отправить данные в командлет **out** , используйте оператор конвейера (|), чтобы отправить выходные данные команды PowerShell в командлет.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-128">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="2fbb3-129">Также можно сохранить данные в переменную передать их в командлет с помощью параметра *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="2fbb3-129">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="2fbb3-130">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-130">For more information, see the examples.</span></span>
* <span data-ttu-id="2fbb3-131">**Out-NULL** не возвращает никаких выходных объектов.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-131">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="2fbb3-132">При передаче выходных данных **out-NULL** в командлет Get-Member, **Get-Member** сообщает о том, что объекты не указаны.</span><span class="sxs-lookup"><span data-stu-id="2fbb3-132">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="2fbb3-133">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2fbb3-133">RELATED LINKS</span></span>

[<span data-ttu-id="2fbb3-134">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="2fbb3-134">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="2fbb3-135">Out-Host</span><span class="sxs-lookup"><span data-stu-id="2fbb3-135">Out-Host</span></span>](Out-Host.md)

