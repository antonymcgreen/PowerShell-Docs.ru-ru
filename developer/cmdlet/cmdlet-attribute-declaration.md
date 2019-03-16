---
title: Объявление атрибута командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlet attribute, described
- attributes, Cmdlet
- Cmdlet attribute
ms.assetid: 1d323332-f773-4c0e-8a69-2aada765afb2
caps.latest.revision: 12
ms.openlocfilehash: 6887467ad5ccafe6edf8f03f531b4750133aa9e9
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058034"
---
# <a name="cmdlet-attribute-declaration"></a>Объявление атрибута командлета

Атрибут командлета определяет класс Microsoft .NET Framework как командлет и указывает глагол и существительное, используемый для вызова командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a>Параметры

`VerbName` ([System.String](/dotnet/api/System.String)) требуется. Указывает команду, командлет. Эта команда задает действие, выполняемое с помощью командлета. Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md) и [необходимые рекомендации по разработке](./required-development-guidelines.md).

`NounName` ([System.String](/dotnet/api/System.String)) требуется. Означает существительные командлета. Это существительное указывает ресурс, который обрабатывает командлет. Дополнительные сведения о существительные командлета, см. в разделе [объявление командлет](./cmdlet-class-declaration.md) и [строго настоятельные рекомендации по разработке](./strongly-encouraged-development-guidelines.md).

`SupportsShouldProcess` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. `True` Указывает, что командлет поддерживает вызовы [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод, который предоставляет возможность запрашивать пользователя, прежде чем будет выполнено действие, которое изменений в системе командлет. `False`, значение по умолчанию, указывает, что командлет не поддерживает вызовы [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод. Дополнительные сведения о запросах подтверждения, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

`ConfirmImpact` ([System.Management.Automation.Confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) необязательный именованный параметр. Указывает, когда действие командлета следует подтвердить с помощью вызова [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод. [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) будет вызываться только при значении ConfirmImpact командлета (по умолчанию — Medium) равным или больше, чем значение `$ConfirmPreference` переменной. Этот параметр должен быть указан только тогда, когда `SupportsShouldProcess` указан параметр.

`DefaultParameterSetName` ([System.String](/dotnet/api/System.String)) необязательный именованный параметр. Указывает, что для параметра по умолчанию установлено, что среда выполнения Windows PowerShell пытается использовать, когда не удается определить, какой набор параметров следует использовать. Обратите внимание на то, что такой ситуации можно избежать путем внесения параметр unique командлета каждого параметра задать обязательный параметр.

Есть один случай, где параметр по умолчанию, устанавливать, даже если указано имя набора параметров по умолчанию нельзя использовать Windows PowerShell. Среда выполнения Windows PowerShell не различает наборов параметров, исходя исключительно из типа объекта. Например, если у вас есть один набор параметров, который принимает строку как путь к файлу и другой набор принимает **FileInfo** объекта непосредственно, Windows PowerShell не может определить, какой параметр, настроенный для использования на основе значений передается командлет, и не использует набор параметров по умолчанию. Таким образом даже если указать имя набора параметров по умолчанию, Windows PowerShell выдает сообщение об ошибке неоднозначный параметр set.

`SupportsTransactions` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. `True` Указывает, что командлет может использоваться в рамках транзакции. Когда `True` указан, то среда выполнения Windows PowerShell добавляет `UseTransaction` параметра к списку параметров командлета. `False`, значение по умолчанию, указывает, что командлет не может использоваться в рамках транзакции.

## <a name="remarks"></a>Замечания

- Вместе глагол и существительное, используются для идентификации зарегистрированных командлета и позволяет вызывать командлет в сценариях.

- Если командлет вызывается из консоли Windows PowerShell, команда имеет вид следующую команду:

**VerbName NounName**

- Все командлеты, изменяющих ресурсы за пределы Windows PowerShell должна включать `SupportsShouldProcess` ключевое слово при объявлении атрибута командлет, который позволяет командлету вызвать [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод прежде, чем командлет выполняет его действие. Если [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов возвращает `false`, действие не должно приниматься. Дополнительные сведения о запросах подтверждения при [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывать, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).

`Confirm` И `WhatIf` параметры командлета, доступны только для командлетов, которые поддерживают [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызовов.

## <a name="example"></a>Пример

Следующее определение класса использует атрибут командлета для идентификации класса .NET Framework для **Get-Proc** командлет, извлекающий сведения о процессах, запущенных на локальном компьютере.

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

Дополнительные сведения о **Get-Proc** командлета, см. в разделе [GetProc руководстве](./getproc-tutorial.md).

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
