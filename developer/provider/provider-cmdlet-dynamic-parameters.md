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
ms.openlocfilehash: 803fe4ae24a4f8022639c5b6d6298100859177ce
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858360"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Динамические параметры командлета поставщика

Поставщики можно определить динамических параметров, которые добавляются к командлету поставщика, когда пользователь задает определенное значение для одного из статических параметров командлета. Например, поставщик можно добавить различные динамические параметры, основанные на какие пути пользователь указывает, когда они вызывают `Get-Item` или `Set-Item` командлеты поставщика.

## <a name="dynamic-parameter-methods"></a>Методы динамического параметра

Динамические параметры определяются путем реализации одного из методов динамических параметров, таких как [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) и [ System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s методы. Эти методы возвращают объект, который содержит открытые свойства, которые помечены атрибутом с атрибутами, похожие на те автономного командлетов. Ниже приведен пример реализации [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) методом взятое из поставщика сертификата:

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

В отличие от статических параметров поставщика командлетов можно указать характеристики этих параметров так же, что параметры определяются в автономном командлетов. Ниже приведен пример класса динамического параметра, взятое из поставщика сертификата:

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

Ниже приведен список статические параметры, которые могут использоваться для добавления динамических параметров.

`Clear-Content` командлет можно определить динамических параметров, которые активируются `Path` параметр командлета Clear-Clear, реализовав [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters* ](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) метод.

`Clear-Item` командлет можно определить динамических параметров, которые активируются `Path` параметр `Clear-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) метод.

`Clear-ItemProperty` командлет можно определить динамических параметров, которые активируются `Path` параметр `Clear-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) метод.

`Copy-Item` командлет можно определить динамических параметров, которые активируются `Path`, `Destination`, и `Recurse` параметры `Copy-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) метод.

Командлет Get-ChildItems можно определить динамических параметров, которые активируются `Path` и `Recures` параметры `Get-ChildItem` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) и [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) методы.

`Get-Content` командлет можно определить динамических параметров, которые активируются `Path` параметр `Get-Content` командлета путем реализации [ System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) метод.

`Get-Item` командлет можно определить динамических параметров, которые активируются `Path` параметр `Get-Item` командлета путем реализации [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) метод.

`Get-ItemProperty` командлет можно определить динамических параметров, которые активируются `Path` и `Name` параметры `Get-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) метод.

`Invoke-Item` командлет можно определить динамических параметров, которые активируются `Path` параметр `Invoke-Item` командлета путем реализации [ System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) метод.

`Move-Item` командлет можно определить динамических параметров, которые активируются `Path` и `Destination` параметры `Move-Item` командлета путем реализации [ System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) метод.

`New-Item` командлет можно определить динамических параметров, которые активируются `Path`, `ItemType`, и `Value` параметры `New-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) метод.

`New-ItemProperty` командлет можно определить динамических параметров, которые активируются `Path`, `Name`, `PropertyType`, и `Value` параметры `New-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) метод.

`New-PSDrive` командлет можно определить динамических параметров, которые активируются [: System.Management.Automation.Psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) объект, возвращаемый `New-PSDrive` командлета путем реализации [ System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) метод.

`Remove-Item` Можно определить динамических параметров, которые активируются `Path` и `Recurse` параметры `Remove-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) метод.

`Remove-ItemProperty` Можно определить динамических параметров, которые активируются `Path` и `Name` параметры `Remove-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) метод.

`Rename-Item` командлет можно определить динамических параметров, которые активируются `Path` и `NewName` параметры `Rename-Item` командлета путем реализации [ System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) метод.

`Rename-ItemProperty` Можно определить динамических параметров, которые активируются `Path`, `Name`, и `NewName` параметры `Rename-ItemProperty` командлета путем реализации [ System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) метод.

`Set-Content` командлет можно определить динамических параметров, которые активируются `Path` параметр `Set-Content` командлета путем реализации [ System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) метод.

`Set-Item` командлет можно определить динамических параметров, которые активируются `Path` и `Value` параметры `Set-Item` командлета путем реализации [ System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) метод.

`Set-ItemProperty` командлет можно определить динамических параметров, которые активируются `Path` и `Value` параметры `Set-Item` командлета путем реализации [ System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) метод.

`Test-Path` командлет можно определить динамических параметров, которые активируются `Path` параметр `Test-Path` командлета путем реализации [ System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) метод.

## <a name="see-also"></a>См. также

[Разработка поставщика Windows PowerShell](./writing-a-windows-powershell-provider.md)