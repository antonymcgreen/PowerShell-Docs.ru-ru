---
title: Основные понятия отчетов об ошибках | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.openlocfilehash: ff010bbe1a87daa351ec13ed249ffc899781a8c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774513"
---
# <a name="error-reporting-concepts"></a>Основные понятия, связанные с отчетами об ошибках

Windows PowerShell предоставляет два механизма для создания отчетов об ошибках: один механизм для *завершения ошибок* и другой механизм *неустранимых ошибок*. Для правильной работы командлета необходимо правильно сообщать об ошибках, чтобы ведущее приложение, выполняющее командлеты, мог реагировать соответствующим образом.

Командлет должен вызвать метод [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) при возникновении ошибки, которая не позволяет командлету продолжить обработку своих входных объектов. Командлет должен вызвать метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) для сообщения об устранимых ошибках, когда командлет может продолжить обработку входных объектов. Оба метода предоставляют запись об ошибке, которую ведущее приложение может использовать для исследования причины ошибки.

Используйте следующие рекомендации, чтобы определить, является ли ошибка завершающей или устранимой ошибкой.

- Ошибка является завершающей ошибкой, если она не позволяет командлету продолжить обработку текущего объекта или успешно обработать все последующие входные объекты, независимо от их содержимого.

- Ошибка является завершающей ошибкой, если не нужно, чтобы командлет продолжал обрабатывать текущий объект или любые последующие входные объекты, независимо от их содержимого.

- Ошибка — это завершающая ошибка, если она возникает в командлете, который не принимает или не возвращает объект, или если он происходит в командлете, который принимает или возвращает только один объект.

- Ошибка — это Неустранимая ошибка, если необходимо, чтобы командлет продолжал обрабатывать текущий объект и все последующие входные объекты.

- Ошибка — это Неустранимая ошибка, если она связана с определенным входным объектом или подмножеством входных объектов.

## <a name="see-also"></a>См. также

[System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
