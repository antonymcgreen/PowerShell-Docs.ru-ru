---
ms.date: 09/13/2016
ms.topic: reference
title: Непрерывающие ошибки
description: Непрерывающие ошибки
ms.openlocfilehash: d23642103e005c6d3a6168b317b11f40001b6bbe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655739"
---
# <a name="non-terminating-errors"></a>Непрерывающие ошибки

В этом разделе обсуждается метод, используемый для сообщения об устранимых ошибках. В нем также обсуждается вызов метода из командлета.

При возникновении неустранимой ошибки командлет должен сообщить об этой ошибке, вызвав метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) . Когда командлет сообщает о неустранимой ошибке, командлет может продолжить работу с этим входным объектом и дальнейшими входящими объектами конвейера. Если командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , командлет может записать запись об ошибке, описывающую условие, вызвавшее неустранимую ошибку. Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

Командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) в соответствии с их методами обработки ввода. Однако командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) только из потока, который вызвал метод обработки входных данных [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)Management. Automation. командлет. ProcessRecord или [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Не вызывайте [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока. Вместо этого следует сообщать об ошибках обратно в основной поток.

## <a name="see-also"></a>См. также:

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
