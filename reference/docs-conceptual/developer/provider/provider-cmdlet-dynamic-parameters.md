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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359953"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Поставщики могут определять динамические параметры, добавляемые в командлет поставщика, когда пользователь указывает определенное значение для одного из статических параметров командлета. Например, поставщик может добавить различные динамические параметры в зависимости от того, какой путь указан пользователем при вызове командлетов поставщика `Get-Item` или `Set-Item`.

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

`Clear-Content` командлет можно определить динамические параметры, активируемые параметром `Path` командлета Clear-Clear, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. клеарконтентдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) .

`Clear-Item` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Clear-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. клеаритемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) .

`Clear-ItemProperty` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Clear-ItemProperty`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. клеарпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) .

`Copy-Item` командлет можно определить динамические параметры, активируемые параметрами `Path`, `Destination`и `Recurse` командлета `Copy-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. копитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) .

Командлет Get-Чилдитемс. можно определить динамические параметры, активируемые `Path` и `Recurse` параметры командлета `Get-ChildItem`, реализовав методы [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемсдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) и [System. Management. Automation. Provider. контаинеркмдлетпровидер. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) .

`Get-Content` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Get-Content`, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) .

`Get-Item` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Get-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. жетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) .

`Get-ItemProperty` командлет можно определить динамические параметры, активируемые `Path` и `Name` параметрами командлета `Get-ItemProperty`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. жетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) .

`Invoke-Item` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Invoke-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

`Move-Item` командлет можно определить динамические параметры, активируемые `Path` и `Destination` параметрами командлета `Move-Item`, реализовав метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) .

`New-Item` командлет можно определить динамические параметры, активируемые параметрами `Path`, `ItemType`и `Value` командлета `New-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. невитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) .

`New-ItemProperty` командлет можно определить динамические параметры, активируемые параметрами `Path`, `Name`, `PropertyType`и `Value` командлета `New-ItemProperty`, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. невпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) .

`New-PSDrive` командлет можно определить динамические параметры, активируемые объектом [System. Management. Automation. PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , возвращаемым командлетом `New-PSDrive`, путем реализации метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .

`Remove-Item` можно определить динамические параметры, активируемые `Path` и `Recurse` параметрами командлета `Remove-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ремовеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) .

`Remove-ItemProperty` можно определить динамические параметры, активируемые `Path` и `Name` параметрами командлета `Remove-ItemProperty`, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ремовепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) .

`Rename-Item` командлет можно определить динамические параметры, активируемые `Path` и `NewName` параметрами командлета `Rename-Item`, реализовав метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. ренамеитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) .

`Rename-ItemProperty` можно определить динамические параметры, активируемые параметрами `Path`, `Name`и `NewName` командлета `Rename-ItemProperty`, реализовав метод [System. Management. Automation. Provider. идинамикпропертикмдлетпровидер. ренамепропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) .

`Set-Content` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Set-Content`, реализовав метод [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентвритердинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) .

`Set-Item` командлет можно определить динамические параметры, активируемые `Path` и `Value` параметрами командлета `Set-Item`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитемдинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) .

`Set-ItemProperty` командлет можно определить динамические параметры, активируемые `Path` и `Value` параметрами командлета `Set-Item`, реализовав метод [System. Management. Automation. Provider. ипропертикмдлетпровидер. сетпропертидинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) .

`Test-Path` командлет можно определить динамические параметры, активируемые параметром `Path` командлета `Test-Path`, реализовав метод [System. Management. Automation. Provider. итемкмдлетпровидер. инвокедефаултактиондинамикпараметерс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) .

## <a name="see-also"></a>См. также:

[Написание поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)