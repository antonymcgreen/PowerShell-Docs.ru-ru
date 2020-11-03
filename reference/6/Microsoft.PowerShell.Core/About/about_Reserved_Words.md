---
description: Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: 928962b9bf28d95e8c037e9c09e5425ee730b172
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231281"
---
# <a name="about-reserved-words"></a>О зарезервированных словах

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Список зарезервированных слов, которые нельзя использовать в качестве идентификаторов, так как они имеют специальное значение в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

В PowerShell есть определенные слова, имеющие специальное значение. Когда эти слова отображаются без кавычек, PowerShell пытается применить специальное значение вместо того, чтобы рассматривать их как символьные строки. Чтобы использовать эти слова в качестве аргументов параметров в команде или скрипте без вызова их специального значения, заключите зарезервированные слова в кавычки.

Ниже приведены зарезервированные слова в PowerShell.

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

Некоторые ключевые слова языка, включая `Foreach` ,, `If` `For` и `While` , имеют собственные справочные статьи. Чтобы просмотреть их, введите `Get-Help about_` и добавьте ключевое слово. Например, чтобы получить сведения о `Foreach` инструкции, введите:

```powershell
Get-Help about_ForEach
```

Для получения сведений о `Filter` инструкции или `Return` синтаксисе инструкции введите:

```powershell
Get-Help about_Functions
```

Для получения сведений о других зарезервированных словах введите:

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> Не все зарезервированные слова имеют собственную справочную статью. Если не `Get-Help` возвращает статью, можно выполнить поиск статей, которые говорят о зарезервированном слове, с помощью следующей команды:
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Language_Keywords](about_Language_Keywords.md)
- [about_Parsing](about_Parsing.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Special_Characters](about_Special_Characters.md)
