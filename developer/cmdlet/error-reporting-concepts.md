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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068187"
---
# <a name="error-reporting-concepts"></a>Основные понятия, связанные с отчетами об ошибках

Windows PowerShell предоставляет два механизма для сообщений об ошибках: один механизм для *завершение ошибки* и еще один механизм *устранимые ошибки*. Очень важно для командлета для сообщения об ошибках правильно, чтобы ведущее приложение, на котором выполняется командлетов может реагировать соответствующим образом.

Необходимо вызвать командлет [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) метод при возникновении ошибки, который не поддерживает или не должен разрешать командлет, чтобы продолжить обработку входные объекты. Необходимо вызвать командлет [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод, позволяющий сообщить устранимые ошибки, когда командлет может продолжить обработку входных объектов. Оба метода обеспечивают запись об ошибке, ведущее приложение можно использовать, чтобы установить причину ошибки.

Чтобы определить, является ли ошибка точки в конце или устранимую ошибку, следуйте приведенным ниже рекомендациям.

- Ошибка является неустранимую ошибку, если он предотвращает командлета продолжение для обработки текущего объекта или успешно обрабатывать любые дополнительные входные объекты, независимо от их содержимого.

- Ошибка является неустранимую ошибку, если вы не хотите командлета для продолжения обработки текущего объекта или дальнейшей входных объектов, независимо от их содержимого.

- Ошибка является неустранимую ошибку, если оно присутствует в командлет, который не принимают или возвращают объект, или если оно присутствует в командлет, который принимает или возвращает только один объект.

- Ошибка является неустранимой ошибки, если вы хотите продолжить обработку текущий объект и все дополнительные входные объекты в командлет.

- Ошибка является неустранимой ошибки, если она связана с отдельный входной объект или подмножество входных объектов.

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Записи об ошибках PowerShell Windows](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
