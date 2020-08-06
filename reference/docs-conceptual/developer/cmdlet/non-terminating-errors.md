---
title: Устранимые ошибки | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d74c248e6ef54151400b8060d76524e89d87352c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786566"
---
# <a name="non-terminating-errors"></a>Непрерывающие ошибки

В этом разделе обсуждается метод, используемый для сообщения об устранимых ошибках. В нем также обсуждается вызов метода из командлета.

При возникновении неустранимой ошибки командлет должен сообщить об этой ошибке, вызвав метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) . Когда командлет сообщает о неустранимой ошибке, командлет может продолжить работу с этим входным объектом и дальнейшими входящими объектами конвейера. Если командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , командлет может записать запись об ошибке, описывающую условие, вызвавшее неустранимую ошибку. Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

Командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) в соответствии с их методами обработки ввода. Однако командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) только из потока, который вызвал метод обработки входных данных [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)Management. Automation. командлет. ProcessRecord или [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Не вызывайте [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока. Вместо этого следует сообщать об ошибках обратно в основной поток.

## <a name="see-also"></a>См. также

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
