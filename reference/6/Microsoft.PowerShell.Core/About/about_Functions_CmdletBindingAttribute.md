---
description: Описывает атрибут, который делает функцию функционировать как скомпилированный командлет.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: c4090910a72e2f68b5a710c76b20cc8af532c04b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231461"
---
# <a name="about-functions-cmdletbindingattribute"></a>О функциях Кмдлетбиндингаттрибуте

## <a name="short-description"></a>Краткое описание
Описывает атрибут, который делает функцию функционировать как скомпилированный командлет.

## <a name="long-description"></a>Подробное описание

`CmdletBinding`Атрибут является атрибутом функций, которые делают их работать как скомпилированные командлеты, написанные на языке C#. Он предоставляет доступ к функциям командлетов.

PowerShell привязывает параметры функций, имеющих атрибут, так `CmdletBinding` же, как он привязывает параметры скомпилированных командлетов. `$PSCmdlet`Автоматическая переменная доступна для функций с `CmdletBinding` атрибутом, но `$Args` переменная недоступна.

В функциях, имеющих `CmdletBinding` атрибут, неизвестные параметры и аргументы, которые не имеют соответствующих параметров позиционирования, приводят к сбою привязки параметра.

> [!NOTE]
> Скомпилированные командлеты используют `Cmdlet` атрибут Required, который аналогичен `CmdletBinding` атрибуту, описанному в этом разделе.

## <a name="syntax"></a>Синтаксис

В следующем примере показан формат функции, указывающей все необязательные аргументы `CmdletBinding` атрибута. Ниже приведено краткое описание каждого аргумента.

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a>ConfirmImpact

Аргумент **ConfirmImpact** указывает, когда действие функции должно быть подтверждено вызовом метода **ShouldProcess** . Вызов метода **ShouldProcess** отображает запрос подтверждения, только если аргумент **ConfirmImpact** равен значению `$ConfirmPreference` привилегированной переменной или больше него. (Значение аргумента по умолчанию — **Medium** .) Указывайте этот аргумент только в том случае, если также указан аргумент **SupportsShouldProcess** .

Дополнительные сведения о запросах на подтверждение см. в разделе [запрос подтверждения](/powershell/scripting/developer/cmdlet/requesting-confirmation).

## <a name="defaultparametersetname"></a>DefaultParameterSetName

Аргумент **дефаултпараметерсетнаме** указывает имя набора параметров, который PowerShell будет пытаться использовать, если не сможет определить, какой набор параметров использовать. Эту ошибку можно избежать, сделав уникальный параметр для каждого параметра, устанавливая обязательный параметр.

## <a name="helpuri"></a>HelpURI

Аргумент **HelpURI** указывает Интернет-адрес интерактивной версии раздела справки, описывающего функцию. Значение аргумента **HelpURI** должно начинаться с "http" или "HTTPS".

Значение аргумента **HelpURI** используется для значения свойства **HelpURI** объекта **CommandInfo** , который `Get-Command` возвращает значение для функции.

Однако если файлы справки установлены на компьютере, а значение первой ссылки в разделе **релатедлинкс** файла справки является URI, а значение первой `.Link` директивы в справке на основе комментариев — URI, URI в файле справки используется в качестве значения свойства **HelpUri** для функции.

`Get-Help`Командлет использует значение свойства **HelpURI** , чтобы определить Интернет-версию раздела справки по функции, если в команде указан параметр **Online** `Get-Help` .

## <a name="supportspaging"></a>суппортспагинг

Аргумент **суппортспагинг** добавляет в функцию **первые** параметры, **Skip** и **IncludeTotalCount** . Эти параметры позволяют пользователям выбирать выходные данные из очень большого результирующего набора. Этот аргумент предназначен для командлетов и функций, возвращающих данные из больших хранилищ данных, которые поддерживают выбор данных, например базу данных SQL.

Этот аргумент появился в Windows PowerShell 3,0.

- **First** : возвращает только первые "n" объектов.
- **Пропустить** : пропускает первые объекты "n", а затем получает оставшиеся объекты.
- **IncludeTotalCount** : сообщает количество объектов в наборе данных (целое число), за которыми следуют объекты. Если командлет не может определить общее число, возвращается значение "Неизвестный общий счетчик".

PowerShell включает **невтоталкаунт** — вспомогательный метод, который получает значение общего числа для возврата и включает оценку точности значения общего числа.

В следующем примере функции показано, как добавить поддержку параметров разбиения по страницам в расширенную функцию.

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

Аргумент **SupportsShouldProcess** добавляет в функцию параметры **Confirm** и **WhatIf** . Параметр **Confirm** запрашивает у пользователя перед выполнением команды для каждого объекта в конвейере. Параметр **WhatIf** перечисляет изменения, которые могут быть внесены командой, вместо выполнения команды.

## <a name="positionalbinding"></a>PositionalBinding

Аргумент **поситионалбиндинг** определяет, являются ли параметры в функции позиционированными по умолчанию. Значение по умолчанию — `$True`. **PositionalBinding** `$False` Для отключения позиционированной привязки можно использовать аргумент поситионалбиндинг со значением.

Аргумент **поситионалбиндинг** появился в Windows PowerShell 3,0.

Если параметры являются позиционированными, имя параметра является необязательным.
PowerShell связывает безымянные значения параметров с параметрами функции в соответствии с порядком или позицией неименованных значений параметров в команде Function.

Если параметры не являются позиционированными (они называются "именованными"), в команде требуется имя параметра (или аббревиатура или псевдоним имени).

Если **поситионалбиндинг** имеет значение `$True` , параметры функции по умолчанию являются позиционированными. PowerShell присваивает номера позиций параметрам в том порядке, в котором они объявляются в функции.

Если **поситионалбиндинг** имеет значение `$False` , параметры функции по умолчанию не являются позиционированными. Если в параметре не **объявлен аргумент-** **параметр** , то имя параметра (или псевдоним или аббревиатура) должно быть включено при использовании параметра в функции.

Аргумент **расположения** атрибута **Parameter** имеет приоритет над значением по умолчанию **поситионалбиндинг** . Аргумент « **позиционирование** » можно использовать для указания значения параметра «значение». Дополнительные сведения о аргументе " **Расположение** " см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

## <a name="notes"></a>Примечания

Аргумент **SupportsTransactions** не поддерживается в расширенных функциях.

## <a name="keywords"></a>Keywords

about_Functions_CmdletBinding_Attribute

## <a name="see-also"></a>См. также статью

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
