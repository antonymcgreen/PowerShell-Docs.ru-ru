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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083201"
---
# <a name="placing-comment-based-help-in-functions"></a>Размещение справки на основе комментариев в функциях

В этом разделе объясняется, где разместить основанной на комментариях справку для функции, чтобы `Get-Help` командлет связывает раздел справки на основе комментариев с соответствующей функции.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Размещение основанной на комментариях справку для функции

- В начале тела функции.

- В конце тела функции.

- Прежде чем `Function` ключевое слово. Если функция является в скрипте или модуль сценария, не может быть более чем одну пустую строку между последней строки справки на основе комментариев и `Function` ключевое слово. В противном случае `Get-Help` связывает справки с помощью сценария, но не функции.

## <a name="examples-of-help-placement-in-a-function"></a>Примеры размещения Help в функции

 Ниже приведены примеры каждой из трех размещения для основанной на комментариях справку для функции.

### <a name="help-at-the-beginning-of-a-function-body"></a>Помочь в начале тела функции

 В следующем примере показано основе комментариев в начале тела функции.

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

### <a name="help-at-the-end-of-a-function-body"></a>Помочь в конце тела функции

 В следующем примере показано, основанной на комментариях в конце тела функции.

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

 В следующих примерах показано основе комментариев в строке до ключевого слова function.

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```