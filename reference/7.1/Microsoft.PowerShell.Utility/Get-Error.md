---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: c29115a65b46d38039d78b10eee293e6944cede5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227217"
---
# <span data-ttu-id="feeb5-103">Get-Error</span><span class="sxs-lookup"><span data-stu-id="feeb5-103">Get-Error</span></span>

## <span data-ttu-id="feeb5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="feeb5-104">SYNOPSIS</span></span>

<span data-ttu-id="feeb5-105">Возвращает и отображает последние сообщения об ошибках из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="feeb5-105">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="feeb5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="feeb5-106">SYNTAX</span></span>

### <span data-ttu-id="feeb5-107">Новейшие (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="feeb5-107">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="feeb5-108">Ошибка</span><span class="sxs-lookup"><span data-stu-id="feeb5-108">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="feeb5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="feeb5-109">DESCRIPTION</span></span>

<span data-ttu-id="feeb5-110">`Get-Error`Командлет возвращает объект **псекстендедеррор** , представляющий текущие сведения об ошибке из последней ошибки, произошедшей в сеансе.</span><span class="sxs-lookup"><span data-stu-id="feeb5-110">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="feeb5-111">Можно использовать `Get-Error` для вывода указанного числа ошибок, произошедших в текущем сеансе, с помощью **последнего** параметра.</span><span class="sxs-lookup"><span data-stu-id="feeb5-111">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="feeb5-112">`Get-Error`Командлет также получает объекты Error из коллекции, например `$Error` , чтобы отобразить несколько ошибок из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="feeb5-112">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="feeb5-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="feeb5-113">EXAMPLES</span></span>

### <span data-ttu-id="feeb5-114">Пример 1. Получение последних сведений об ошибке</span><span class="sxs-lookup"><span data-stu-id="feeb5-114">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="feeb5-115">В этом примере `Get-Error` отображаются сведения о последней ошибке, произошедшей в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="feeb5-115">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

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

### <span data-ttu-id="feeb5-116">Пример 2. Получение указанного числа сообщений об ошибках, произошедших в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="feeb5-116">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="feeb5-117">В этом примере показано, как использовать `Get-Error` с **новым** параметром.</span><span class="sxs-lookup"><span data-stu-id="feeb5-117">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="feeb5-118">В этом примере **последними** возвращаются сведения о трех последних ошибках, произошедших в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="feeb5-118">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="feeb5-119">Пример 3. Отправка коллекции ошибок для получения подробных сообщений</span><span class="sxs-lookup"><span data-stu-id="feeb5-119">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="feeb5-120">`$Error`Автоматическая переменная содержит массив объектов Error в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="feeb5-120">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="feeb5-121">Для `Get-Error` получения подробных сообщений об ошибках можно направить массив объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="feeb5-121">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="feeb5-122">В этом примере `$Error` передается `Get-Error` командлету.</span><span class="sxs-lookup"><span data-stu-id="feeb5-122">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="feeb5-123">Результат представляет собой список подробных сообщений об ошибках, аналогичный результату примера 1.</span><span class="sxs-lookup"><span data-stu-id="feeb5-123">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="feeb5-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="feeb5-124">PARAMETERS</span></span>

### <span data-ttu-id="feeb5-125">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="feeb5-125">-Newest</span></span>

<span data-ttu-id="feeb5-126">Указывает количество ошибок, которые должны отображаться в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="feeb5-126">Specifies the number of errors to display that have occurred in the current session.</span></span>

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

### <span data-ttu-id="feeb5-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="feeb5-127">-InputObject</span></span>

<span data-ttu-id="feeb5-128">Этот параметр используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="feeb5-128">This parameter is used for pipeline input.</span></span>

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

### <span data-ttu-id="feeb5-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="feeb5-129">CommonParameters</span></span>

<span data-ttu-id="feeb5-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="feeb5-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="feeb5-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="feeb5-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="feeb5-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="feeb5-132">INPUTS</span></span>

### <span data-ttu-id="feeb5-133">PSObject</span><span class="sxs-lookup"><span data-stu-id="feeb5-133">PSObject</span></span>

<span data-ttu-id="feeb5-134">Поддерживает входные данные из любого **PSObject** , но результаты могут различаться, если не задан объект **ерроррекорд** или **Exception** .</span><span class="sxs-lookup"><span data-stu-id="feeb5-134">Supports input from any **PSObject** , but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="feeb5-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="feeb5-135">OUTPUTS</span></span>

### <span data-ttu-id="feeb5-136">System. Management. Automation. Ерроррекорд # Псекстендедеррор</span><span class="sxs-lookup"><span data-stu-id="feeb5-136">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="feeb5-137">Выходные данные в объекте **псекстендедеррор** .</span><span class="sxs-lookup"><span data-stu-id="feeb5-137">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="feeb5-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="feeb5-138">NOTES</span></span>

<span data-ttu-id="feeb5-139">`Get-Error` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="feeb5-139">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="feeb5-140">Например, `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="feeb5-140">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="feeb5-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="feeb5-141">RELATED LINKS</span></span>

[<span data-ttu-id="feeb5-142">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="feeb5-142">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
