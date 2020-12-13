---
ms.date: 08/21/2019
ms.topic: reference
title: Расширение свойств для объектов
description: Расширение свойств для объектов
ms.openlocfilehash: 37803d9fd87319204565c2abde62f269744481b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652893"
---
# <a name="extending-properties-for-objects"></a>Расширение свойств для объектов

При расширении .NET Framework объектов можно добавить свойства псевдонима, свойства кода, свойства примечаний, свойства скрипта и наборы свойств в объекты. XML-код, определяющий эти свойства, описан в следующих разделах.

> [!NOTE]
> Примеры в следующих разделах относятся к файлу типов по умолчанию `Types.ps1xml` в каталоге установки PowerShell ( `$PSHOME` ). Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="alias-properties"></a>Свойства псевдонима

Свойство Alias определяет новое имя для существующего свойства.

В следующем примере свойство **Count** добавляется к типу [System. Array](/dotnet/api/System.Array) . Элемент [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) определяет расширенное свойство как свойство Alias. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает новое имя. И элемент [референцедмембернаме](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) указывает на существующее свойство, на которое ссылается псевдоним. Также можно добавить `AliasProperty` элемент в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a>Свойства кода

Свойство Code ссылается на статическое свойство объекта .NET Framework.

В следующем примере свойство **mode** добавляется к типу [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) . Элемент [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) определяет расширенное свойство как свойство Code. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. И элемент [жеткодереференце](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) определяет статический метод, на который ссылается расширенное свойство. Также можно добавить `CodeProperty` элемент в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a>Запись свойств

Свойство Note определяет свойство, имеющее статическое значение.

В следующем примере свойство **Status** , значение которого всегда равно **Success**, добавляется в тип [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) . Элемент [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) определяет расширенное свойство как свойство Note. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. Элемент [value](/dotnet/api/system.management.automation.psnoteproperty.value) указывает статическое значение расширенного свойства. `NoteProperty`Элемент также можно добавить в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a>Свойства скрипта

Свойство скрипта определяет свойство, значение которого является выходным значением скрипта.

В следующем примере свойство **versionInfo** добавляется в тип [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) . Элемент [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) определяет расширенное свойство как свойство скрипта. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. И элемент [жетскриптблокк](/dotnet/api/system.management.automation.psscriptproperty.getterscript) указывает скрипт, который создает значение свойства. Также можно добавить `ScriptProperty` элемент в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a>Наборы свойств

Набор свойств определяет группу расширенных свойств, на которые может ссылаться имя набора.
Например, параметр свойства [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) 
  может указывать конкретный набор свойств для отображения. Если задан набор свойств, отображаются только те свойства, которые принадлежат набору.

Количество наборов свойств, которые могут быть определены для объекта, не ограничено. Однако наборы свойств, используемые для определения свойств экрана по умолчанию для объекта, должны быть указаны в наборе элементов **псстандардмемберс** . В `Types.ps1xml` файле типов имена наборов свойств по умолчанию включают **дефаултдисплайпроперти**, **дефаултдисплайпропертисет** и **дефаулткэйпропертисет**. Все дополнительные наборы свойств, добавляемые в набор элементов **псстандардмемберс** , игнорируются.

В следующем примере набор свойств **дефаултдисплайпропертисет** добавляется в набор элементов **псстандардмемберс** типа [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . Элемент набора [свойств](/dotnet/api/system.management.automation.pspropertyset) определяет группу свойств. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя набора свойств. И элемент [референцедпропертиес](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) указывает свойства набора. Можно также добавить `PropertySet` элемент в элементы элемента [Type](/dotnet/api/system.management.automation.pstypename) .

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a>См. также раздел

[Сведения о Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[System.Management.Automation](/dotnet/api/System.Management.Automation)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
