---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-member?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Member
ms.openlocfilehash: 290d19cb2bf04e22bf7855cb88467ed26ad42fe7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227646"
---
# Get-Member

## Краткий обзор
Получает свойства и методы объектов.

## SYNTAX

```
Get-Member [-InputObject <PSObject>] [[-Name] <String[]>] [-MemberType <PSMemberTypes>]
 [-View <PSMemberViewTypes>] [-Static] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`Get-Member`Командлет получает элементы, свойства и методы объектов.

Чтобы указать объект, используйте параметр **InputObject** или передайте объект в `Get-Member` . Чтобы получить сведения о статических членах, члены класса, а не экземпляра, используют **статический** параметр. Чтобы получить только определенные типы членов, например **нотепропертиес** , используйте параметр **MemberType** .

## Примеры

### Пример 1. Получение элементов объектов Process

Эта команда отображает свойства и методы объектов службы, создаваемых `Get-Service` командлетом.

Поскольку `Get-Member` часть команды не имеет параметров, она использует значения по умолчанию для параметров. По умолчанию не `Get-Member` получает статические или встроенные члены.

```powershell
Get-Service | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, System.EventArgs)
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(type requestedType)
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.ServiceControllerSt...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] DependentServices {get;}
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle ServiceHandle {get;}
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] ServicesDependedOn {get;}
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType {get;}
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartType {get;}
Status                    Property      System.ServiceProcess.ServiceControllerStatus Status {get;}
ToString                  ScriptMethod  System.Object ToString();
```

### Пример 2. Получение элементов объектов службы

В этом примере возвращаются все элементы (свойства и методы) объектов служб, полученных с помощью `Get-Service` командлета, включая внутренние элементы, такие как **PSBase** , **PSObject** , а также методы **get_** и **set_** .

```powershell
Get-Service | Get-Member -Force
(Get-Service Schedule).PSBase
```

`Get-Member`Команда использует параметр **Force** для добавления внутренних членов и созданных компилятором членов объектов к отображению. Эти свойства и методы можно использовать так же, как и адаптированный метод объекта. Вторая команда показывает, как отображать значение свойства PSBase службы Schedule.

### Пример 3. получение расширенных элементов объектов службы

Этот пример получает методы и свойства объектов службы, которые были расширены с помощью `Types.ps1xml` файла или `Add-Member` командлета.

```powershell
Get-Service | Get-Member -View Extended
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name             MemberType    Definition
----             ----------    ----------
Name             AliasProperty Name = ServiceName
RequiredServices AliasProperty RequiredServices = ServicesDependedOn
ToString         ScriptMethod  System.Object ToString();
```

`Get-Member`Команда использует параметр **View** для получения только расширенных элементов объектов службы. В этом случае расширенный член является свойством **Name** , которое является свойством Alias свойства **ServiceName** .

### Пример 4. получение свойств скрипта объектов журнала событий

Этот пример возвращает свойства скриптов объектов журнала событий в системном журнале в Просмотр событий.

```powershell
Get-WinEvent -LogName System -MaxEvents 1 | Get-Member -MemberType NoteProperty
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.EventLogRecord

Name    MemberType   Definition
----    ----------   ----------
Message NoteProperty string Message=The machine-default permission settings do not grant Local ...
```

Параметр **MemberType** возвращает только объекты со значением `NoteProperty` свойства **MemberType** .

Команда возвращает свойство **Message** объекта **EventLogRecord** .

### Пример 5. Получение объектов с указанным свойством

Этот пример получает объекты со свойством **MachineName** в выходных данных из списка командлетов.

`$list`Переменная содержит список командлетов для оценки. Оператор **foreach** вызывает каждую команду и отправляет результаты в `Get-Member` . Параметр **Name** ограничивает результаты от `Get-Member` до элементов, имеющих имя **MachineName**.

```powershell
$list = "Get-Process", "Get-Service", "Get-Culture", "Get-PSDrive", "Get-ExecutionPolicy"
foreach ($cmdlet in $list) {& $cmdlet | Get-Member -Name MachineName}
```

```Output
   TypeName: System.Diagnostics.Process

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;}

   TypeName: System.ServiceProcess.ServiceController

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;set;}
```

Результаты показывают, что только объекты обработки и объекты службы имеют свойство **MachineName** .

### Пример 6. Получение элементов для массива

В этом примере показано, как найти элементы массива объектов. При передаче по конвейеру и массиву объектов `Get-Member` командлет возвращает список элементов для каждого уникального типа объекта в массиве.
При передаче массива с помощью параметра **InputObject** массив обрабатывается как один объект.

```powershell
$array = @(1,'hello')
$array | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType Definition
----        ---------- ----------
CompareTo   Method     int CompareTo(System.Object value), int CompareTo(int value), int ICompar...
Equals      Method     bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int...
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
GetTypeCode Method     System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method     bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method     byte IConvertible.ToByte(System.IFormatProvider provider)
...

   TypeName: System.String

Name                 MemberType            Definition
----                 ----------            ----------
Clone                Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo            Method                int CompareTo(System.Object value), int CompareTo(str...
Contains             Method                bool Contains(string value), bool Contains(string val...
CopyTo               Method                void CopyTo(int sourceIndex, char[] destination, int ...
EndsWith             Method                bool EndsWith(string value), bool EndsWith(string val...
EnumerateRunes       Method                System.Text.StringRuneEnumerator EnumerateRunes()
Equals               Method                bool Equals(System.Object obj), bool Equals(string va...
GetEnumerator        Method                System.CharEnumerator GetEnumerator(), System.Collect...
GetHashCode          Method                int GetHashCode(), int GetHashCode(System.StringCompa...
...
```

```powershell
Get-Member -InputObject $array
```

```Output
   TypeName: System.Object[]

Name           MemberType            Definition
----           ----------            ----------
Add            Method                int IList.Add(System.Object value)
Address        Method                System.Object&, System.Private.CoreLib, Version=4.0.0.0, Cu...
Clear          Method                void IList.Clear()
Clone          Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo      Method                int IStructuralComparable.CompareTo(System.Object other, Sy...
...
```

`$array`Переменная содержит объект **Int32** и **строковый** объект, как показано при перенаправлении массива `Get-Member` . При `$array` передаче с помощью параметра **InputObject** `Get-Member` возвращает элементы типа **Object []** .

### Пример 7. Определение свойств объектов, которые можно задать

В этом примере показано, как определить, какое из свойств объекта можно изменить.

```powershell
$File = Get-Item c:\test\textFile.txt
$File.PSObject.Properties | Where-Object isSettable | Select-Object -Property Name
```

```Output
Name
----
PSPath
PSParentPath
PSChildName
PSDrive
PSProvider
PSIsContainer
IsReadOnly
CreationTime
CreationTimeUtc
LastAccessTime
LastAccessTimeUtc
LastWriteTime
LastWriteTimeUtc
Attributes
```

## PARAMETERS

### -Force

Добавляет в отображение внутренние элементы и созданные компилятором **get_** и **set_** методы.
В следующем списке описываются свойства, которые добавляются при использовании параметра **Force** :

- **PSBase** : исходные свойства объекта .NET без расширения или адаптации. Это свойства, определенные для класса Object.
- **Псадаптед**. Свойства и методы, определенные в системе расширенного типа PowerShell.
- **Псекстендед**. Свойства и методы, которые были добавлены в `Types.ps1xml` файлы или с помощью `Add-Member` командлета.
- **PSObject**. Адаптер, преобразующий базовый объект в объект PowerShell **PSObject** .
- **PSTypeNames**. Список типов объектов, описывающих объект, в порядке специфичности. При форматировании объекта PowerShell ищет типы в `Format.ps1xml` файлах в каталоге установки PowerShell ( `$PSHOME` ). Определение форматирования используется для первого найденного типа.

По умолчанию `Get-Member` получает эти свойства во всех представлениях, за исключением **базового** и **адаптированного** , но не отображает их.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объект с полученными членами.

Использование параметра **InputObject** не совпадает с параметрами передачи объекта по конвейеру `Get-Member` . Различия заключаются в следующем.

- При передаче коллекции объектов в объект `Get-Member` `Get-Member` получает элементы отдельных объектов в коллекции, например свойства каждой строки в массиве строк.
- При использовании **InputObject** для отправки коллекции объектов `Get-Member` получает элементы коллекции, такие как свойства массива в массиве строк.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberType

Указывает тип элемента, который получает этот командлет. Значение по умолчанию — **All**.

Допустимые значения для этого параметра:

- AliasProperty
- CodeProperty
- Свойство
- NoteProperty
- ScriptProperty
- Свойства
- PropertySet
- Метод
- CodeMethod
- ScriptMethod
- Методы
- ParameterizedProperty
- MemberSet
- Событие
- Динамический
- Все

Дополнительные сведения об этих значениях см. в разделе [Псмембертипес enumeration](/dotnet/api/system.management.automation.psmembertypes).

Не у всех объектов имеются члены всех типов. При указании типа элемента, который отсутствует в объекте, PowerShell возвращает значение null.

Чтобы получить связанные типы членов, например все расширенные элементы, используйте параметр **View**. При использовании параметра **MemberType** со **статическими** или параметрами **представления** `Get-Member` получает элементы, принадлежащие обоим наборам.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имя одного или нескольких свойств или методов объекта. `Get-Member` Возвращает только указанные свойства и методы.

При использовании параметра **Name** с параметром **MemberType** , **View** или **static** `Get-Member` получает только те элементы, которые удовлетворяют критериям всех параметров.

Чтобы получить статический элемент по имени, используйте **статический** параметр с параметром **Name** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Static

Указывает, что этот командлет получает только статические свойства и методы объекта. Статические свойства и методы определяются по классу объекта, а не по отдельному экземпляру класса.

При использовании **статического** параметра с параметром **View** параметр **View** игнорируется.
При использовании **статического** параметра с параметром **MemberType** `Get-Member` возвращает только те элементы, которые принадлежат к обоим наборам.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -View

Указывает, что этот командлет получает только свойства и методы определенных типов. Укажите одно или несколько значений. Значение по умолчанию — **адаптированное** , **Расширенное**.

Допустимые значения для этого параметра:

- База. Возвращает только исходные свойства и методы объекта .NET (без расширения или адаптации).
- Адаптировать. Возвращает только свойства и методы, определенные в системе расширенного типа PowerShell.
- Расширенных. Возвращает только свойства и методы, которые были добавлены в `Types.ps1xml` файлы или с помощью `Add-Member` командлета.
- Все. Получает элементы представлений Base, Adapted и Extended.

Параметр **View** определяет извлекаемые элементы, а не только отображение этих элементов.

Чтобы получить определенные типы элементов, например свойства скриптов, используйте параметр **MemberType** . Если вы используете параметры **MemberType** и **View** в одной команде, `Get-Member` получает элементы, принадлежащие обоим наборам. Если в одной команде используются параметры **static** и **View** , параметр **View** игнорируется.

```yaml
Type: System.Management.Automation.PSMemberViewTypes
Parameter Sets: (All)
Aliases:
Accepted values: Extended, Adapted, Base, All

Required: False
Position: Named
Default value: Adapted, Extended
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в `Get-Member` .

## Выходные данные

### Microsoft. PowerShell. Commands. MemberDefinition

`Get-Member` Возвращает объект для каждого свойства или метода, который получает.

## ПРИМЕЧАНИЯ

Сведения об объекте коллекции можно получить с помощью параметра **InputObject** или путем передачи объекта перед запятой в `Get-Member` .

В `$This` блоках сценариев можно использовать автоматическую переменную, определяющую значения новых свойств и методов. `$This`Переменная ссылается на экземпляр объекта, к которому добавляются свойства и методы. Дополнительные сведения о `$This` переменной см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Если передать объект, представляющий _тип_ , например литерал типа, такой как `[int]` , `Get-Member` возвращают сведения о `[System.RuntimeType]` типе. Однако при использовании **статического** параметра `Get-Member` возвращает статические члены конкретного типа, представленного `System.RuntimeType` экземпляром.

## Связанные ссылки

[Add-Member](Add-Member.md)
