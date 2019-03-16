---
title: Расширение свойств для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: 496e363b041194563d46c09eee67a12055bb54b0
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057303"
---
# <a name="extending-properties-for-objects"></a>Расширение свойств для объектов

При расширении объекты .NET Framework, можно добавить псевдоним свойства, свойства кода, свойства примечаний, свойства сценария и наборов свойств к объектам. В следующих разделах описывается XML, который используется для определения этих свойств.

> [!NOTE]
> В следующих разделах относятся, например из файла Types.ps1xml типы по умолчанию в каталоге установки Windows PowerShell (`$pshome`).

## <a name="alias-properties"></a>Свойства псевдонима

Свойства псевдонима определяет новое имя для существующего свойства.

В следующем примере `Count` свойство добавляется к [System.Array? Displayproperty = Fullname](/dotnet/api/System.Array) типа. [AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1) элемент определяет расширенное свойство как свойство псевдонима. [Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент указывает новое имя. И [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a) элемент задает существующее свойство, на который ссылается псевдоним. (Можно также добавить [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)

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

Свойство код ссылается на статическое свойство объекта .NET Framework.

В следующем примере `Node` свойство добавляется к [System.IO.Directoryinfo? Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo) типа. [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) элемент определяет расширенное свойство как свойство кода. [Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства. И [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0) элемент определяет статический метод, который ссылается расширенного свойства. (Можно также добавить [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)

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

## <a name="note-properties"></a>Свойства примечаний

Свойство примечания определяет свойство, которое имеет статическое значение.

В следующем примере `Status` свойства (значение которого всегда является «Успех») добавляется к [System.IO.Directoryinfo? Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo) типа. [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) элемент определяет расширенное свойство как свойство примечания; [имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства; и [значение](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) элемент Задает статическое значение расширенного свойства. ( [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) также можно добавить элемент к членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)

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

## <a name="script-properties"></a>Свойства сценария

Свойство скрипт определяет свойство, значение которого является результатом выполнения скрипта.

В следующем примере `VersionInfo` свойство добавляется к [System.IO.FileInfo? Displayproperty = Fullname](/dotnet/api/System.IO.FileInfo) типа. [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) элемент определяет расширенное свойство как свойство скрипта. [Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства. И [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) элемент указывает сценарий, который создает значение свойства. (Можно также добавить [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)

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

Набор свойств определяется группа расширенные свойства, которые можно ссылаться по имени набора. Например `Property` параметр [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) командлета можно указать значение для отображения конкретного свойства. Если указан набор свойств, отображаются только те свойства, которые принадлежат к набору.

Нет никаких ограничений на количество наборов свойств, которые могут быть определены для объекта. Тем не менее наборов свойств, используемый для определения свойств отображения по умолчанию объекта должно быть указано в наборе элементов PSStandardMembers. В файле Types.ps1xml типы имена набора свойств по умолчанию включают DefaultDisplayProperty DefaultDisplayPropertySet и DefaultKeyPropertySet. Все наборы дополнительные свойства, добавленные в набор элементов PSStandardMembers игнорируются.

В следующем примере добавляется набор свойств DefaultDisplayPropertySet набором элементов PSStandardMembers [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) типа. [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) элемент определяет группу свойств. [Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя набора свойств. И [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786) элемент определяет свойства набора. (Можно также добавить [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) элемент членам [тип](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe) элемент.)

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
