---
title: Размещение справки на основе комментариев в функциях | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367783"
---
# <a name="placing-comment-based-help-in-functions"></a>Размещение справки на основе комментариев в функциях

В этом разделе объясняется, куда поместить справку на основе комментариев для функции, чтобы командлет `Get-Help` свяжет раздел справки на основе комментариев с правильной функцией.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Размещение справки на основе комментариев для функции

- В начале тела функции.

- В конце тела функции.

- Перед ключевым словом `Function`. Если функция находится в сценарии или модуле скрипта, между последней строкой справки на основе комментариев и ключевым словом `Function` не может быть больше одной пустой строки. В противном случае `Get-Help` связывает справку со сценарием, а не с функцией.

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