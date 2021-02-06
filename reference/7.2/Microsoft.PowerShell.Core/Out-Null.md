---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: fe28f52088a82b93799724de7a7a3f20ce42e36b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604106"
---
# <span data-ttu-id="9416a-102">Out-Null</span><span class="sxs-lookup"><span data-stu-id="9416a-102">Out-Null</span></span>

## <span data-ttu-id="9416a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9416a-103">SYNOPSIS</span></span>
<span data-ttu-id="9416a-104">Скрывает выходные данные вместо отправки их в конвейер или отображения.</span><span class="sxs-lookup"><span data-stu-id="9416a-104">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="9416a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9416a-105">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="9416a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9416a-106">DESCRIPTION</span></span>

<span data-ttu-id="9416a-107">Командлет **out-NULL** отправляет свои выходные данные в значение null, фактически удаляя его из конвейера и предотвращая Отображение выходных данных на экране.</span><span class="sxs-lookup"><span data-stu-id="9416a-107">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="9416a-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="9416a-108">EXAMPLES</span></span>

### <span data-ttu-id="9416a-109">Пример 1. Удаление выходных данных</span><span class="sxs-lookup"><span data-stu-id="9416a-109">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="9416a-110">Эта команда возвращает элементы в текущем расположении или каталоге, но выходные данные не передаются через конвейер и не отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9416a-110">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="9416a-111">Это полезно для скрытия выходных данных, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="9416a-111">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="9416a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9416a-112">PARAMETERS</span></span>

### <span data-ttu-id="9416a-113">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9416a-113">-InputObject</span></span>

<span data-ttu-id="9416a-114">Указывает объект, который будет отправлен в NULL (удален из конвейера).</span><span class="sxs-lookup"><span data-stu-id="9416a-114">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="9416a-115">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="9416a-115">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="9416a-116">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9416a-116">CommonParameters</span></span>

<span data-ttu-id="9416a-117">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9416a-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9416a-118">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9416a-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9416a-119">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9416a-119">INPUTS</span></span>

### <span data-ttu-id="9416a-120">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="9416a-120">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="9416a-121">В этот командлет можно передать по конвейеру любой объект.</span><span class="sxs-lookup"><span data-stu-id="9416a-121">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="9416a-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9416a-122">OUTPUTS</span></span>

### <span data-ttu-id="9416a-123">None</span><span class="sxs-lookup"><span data-stu-id="9416a-123">None</span></span>

<span data-ttu-id="9416a-124">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9416a-124">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9416a-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9416a-125">NOTES</span></span>

* <span data-ttu-id="9416a-126">Командлеты, которые содержат команду **out** (командлеты **out** ), не имеют параметров для имен или путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="9416a-126">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="9416a-127">Чтобы отправить данные в командлет **out** , используйте оператор конвейера (|), чтобы отправить выходные данные команды PowerShell в командлет.</span><span class="sxs-lookup"><span data-stu-id="9416a-127">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="9416a-128">Также можно сохранить данные в переменную передать их в командлет с помощью параметра *InputObject*.</span><span class="sxs-lookup"><span data-stu-id="9416a-128">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="9416a-129">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="9416a-129">For more information, see the examples.</span></span>
* <span data-ttu-id="9416a-130">**Out-NULL** не возвращает никаких выходных объектов.</span><span class="sxs-lookup"><span data-stu-id="9416a-130">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="9416a-131">При передаче выходных данных **out-NULL** в командлет Get-Member, **Get-Member** сообщает о том, что объекты не указаны.</span><span class="sxs-lookup"><span data-stu-id="9416a-131">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="9416a-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9416a-132">RELATED LINKS</span></span>

[<span data-ttu-id="9416a-133">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="9416a-133">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="9416a-134">Out-Host</span><span class="sxs-lookup"><span data-stu-id="9416a-134">Out-Host</span></span>](Out-Host.md)

