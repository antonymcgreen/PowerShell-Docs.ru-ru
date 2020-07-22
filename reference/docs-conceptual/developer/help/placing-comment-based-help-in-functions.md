---
title: Размещение справки на основе комментариев в функциях
ms.date: 09/12/2016
ms.openlocfilehash: c7a8f8db6c71fa2ef12aaa4df0f78815626ec8d6
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893209"
---
# <a name="placing-comment-based-help-in-functions"></a>Размещение справки на основе комментариев в функциях

В этом разделе объясняется, куда поместить справку на основе комментариев для функции, чтобы командлет привязывает `Get-Help` раздел справки на основе комментариев с правильной функцией.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Размещение справки на основе комментариев для функции

- В начале тела функции.

- В конце тела функции.

- Перед `Function` ключевым словом. Если функция находится в сценарии или модуле скрипта, между последней строкой справки на основе комментариев и ключевым словом не может быть больше одной пустой строки `Function` . В противном случае `Get-Help` связывает справку со сценарием, а не с функцией.

## <a name="examples-of-help-placement-in-a-function"></a>Примеры размещения справки в функции

В следующих примерах показаны все три параметра размещения для справки на основе комментариев для функции.

### <a name="help-at-the-beginning-of-a-function-body"></a>Справка в начале тела функции

В следующем примере показано, как на основе комментариев в начале тела функции.

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a>Справка в конце тела функции

 В следующем примере показано, как комментарии основаны на комментариях в конце тела функции.

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a>Справка перед ключевым словом функции

 В следующих примерах показаны комментарии на основе строки перед ключевым словом function.

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
