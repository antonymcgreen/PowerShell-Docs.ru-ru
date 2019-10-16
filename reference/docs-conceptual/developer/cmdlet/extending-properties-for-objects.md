---
title: Расширение свойств объектов | Документация Майкрософт
ms.custom: ''
ms.date: 08/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: 3b14007384cca0d0cfa35655aee437adf73b1ff0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364453"
---
# <a name="extending-properties-for-objects"></a>Расширение свойств для объектов

При расширении .NET Framework объектов можно добавить свойства псевдонима, свойства кода, свойства примечаний, свойства скрипта и наборы свойств в объекты. XML-код, определяющий эти свойства, описан в следующих разделах.

> [!NOTE]
> Примеры в следующих разделах относятся к файлу `Types.ps1xml` типов по умолчанию в каталоге установки PowerShell (`$PSHOME`). Дополнительные сведения см. в разделе [About types. ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="alias-properties"></a>Свойства псевдонима

Свойство Alias определяет новое имя для существующего свойства.

В следующем примере свойство **Count** добавляется к типу [System. Array](/dotnet/api/System.Array) . Элемент [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) определяет расширенное свойство как свойство Alias. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает новое имя. И элемент [референцедмембернаме](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) указывает на существующее свойство, на которое ссылается псевдоним. Можно также добавить элемент `AliasProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

В следующем примере свойство **mode** добавляется к типу [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) . Элемент [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) определяет расширенное свойство как свойство Code. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. И элемент [жеткодереференце](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) определяет статический метод, на который ссылается расширенное свойство. Можно также добавить элемент `CodeProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

## <a name="note-properties"></a>Свойства заметки

Свойство Note определяет свойство, имеющее статическое значение.

В следующем примере свойство **Status** , значение которого всегда равно **Success**, добавляется в тип [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) . Элемент [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) определяет расширенное свойство как свойство Note. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. Элемент [value](/dotnet/api/system.management.automation.psnoteproperty.value) указывает статическое значение расширенного свойства. Элемент `NoteProperty` также можно добавить в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

В следующем примере свойство **versionInfo** добавляется в тип [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) . Элемент [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) определяет расширенное свойство как свойство скрипта. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства. И элемент [жетскриптблокк](/dotnet/api/system.management.automation.psscriptproperty.getterscript) указывает скрипт, который создает значение свойства. Можно также добавить элемент `ScriptProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .

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

Количество наборов свойств, которые могут быть определены для объекта, не ограничено. Однако наборы свойств, используемые для определения свойств экрана по умолчанию для объекта, должны быть указаны в наборе элементов **псстандардмемберс** . В файле типа `Types.ps1xml` имена наборов свойств по умолчанию включают **дефаултдисплайпроперти**, **дефаултдисплайпропертисет**и **дефаулткэйпропертисет**. Все дополнительные наборы свойств, добавляемые в набор элементов **псстандардмемберс** , игнорируются.

В следующем примере набор свойств **дефаултдисплайпропертисет** добавляется в набор элементов **псстандардмемберс** типа [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) . Элемент набора [свойств](/dotnet/api/system.management.automation.pspropertyset) определяет группу свойств. Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя набора свойств. И элемент [референцедпропертиес](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) указывает свойства набора. Можно также добавить элемент `PropertySet` в элементы элемента [Type](/dotnet/api/system.management.automation.pstypename) .

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

## <a name="see-also"></a>См. также статью

[О типах. ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[System. Management. Automation](/dotnet/api/System.Management.Automation)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
