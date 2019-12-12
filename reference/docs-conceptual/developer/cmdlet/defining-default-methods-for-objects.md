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
ms.openlocfilehash: 346a194c6b4c81aa61a6331cdb62ae380a17bb1e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365693"
---
# <a name="defining-default-methods-for-objects"></a>Определение методов по умолчанию для объектов

При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.
XML-код, используемый для определения этих методов, описан в следующих разделах.

> [!NOTE]
> Примеры в следующих разделах взяты из файла типов `Types.ps1xml` в каталоге установки Windows PowerShell (`$PSHOME`). Дополнительные сведения см. в разделе [About types. ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="code-methods"></a>Методы кода

Метод Code ссылается на статический метод объекта .NET Framework.

В следующем примере метод **ToString** добавляется в тип [System. XML. XMLNode](/dotnet/api/System.Xml.XmlNode) . Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода. И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод. Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>Методы скриптов

Метод скрипта определяет метод, значение которого является выходным значением скрипта. В следующем примере метод **ConvertToDateTime** добавляется в тип [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) . Элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) определяет расширенный метод как метод скрипта. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода. И элемент [script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) указывает скрипт, который создает значение метода. Можно также добавить элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .

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

## <a name="see-also"></a>См. также статью

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
