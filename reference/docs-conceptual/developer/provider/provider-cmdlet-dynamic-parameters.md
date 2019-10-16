---
title: Динамические параметры командлета поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f1069f7-8fa8-4622-9e2c-af29b0b961c2
caps.latest.revision: 6
ms.openlocfilehash: a50de014988336c473c565b506a73de1c864d7e0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359953"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Поставщики могут определять динамические параметры, добавляемые в командлет поставщика, когда пользователь указывает определенное значение для одного из статических параметров командлета. Например, поставщик может добавить различные динамические параметры в зависимости от того, какой путь пользователь указывает при вызове командлетов поставщика `Get-Item` или `Set-Item`.

## <a name="dynamic-parameter-methods"></a>Методы динамических параметров

Динамические параметры определяются путем реализации одного из методов динамического параметра, таких как [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) и [ Методы System. Management. Automation. Provider. Итемкмдлетпровидер. Сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s. Эти методы возвращают объект, который имеет открытые свойства, имеющие атрибуты, аналогичные атрибутам изолированных командлетов. Ниже приведен пример реализации метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) , взятого из поставщика сертификатов:

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

В отличие от статических параметров командлетов поставщика, можно указать характеристики этих параметров таким же образом, как параметры определяются в отдельных командлетах. Ниже приведен пример класса динамических параметров, полученного от поставщика сертификатов.

```csharp
internal sealed class CertificateProviderDynamicParameters
{
  /// <summary>
  /// Dynamic parameter the controls whether we only return
  /// code signing certs.
  /// </summary>
  [Parameter()]
  public SwitchParameter CodeSigningCert
  {
    get
    {
      {
        return codeSigningCert;
      }
    }

    set
    {
      {
        codeSigningCert = value;
      }
    }
  }

    private SwitchParameter codeSigningCert = new SwitchParameter();
}
```

## <a name="dynamic-parameters"></a>Динамические параметры

Ниже приведен список статических параметров, которые можно использовать для добавления динамических параметров.

Командлет `Clear-Content`. можно определить динамические параметры, активируемые параметром `Path` командлета Clear-Clear путем реализации класса [System. Management. Automation. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) Method.

Командлет `Clear-Item`. можно определить динамические параметры, активируемые параметром `Path` командлета `Clear-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

Командлет `Clear-ItemProperty`. Вы можете определить динамические параметры, активируемые параметром `Path` командлета `Clear-ItemProperty`, реализовав метод [System. Management. автоматизации. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) . .

Командлет `Copy-Item`. можно определить динамические параметры, активируемые параметрами `Path`, `Destination` и `Recurse` командлета `Copy-Item`, реализовав [ Метод System. Management. Automation. Provider. Контаинеркмдлетпровидер. Копитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

Командлет Get-Чилдитемс. можно определить динамические параметры, активируемые параметрами `Path` и `Recurse` командлета `Get-ChildItem`, реализовав [ Методы System. Management. Automation. Provider. Контаинеркмдлетпровидер. Жетчилдитемсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) и [System. Management. Automation. Provider. Контаинеркмдлетпровидер. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) .

Командлет `Get-Content`. можно определить динамические параметры, активируемые параметром `Path` командлета `Get-Content` путем реализации класса [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) Method.

Командлет `Get-Item`. можно определить динамические параметры, активируемые параметром `Path` командлета `Get-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

Командлет `Get-ItemProperty`. можно определить динамические параметры, активируемые параметрами `Path` и `Name` командлета `Get-ItemProperty` путем реализации класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс * ](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)метод.

Командлет `Invoke-Item`. можно определить динамические параметры, активируемые параметром `Path` командлета `Invoke-Item` путем реализации класса [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) Method.

Командлет `Move-Item`. можно определить динамические параметры, активируемые параметрами `Path` и `Destination` командлета `Move-Item` путем реализации класса [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс * ](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)метод.

Командлет `New-Item`. можно определить динамические параметры, активируемые параметрами `Path`, `ItemType` и `Value` командлета `New-Item`, реализовав [ Метод System. Management. Automation. Provider. Контаинеркмдлетпровидер. Невитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) .

Командлет `New-ItemProperty`. можно определить динамические параметры, активируемые параметрами `Path`, `Name`, `PropertyType` и `Value` командлета `New-ItemProperty`, реализовав [ Метод System. Management. Automation. Provider. Идинамикпропертикмдлетпровидер. Невпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

Командлет `New-PSDrive`. можно определить динамические параметры, активируемые объектом [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , возвращаемыми командлетом `New-PSDrive`, путем реализации [ Метод System. Management. Automation. Provider. Дривекмдлетпровидер. Невдривединамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

`Remove-Item` можно определить динамические параметры, активируемые параметрами `Path` и `Recurse` командлета `Remove-Item` путем реализации класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) Method.

`Remove-ItemProperty` можно определить динамические параметры, активируемые параметрами `Path` и `Name` командлета `Remove-ItemProperty`, реализовав [ Метод System. Management. Automation. Provider. Идинамикпропертикмдлетпровидер. Ремовепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

Командлет `Rename-Item`. можно определить динамические параметры, активируемые параметрами `Path` и `NewName` командлета `Rename-Item` путем реализации класса [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс * ](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)метод.

`Rename-ItemProperty` можно определить динамические параметры, активируемые параметрами `Path`, `Name` и `NewName` командлета `Rename-ItemProperty`, реализовав [ Метод System. Management. Automation. Provider. Идинамикпропертикмдлетпровидер. Ренамепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

Командлет `Set-Content`. можно определить динамические параметры, активируемые параметром `Path` командлета `Set-Content` путем реализации класса [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) Method.

Командлет `Set-Item`. можно определить динамические параметры, активируемые параметрами `Path` и `Value` командлета `Set-Item` путем реализации класса [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) Method.

Командлет `Set-ItemProperty`. можно определить динамические параметры, активируемые параметрами `Path` и `Value` командлета `Set-Item` путем реализации класса [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс * ](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)метод.

Командлет `Test-Path`. можно определить динамические параметры, активируемые параметром `Path` командлета `Test-Path` путем реализации класса [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) Method.

## <a name="see-also"></a>См. также:

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)