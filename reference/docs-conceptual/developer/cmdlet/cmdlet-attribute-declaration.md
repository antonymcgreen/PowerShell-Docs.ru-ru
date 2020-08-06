---
title: Объявление атрибута командлета | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- Cmdlet attribute, described
- attributes, Cmdlet
- Cmdlet attribute
ms.openlocfilehash: 672609f1f50e4600aebcbb7e6e79bb7353ec867d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774836"
---
# <a name="cmdlet-attribute-declaration"></a>Объявление атрибута командлета

Атрибут командлета определяет класс Microsoft .NET Framework в качестве командлета и указывает глагол и существительное, используемые для вызова командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[Cmdlet("verbName", "nounName")]
[Cmdlet("verbName", "nounName", Named Parameters...)]
```

#### <a name="parameters"></a>Параметры

`VerbName`([System. String](/dotnet/api/System.String)) обязательный. Задает команду командлета. Эта команда задает действие, выполняемое командлетом. Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md) и [необходимые рекомендации по разработке](./required-development-guidelines.md).

`NounName`([System. String](/dotnet/api/System.String)) обязательный. Задает существительное командлет. Это существительное Указывает ресурс, на основе которого работает командлет. Дополнительные сведения о существительных командлетов см. в разделе [объявление командлета](./cmdlet-class-declaration.md) и [рекомендации по разработке настоятельно рекомендуется](./strongly-encouraged-development-guidelines.md).

`SupportsShouldProcess`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. `True`Указывает, что командлет поддерживает вызовы метода [System. Management. Automation. командлета. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , который предоставляет командлету способ запроса пользователя перед действием, которое изменяет систему. `False`значение по умолчанию указывает, что командлет не поддерживает вызовы метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Дополнительные сведения о запросах на подтверждение см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

`ConfirmImpact`([System. Management. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact)) необязательный именованный параметр. Указывает, когда действие командлета должно быть подтверждено вызовом метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) будет вызываться только тогда, когда значение ConfirmImpact командлета (по умолчанию) больше или равно значению `$ConfirmPreference` переменной. Этот параметр должен быть указан только в том случае, если `SupportsShouldProcess` указан параметр.

`DefaultParameterSetName`([System. String](/dotnet/api/System.String)) необязательный именованный параметр. Указывает набор параметров по умолчанию, который среда выполнения Windows PowerShell пытается использовать, если не может определить, какой набор параметров использовать. Обратите внимание, что эту ситуацию можно устранить, сделав уникальный параметр для каждого параметра, устанавливая обязательный параметр.

Существует один случай, когда Windows PowerShell не может использовать набор параметров по умолчанию, даже если задано имя набора параметров по умолчанию. Среда выполнения Windows PowerShell не может отличить наборы параметров только от типа объекта. Например, если имеется один набор параметров, принимающий в качестве пути к файлу строку, и другой набор, который напрямую принимает объект **FileInfo** , Windows PowerShell не может определить, какой набор параметров следует использовать, на основе значений, переданных в командлет, и не использует набор параметров по умолчанию. В этом случае, даже если указать имя набора параметров по умолчанию, Windows PowerShell выдает неоднозначное сообщение об ошибке набора параметров.

`SupportsTransactions`([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. `True`Указывает, что командлет можно использовать в транзакции. Если `True` указан аргумент, среда выполнения Windows PowerShell добавляет `UseTransaction` параметр в список параметров командлета. `False`значение по умолчанию указывает, что командлет нельзя использовать в транзакции.

## <a name="remarks"></a>Примечания

- Вместе команда и существительное используются для задания зарегистрированного командлета и вызова командлета в скрипте.

- При вызове командлета из консоли Windows PowerShell команда напоминает следующую команду:

**Вербнаме — Науннаме**

- Все командлеты, изменяющие ресурсы за пределами Windows PowerShell, должны включать `SupportsShouldProcess` ключевое слово при объявлении атрибута командлета, что позволяет командлету вызвать метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) перед выполнением командлетом действия. Если вызов [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) возвращает `false` , действие не должно выполняться. Дополнительные сведения о запросах подтверждения, создаваемых вызовом [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , см. в разделе [запрос подтверждения](./requesting-confirmation-from-cmdlets.md).

`Confirm` `WhatIf` Параметры командлета и доступны только для командлетов, поддерживающих вызовы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .

## <a name="example"></a>Пример

Следующее определение класса использует атрибут командлета для определения класса .NET Framework для командлета **Get-proc** , который получает сведения о процессах, выполняемых на локальном компьютере.

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

Дополнительные сведения о командлете **Get-proc** см. в [руководстве по процедуре INPROC](./getproc-tutorial.md).

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
