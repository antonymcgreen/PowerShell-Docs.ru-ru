---
title: Определение методов по умолчанию для объектов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 10917de9e897fc1eed362430d63ff5b9cb7e813d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774598"
---
# <a name="defining-default-methods-for-objects"></a>Определение методов по умолчанию для объектов

При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.
XML-код, используемый для определения этих методов, описан в следующих разделах.

> [!NOTE]
> Примеры в следующих разделах взяты из `Types.ps1xml` файла типов в каталоге установки Windows PowerShell ( `$PSHOME` ). Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="code-methods"></a>Методы кода

Метод Code ссылается на статический метод объекта .NET Framework.

В следующем примере метод **ToString** добавляется в тип [узлаSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) . Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода. И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод. Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
