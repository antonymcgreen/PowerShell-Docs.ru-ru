---
title: Основные понятия отчетов об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: 2f185e415e3effc2cf09a282ca1167e3bcfb7d6a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364623"
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

## <a name="see-also"></a>См. также:

[System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
