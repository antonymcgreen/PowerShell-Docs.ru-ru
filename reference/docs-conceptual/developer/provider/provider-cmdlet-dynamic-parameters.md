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
ms.openlocfilehash: 9e70fbeaef61d04e66f16d06519742ff2f679df6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564246"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Поставщики могут определять динамические параметры, добавляемые в командлет поставщика, когда пользователь указывает определенное значение для одного из статических параметров командлета. Например, поставщик может добавить различные динамические параметры в зависимости от того, какой путь пользователь указывает при вызове `Get-Item` `Set-Item` командлетов или.

## <a name="dynamic-parameter-methods"></a>Методы динамических параметров

Динамические параметры определяются путем реализации одного из методов динамического параметра, таких как методы [System. Management. автоматизации. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s. Эти методы возвращают объект, который имеет открытые свойства, имеющие атрибуты, аналогичные атрибутам изолированных командлетов. Ниже приведен пример реализации метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) , взятого из поставщика сертификатов:

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

`Clear-Content`Командлет можно определить динамические параметры, активируемые `Path` параметром командлета Clear-Clear, реализовав метод [System. Management. Automation. Provider. Иконтенткмдлетпровидер. клеарконтентдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

`Clear-Item`Командлет можно определить динамические параметры, активируемые `Path` параметром `Clear-Item` командлета, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

`Clear-ItemProperty`Командлет можно определить динамические параметры, активируемые `Path` параметром `Clear-ItemProperty` командлета, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

`Copy-Item`Командлет можно определить динамические параметры, активируемые `Path` `Destination` параметрами, и `Recurse` `Copy-Item` командлетом, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

Командлет Get-Чилдитемс. Вы можете определить динамические параметры, активируемые `Path` `Recurse` параметрами и `Get-ChildItem` командлетом, реализуя методы [System. Management. автоматизации. Provider. контаинеркмдлетпровидер. жетчилдитемсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) .

`Get-Content`Командлет можно определить динамические параметры, активируемые `Path` параметром `Get-Content` командлета, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) .

`Get-Item`Командлет можно определить динамические параметры, активируемые `Path` параметром `Get-Item` командлета, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

`Get-ItemProperty`Командлет можно определить динамические параметры, активируемые `Path` `Name` параметрами и `Get-ItemProperty` командлетом, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

`Invoke-Item`Командлет можно определить динамические параметры, активируемые `Path` параметром `Invoke-Item` командлета, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

`Move-Item`Командлет можно определить динамические параметры, активируемые `Path` `Destination` параметрами и `Move-Item` командлетом, путем реализации метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) .

`New-Item`Командлет можно определить динамические параметры, активируемые `Path` `ItemType` параметрами, и `Value` `New-Item` командлетом, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. невитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) .

`New-ItemProperty`Командлет можно определить динамические параметры, активируемые `Path` `Name` `PropertyType` параметрами командлета,, и, `Value` `New-ItemProperty` путем реализации метода [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

`New-PSDrive`Командлет можно определить динамические параметры, активируемые объектом [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , возвращаемым `New-PSDrive` командлетом, путем реализации метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

`Remove-Item`Можно определить динамические параметры, активируемые `Path` `Recurse` параметрами и `Remove-Item` командлета, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

`Remove-ItemProperty`Можно определить динамические параметры, активируемые `Path` `Name` параметрами и `Remove-ItemProperty` командлета, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ремовепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

`Rename-Item`Командлет можно определить динамические параметры, активируемые `Path` `NewName` параметрами и `Rename-Item` командлетом, путем реализации метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

`Rename-ItemProperty`Можно определить динамические параметры, активируемые `Path` `Name` `NewName` параметрами командлета, и, `Rename-ItemProperty` реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

`Set-Content`Командлет можно определить динамические параметры, активируемые `Path` параметром `Set-Content` командлета, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) .

`Set-Item`Командлет можно определить динамические параметры, активируемые `Path` `Value` параметрами и `Set-Item` командлетом, путем реализации метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

`Set-ItemProperty`Командлет можно определить динамические параметры, активируемые `Path` `Value` параметрами и `Set-Item` командлетом, путем реализации метода [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

`Test-Path`Командлет можно определить динамические параметры, активируемые `Path` параметром `Test-Path` командлета, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

## <a name="see-also"></a>См. также:

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)
