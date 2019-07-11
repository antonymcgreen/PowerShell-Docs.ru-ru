---
title: Определение методов по умолчанию для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fe744a-485f-4c21-9623-1cb546372211
caps.latest.revision: 9
ms.openlocfilehash: af554cde5e888f2a008028010332caa473151622
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733981"
---
# <a name="defining-default-methods-for-objects"></a>Определение методов по умолчанию для объектов

При расширении объекты .NET Framework, можно добавить код методов и методов скриптов к объектам. XML, который используется для определения этих методов описан в следующих разделах.

> [!NOTE]
> В следующих разделах относятся, например из типов файла Types.ps1xml в каталоге установки Windows PowerShell (`$pshome`).

## <a name="code-methods"></a>Методы кода

Метод код ссылается на статический метод объекта .NET Framework.

В следующем примере **ConvertLargeIntegerToInt64** добавляется метод [System.Xml.Xmlnode? Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode) типа. [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) элемент определяет расширенный метод как метод код. [Имя](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) элемент задает имя расширенного метода. И [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) элемент указывает статический метод. (Можно также добавить [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) элемент членам [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) элемент.)

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodemethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>Методы сценариев

Метод скрипт определяет метод, значение которого является результатом выполнения скрипта. В следующем примере **ConvertToDateTime** добавляется метод [System.Management.Managementobject? Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject) типа. [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) элемент определяет расширенный метод как метод скрипта. [Имя](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) элемент задает имя расширенного метода. И [скрипт](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) элемент указывает сценарий, который создает значение метода. (Можно также добавить [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) элемент членам [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) элемент.)

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
