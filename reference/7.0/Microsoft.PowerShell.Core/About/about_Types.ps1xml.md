---
description: Объясняется, как использовать `Types.ps1xml` файлы для расширения типов объектов, используемых в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_`Types.ps1xml`?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: c2b5cb2e0b97b31ee584baf743cb33c1c9b61ccd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231874"
---
# <a name="about-typesps1xml"></a>Сведения о Types.ps1XML

## <a name="short-description"></a>Краткое описание
Объясняется, как использовать `Types.ps1xml` файлы для расширения типов объектов, используемых в PowerShell.

## <a name="long-description"></a>Подробное описание

Расширенные данные типа определяют дополнительные свойства и методы ("члены") типов объектов в PowerShell. Существует два способа добавления данных расширенного типа в сеанс PowerShell.

- `Types.ps1xml` файл: XML-файл, определяющий Расширенные данные типа.
- `Update-TypeData`: Командлет, который перезагружает `Types.ps1xml` файлы и определяет Расширенные данные для типов в текущем сеансе.

В этом разделе описываются `Types.ps1xml` файлы. Дополнительные сведения об использовании `Update-TypeData` командлета для добавления динамических данных расширенного типа в текущий сеанс см. в разделе [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).

## <a name="about-extended-type-data"></a>Сведения о расширенных типах данных

Расширенные данные типа определяют дополнительные свойства и методы ("члены") типов объектов в PowerShell. Можно расширить любой тип, поддерживаемый PowerShell, и использовать добавленные свойства и методы так же, как и свойства, определенные для типов объектов.

Например, PowerShell добавляет свойство **DateTime** во все `System.DateTime` объекты, например те, которые `Get-Date` возвращает командлет.

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

Свойство **DateTime** не будет найдено в описании структуры [System. DateTime](/dotnet/api/system.datetime) , так как PowerShell добавляет свойство, и оно видимо только в PowerShell.

PowerShell внутренне определяет набор расширенных типов по умолчанию. Эти сведения о типе загружаются в каждом сеансе PowerShell при запуске. Свойство **DateTime** является частью этого набора по умолчанию. До выхода версии PowerShell 6 определения типов сохраняли `Types.ps1xml` файл в каталоге установки PowerShell ( `$PSHOME` ).

## <a name="adding-extended-type-data-to-powershell"></a>Добавление данных расширенного типа в PowerShell

В сеансах PowerShell есть три источника данных расширенного типа.

- Объект, определенный PowerShell и автоматически загружаемый в каждый сеанс PowerShell. Начиная с PowerShell 6, эта информация компилируется в PowerShell и больше не отправляется в `Types.ps1xml` файл.

- `Types.ps1xml`Файлы, экспортируемые модулями, загружаются при импорте модуля в текущий сеанс.

- Данные расширенного типа, определенные с помощью `Update-TypeData` командлета, добавляются только в текущий сеанс. Он не сохраняется в файле.

В сеансе данные расширенного типа из трех источников применяются к объектам одинаковым образом и доступны для всех объектов указанных типов.

## <a name="the-typedata-cmdlets"></a>Командлеты TypeData

Следующие командлеты включены в модуль **Microsoft. PowerShell. Utility** в PowerShell 3,0 и более поздних версиях.

- `Get-TypeData`: Получает данные расширенного типа в текущем сеансе.
- `Update-TypeData`: Перезагружает `Types.ps1xml` файлы. Добавляет данные расширенного типа в текущий сеанс.
- `Remove-TypeData`: Удаляет данные расширенного типа из текущего сеанса.

Дополнительные сведения об этих командлетах см. в разделе справки для каждого командлета.

## <a name="built-in-typesps1xml-files"></a>Встроенные Types.ps1XML-файлы

`Types.ps1xml`Файлы в `$PSHOME` каталоге добавляются в каждый сеанс автоматически.

`Types.ps1xml`Файл в каталоге установки PowerShell ( `$PSHOME` ) является текстовым файлом на основе XML, который позволяет добавлять свойства и методы в объекты, используемые в PowerShell. В PowerShell есть встроенные `Types.ps1xml` файлы, которые добавляют несколько элементов в типы .NET, но `Types.ps1xml` для дальнейшего расширения типов можно создать дополнительные файлы.

Например, по умолчанию объекты Array ( `System.Array` ) имеют свойство **length** , которое содержит количество объектов в массиве. Однако, поскольку **Длина** имени не содержит четкого описания свойства, PowerShell добавляет свойство Alias с именем **Count** , которое отображает то же значение. Следующий XML-код добавляет свойство **Count** к `System.Array` типу.

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

Чтобы получить новый **AliasProperty** , используйте `Get-Member` команду в любом массиве, как показано в следующем примере.

```powershell
Get-Member -InputObject (1,2,3,4)
```

Команда возвращает следующие результаты.

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

В результате вы можете использовать свойство **Count** либо свойство **length** массивов в PowerShell. Пример:

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a>Создание новых Types.ps1XML-файлов

`.ps1xml`Файлы, устанавливаемые с помощью PowerShell, имеют цифровую подпись, чтобы предотвратить незаконное изменение, так как форматирование может включать блоки сценариев. Поэтому, чтобы добавить свойство или метод в тип .NET, создайте собственные `Types.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.

Чтобы создать новый файл, начните с копирования существующего `Types.ps1xml` файла. Новый файл может иметь любое имя, но он должен иметь `.ps1xml` расширение имени файла. Новый файл можно поместить в любой каталог, доступный для PowerShell, но он удобен для размещения файлов в каталоге установки PowerShell () или в подкаталоге `$PSHOME` каталога установки.

После сохранения нового файла используйте `Update-TypeData` командлет, чтобы добавить новый файл в сеанс PowerShell. Если вы хотите, чтобы типы применялись к определенным встроенным типам, используйте параметр **препенддата** `Update-TypeData` командлета. `Update-TypeData` влияет только на текущий сеанс. Чтобы внести изменения во все будущие сеансы, экспортируйте консоль или добавьте `Update-TypeData` команду в профиль PowerShell.

## <a name="typesps1xml-and-add-member"></a>Types.ps1XML и Add-Member

`Types.ps1xml`Файлы добавляют свойства и методы ко всем экземплярам объектов указанного типа .NET в затронутом сеансе PowerShell. Однако если необходимо добавить свойства или методы только в один экземпляр объекта, используйте `Add-Member` командлет.

Дополнительные сведения см. в разделе [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a>Пример. Добавление элемента Age в объекты FileInfo

В этом примере показано, как добавить свойство **Age** в объекты **System. IO. FileInfo** . Возраст файла — это разница между временем создания и текущим временем в днях.

Так как свойство **Age** вычисляется с помощью блока скрипта, найдите `<ScriptProperty>` тег, который будет использоваться в качестве модели для нового свойства **Age** .

Сохраните следующий XML-код в файле `$PSHOME\MyTypes.ps1xml` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

Выполните команду `Update-TypeData` , чтобы добавить новый `Types.ps1xml` файл в текущий сеанс. Команда использует параметр **препенддата** для размещения нового файла в порядке очередности выше исходных определений.

Дополнительные сведения о `Update-TypeData` см. в разделе [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

Чтобы проверить изменение, выполните команду, `Get-ChildItem` чтобы получить файл PowerShell.exe в `$PSHOME` каталоге, а затем передайте файл в `Format-List` командлет, чтобы вывести список всех свойств файла. В результате изменения в списке появится свойство **Age** .

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a>XML-файлы в Types.ps1XML-файлах

Полное определение схемы можно найти в файле [types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) в репозитории исходного кода PowerShell на сайте GitHub.

`<Types>`Тег включает все типы, определенные в файле. Должен быть только один `<Types>` тег.

Каждый тип .NET, упомянутый в файле, должен быть представлен `<Type>` тегом.

Теги типа должны содержать следующие Теги:

`<Name>`: Заключает имя затронутого типа .NET.

`<Members>`: Заключает теги для новых свойств и методов, определенных для типа .NET.

Любой из следующих тегов элементов может находиться внутри `<Members>` тега.

`<AliasProperty>`: Определяет новое имя для существующего свойства.

`<AliasProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<ReferencedMemberName>` тег, указывающий существующее свойство.

Например, свойство псевдонима **Count** является псевдонимом для свойства **length** объектов Array.

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

`<CodeMethod>`: Ссылается на статический метод класса .NET.

`<CodeMethod>`Тег должен иметь `<Name>` тег, указывающий имя нового метода и `<GetCodeReference>` тег, указывающий код, в котором определен метод.

Например, свойство **mode** `System.IO.DirectoryInfo` объектов — это свойство Code, определенное в поставщике файловой системы PowerShell.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<CodeProperty>`: Ссылается на статический метод класса .NET.

`<CodeProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<GetCodeReference>` тег, указывающий код, в котором определено свойство.

Например, свойство **mode** `System.IO.DirectoryInfo` объектов — это свойство Code, определенное в поставщике файловой системы PowerShell.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<MemberSet>`: Определяет коллекцию элементов (свойства и методы).

`<MemberSet>`Теги отображаются в первичных `<Members>` тегах. Теги должны заключать `<Name>` тег в окружающее имя набора элементов и дополнительный `<Members>` тег, охватывающий элементы (свойства и методы) в наборе. Любой из тегов, которые создают свойство (например, `<NoteProperty>` или `<ScriptProperty>` ) или метод (например, `<Method>` или), `<ScriptMethod>` может быть членом набора.

В `Types.ps1xml` файлах `<MemberSet>` тег используется для определения представлений по умолчанию для объектов .NET в PowerShell. В этом случае имя набора элементов (значение в `<Name>` тегах) всегда равно **псстандардмемберс** , а имена свойств (значение `<Name>` тега) являются одним из следующих:

- `DefaultDisplayProperty`: Отдельное свойство объекта.

- `DefaultDisplayPropertySet`: Одно или несколько свойств объекта.

- `DefaultKeyPropertySet`: Одно или несколько ключевых свойств объекта. Ключевое свойство определяет экземпляры значений свойств, такие как ИДЕНТИФИКАТОРы элементов в журнале сеанса.

Например, следующий XML-код определяет отображение служб (объектов) по умолчанию `System.ServiceProcess.ServiceController` , возвращаемое `Get-Service` командлетом. Он определяет набор элементов с именем **псстандардмемберс** , который состоит из набора свойств по умолчанию со свойствами **Status** , **Name** и **DisplayName** .

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
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<Method>`: Ссылается на собственный метод базового объекта.

`<Methods>`: Коллекция методов объекта.

`<NoteProperty>`: Определяет свойство со статическим значением.

`<NoteProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<Value>` тег, указывающий значение свойства.

Например, следующий XML-код создает свойство **Status** для объектов **System. IO. DirectoryInfo** . Значение свойства **Status** всегда равно **Success** .

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

`<ParameterizedProperty>`: Свойства, принимающие аргументы и возвращающие значение.

`<Properties>`: Коллекция свойств объекта.

`<Property>`: Свойство базового объекта.

`<PropertySet>`: Определяет коллекцию свойств объекта.

`<PropertySet>`Тег должен иметь `<Name>` тег, указывающий имя набора свойств, и `<ReferencedProperty>` тег, указывающий свойства. Имена свойств заключаются в `<Name>` тег.

В `Types.ps1xml` `<PropertySet>` теги используются для определения наборов свойств для отображаемого по умолчанию объекта. Можно задать отображение по умолчанию по значению **псстандардмемберс** в `<Name>` теге `<MemberSet>` тега.

Например, следующий XML-код создает свойство **Status** для `System.IO.DirectoryInfo` объекта. Значение свойства **Status** всегда равно **Success** .

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
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<ScriptMethod>`: Определяет метод, значение которого является выходным значением скрипта.

`<ScriptMethod>`Тег должен иметь `<Name>` тег, указывающий имя нового метода и `<Script>` тег, который заключает в себя блок скрипта, который возвращает результат метода.

Например, `ConvertToDateTime` `ConvertFromDateTime` методы и объектов управления ( `System.System.Management.ManagementObject` ) являются методами скриптов, которые используют `ToDateTime` `ToDmtfDateTime` статические методы `System.Management.ManagementDateTimeConverter` класса.

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
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

`<ScriptProperty>`: Определяет свойство, значение которого является выходным значением скрипта.

`<ScriptProperty>`Тег должен иметь `<Name>` тег, указывающий имя нового свойства и `<GetScriptBlock>` тег, который заключает в себя блок скрипта, возвращающий значение свойства.

Например, свойство **versionInfo** объекта **System. IO. FileInfo** представляет собой свойство скрипта, полученное в результате использования свойства **FullName** статического метода **жетверсионинфо** объектов **System. Diagnostics. FileVersionInfo** .

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

Дополнительные сведения см. в разделе [пакет средств разработки программного обеспечения Windows PowerShell (SDK)](/powershell/scripting/developer/windows-powershell).

## <a name="update-typedata"></a>Update-TypeData

Чтобы загрузить `Types.ps1xml` файлы в сеанс PowerShell, выполните `Update-TypeData` командлет. Если требуется, чтобы типы в файле применялись к типам во встроенном `Types.ps1xml` файле, добавьте параметр **препенддата** из `Update-TypeData` . `Update-TypeData` влияет только на текущий сеанс. Чтобы внести изменения во все будущие сеансы, экспортируйте сеанс или добавьте `Update-TypeData` команду в профиль PowerShell.

Исключения, возникающие в свойствах или при добавлении свойств в `Update-TypeData` команду, не сообщают об ошибках `StdErr` . Это необходимо для подавления исключений, которые могут возникнуть во многих распространенных типах в процессе форматирования и вывода. Если вы получаете свойства .NET, подавление исключений можно обойти с помощью синтаксиса метода, как показано в следующем примере:

```powershell
"hello".get_Length()
```

Обратите внимание, что синтаксис метода можно использовать только со свойствами .NET. Свойства, которые добавляются путем запуска `Update-TypeData` командлета, не могут использовать синтаксис метода.

## <a name="signing-a-typesps1xml-file"></a>Подписывание Types.ps1XML-файла

Чтобы защитить пользователей `Types.ps1xml` файла, можно подписать файл с помощью цифровой подписи. Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).

## <a name="see-also"></a>См. также статью

[about_Signing](about_Signing.md)

[Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)

[Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Get-TypeData](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[Remove-TypeData](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData)
