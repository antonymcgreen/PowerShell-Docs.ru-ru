---
title: Параметры командлета динамической | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 2fc73b6ef5a862fafb7a3c8fe3da19ac71bafc05
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853810"
---
# <a name="cmdlet-dynamic-parameters"></a>Динамические параметры командлетов

Командлеты можно определить параметры, доступные для пользователя специальных условиях, например, если аргумент другого параметра конкретное значение. Эти параметры будут добавлены во время выполнения и называются *динамических параметров* так, как они добавляются только в том случае, когда они нужны. Например можно создать командлет, который добавляет несколько параметров, только в том случае, если указан параметр определенного коммутатора.

> [!NOTE]
> Поставщики и функции Windows PowerShell можно также определить динамических параметров.

## <a name="dynamic-parameters-in-windows-powershell-cmdlets"></a>Динамические параметры в командлетах Windows PowerShell

Windows PowerShell использует динамические параметры в некоторых из его командлетов поставщика. Например `Get-Item` и `Get-ChildItem` добавьте командлеты `CodeSigningCert` параметра во время выполнения при `Path` параметр командлета путь поставщика сертификата. Если `Path` параметр командлета указывает путь для другого поставщика, `CodeSigningCert` параметра не поддерживается.

В следующих примерах показывается как `CodeSigningCert` добавлен параметр во время выполнения при `Get-Item` выполнения командлета.

В первом примере среда выполнения Windows PowerShell добавлен параметр, а командлет прошла успешно.

```powershell
Get-Item -Path cert:\CurrentUser -codesigningcert
```

```output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

Во втором примере диск файловой системы указан и возвращается сообщение об ошибке. Сообщение об ошибке указывает, что `CodeSigningCert` параметр не найден.

```powershell
Get-Item -Path C:\ -codesigningcert
```

```output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a>Поддержка динамических параметров

Для поддержки динамических параметров, код командлета должен включать следующие элементы.

[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) этот интерфейс предоставляет метод, который получает динамические параметры.

Пример:

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

[System.Management.Automation.Idynamicparameters.Getdynamicparameters*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) этот метод извлекает объект, который содержит определения динамических параметров.

Пример:

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

Класс динамических параметров в этот класс определяет параметры для добавления. Этот класс должен включать атрибут параметра для каждого параметра и дополнительные атрибуты псевдоним и проверки, которые необходимы с помощью командлета.

Пример:

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

Полный пример, который поддерживает динамические параметры командлета, см. в разделе [как объявить динамических параметров](./how-to-declare-dynamic-parameters.md).

## <a name="see-also"></a>См. также

[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)

[System.Management.Automation.Idynamicparameters.Getdynamicparameters*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Как объявить динамических параметров](./how-to-declare-dynamic-parameters.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
