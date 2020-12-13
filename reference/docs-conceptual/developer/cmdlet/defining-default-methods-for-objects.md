---
ms.date: 09/13/2016
ms.topic: reference
title: Определение методов по умолчанию для объектов
description: Определение методов по умолчанию для объектов
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355533"
---
# <a name="defining-default-methods-for-objects"></a>Определение методов по умолчанию для объектов

При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.
XML-код, используемый для определения этих методов, описан в следующих разделах.

> [!NOTE]
> Примеры в следующих разделах взяты из `Types.ps1xml` файла типов в каталоге установки Windows PowerShell ( `$PSHOME` ). Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="code-methods"></a>Методы кода

Метод Code ссылается на статический метод объекта .NET Framework.

В следующем примере метод **ToString** добавляется в тип [ узлаSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) . Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода. И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод. Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

Метод скрипта определяет метод, значение которого является выходным значением скрипта. В следующем примере метод **ConvertToDateTime** добавляется в тип [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) . Элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod) определяет расширенный метод как метод скрипта. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода. И элемент [script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) указывает скрипт, который создает значение метода. Можно также добавить элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

## <a name="see-also"></a>См. также раздел

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
