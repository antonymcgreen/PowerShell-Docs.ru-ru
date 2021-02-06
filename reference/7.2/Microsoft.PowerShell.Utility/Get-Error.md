---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 7e4f4adf60a4f6386c646d92ada0003f239f05f4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602290"
---
# <span data-ttu-id="500de-102">Get-Error</span><span class="sxs-lookup"><span data-stu-id="500de-102">Get-Error</span></span>

## <span data-ttu-id="500de-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="500de-103">SYNOPSIS</span></span>

<span data-ttu-id="500de-104">Возвращает и отображает последние сообщения об ошибках из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="500de-104">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="500de-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="500de-105">SYNTAX</span></span>

### <span data-ttu-id="500de-106">Новейшие (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="500de-106">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="500de-107">Ошибка</span><span class="sxs-lookup"><span data-stu-id="500de-107">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="500de-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="500de-108">DESCRIPTION</span></span>

<span data-ttu-id="500de-109">`Get-Error`Командлет возвращает объект **псекстендедеррор** , представляющий текущие сведения об ошибке из последней ошибки, произошедшей в сеансе.</span><span class="sxs-lookup"><span data-stu-id="500de-109">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="500de-110">Можно использовать `Get-Error` для вывода указанного числа ошибок, произошедших в текущем сеансе, с помощью **последнего** параметра.</span><span class="sxs-lookup"><span data-stu-id="500de-110">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="500de-111">`Get-Error`Командлет также получает объекты Error из коллекции, например `$Error` , чтобы отобразить несколько ошибок из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="500de-111">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="500de-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="500de-112">EXAMPLES</span></span>

### <span data-ttu-id="500de-113">Пример 1. Получение последних сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="500de-113">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="500de-114">В этом примере `Get-Error` отображаются сведения о последней ошибке, произошедшей в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="500de-114">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### <span data-ttu-id="500de-115">Пример 2. Получение указанного числа сообщений об ошибках, произошедших в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="500de-115">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="500de-116">В этом примере показано, как использовать `Get-Error` с **новым** параметром.</span><span class="sxs-lookup"><span data-stu-id="500de-116">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="500de-117">В этом примере **последними** возвращаются сведения о трех последних ошибках, произошедших в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="500de-117">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="500de-118">Пример 3. Отправка коллекции ошибок для получения подробных сообщений</span><span class="sxs-lookup"><span data-stu-id="500de-118">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="500de-119">`$Error`Автоматическая переменная содержит массив объектов Error в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="500de-119">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="500de-120">Для `Get-Error` получения подробных сообщений об ошибках можно направить массив объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="500de-120">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="500de-121">В этом примере `$Error` передается `Get-Error` командлету.</span><span class="sxs-lookup"><span data-stu-id="500de-121">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="500de-122">Результат представляет собой список подробных сообщений об ошибках, аналогичный результату примера 1.</span><span class="sxs-lookup"><span data-stu-id="500de-122">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="500de-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="500de-123">PARAMETERS</span></span>

### <span data-ttu-id="500de-124">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="500de-124">-Newest</span></span>

<span data-ttu-id="500de-125">Указывает количество ошибок, которые должны отображаться в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="500de-125">Specifies the number of errors to display that have occurred in the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="500de-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="500de-126">-InputObject</span></span>

<span data-ttu-id="500de-127">Этот параметр используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="500de-127">This parameter is used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="500de-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="500de-128">CommonParameters</span></span>

<span data-ttu-id="500de-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="500de-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="500de-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="500de-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="500de-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="500de-131">INPUTS</span></span>

### <span data-ttu-id="500de-132">PSObject</span><span class="sxs-lookup"><span data-stu-id="500de-132">PSObject</span></span>

<span data-ttu-id="500de-133">Поддерживает входные данные из любого **PSObject**, но результаты могут различаться, если не задан объект **ерроррекорд** или **Exception** .</span><span class="sxs-lookup"><span data-stu-id="500de-133">Supports input from any **PSObject**, but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="500de-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="500de-134">OUTPUTS</span></span>

### <span data-ttu-id="500de-135">System. Management. Automation. Ерроррекорд # Псекстендедеррор</span><span class="sxs-lookup"><span data-stu-id="500de-135">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="500de-136">Выходные данные в объекте **псекстендедеррор** .</span><span class="sxs-lookup"><span data-stu-id="500de-136">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="500de-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="500de-137">NOTES</span></span>

<span data-ttu-id="500de-138">`Get-Error` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="500de-138">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="500de-139">Пример: `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="500de-139">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="500de-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="500de-140">RELATED LINKS</span></span>

[<span data-ttu-id="500de-141">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="500de-141">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
