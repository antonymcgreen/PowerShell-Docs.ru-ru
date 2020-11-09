---
title: Добавление поддержки учетных данных в функции PowerShell
description: Узнайте, как добавлять параметры учетных данных в скрипты, функции и командлеты PowerShell.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: 3e4a3f41ccbca1cf97f2e96fd60f22d89be7bc5a
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354632"
---
# <a name="add-credential-support-to-powershell-functions"></a>Добавление поддержки учетных данных в функции PowerShell

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@joshduffney][]. Эта статья была изменена для публикации на этом сайте. Группа разработчиков PowerShell благодарит Джоша (Josh) за то, что он поделился с нами этим содержимым. Посетите его блог [duffney.io][].

В этой статье показано, как и зачем добавлять параметры учетных данных в функции PowerShell. Параметр учетных данных позволяет выполнять функцию или командлет от лица другого пользователя. Чаще всего такая возможность используется для выполнения функции или командлета от лица пользователя с повышенными привилегиями.

Например, командлет `New-ADUser` имеет параметр учетных данных **Credential** , в котором вы можете указать учетные данные администратора домена при создании учетной записи в домене, если ваша обычная учетная запись с запущенным сеансом PowerShell не имеет таких прав.

## <a name="creating-credential-object"></a>Создание объекта учетных данных

Объект [PSCredential][] представляет набор учетных данных для безопасности, таких как имя пользователя и пароль. Объект можно передать в качестве параметра функции, которая выполняется от имени учетной записи пользователя в таком объекте учетных данных. Существует несколько способов создания объекта учетных данных. Первый способ заключается в использовании командлета PowerShell `Get-Credential`. Если запустить его без параметров, отобразится запрос на ввод имени пользователя и пароля. Или же вы можете вызвать командлет с необязательными параметрами.

Чтобы предварительно указать имя домена и имя пользователя, вы можете использовать параметр **Credential** или **UserName**. Если используется параметр **UserName** , вам также необходимо указать значение **Message**. В блоке кода ниже демонстрируется использование этого командлета. Вы также можете сохранить объект учетных данных в переменной для многократного использования учетных данных. В примере ниже объект учетных данных сохраняется в переменной `$Cred`.

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

В некоторых случая вы не сможете воспользоваться интерактивным методом для создания объектов учетных данных, который продемонстрирован в предыдущем примере. Большинство средств автоматизации поддерживают только неинтерактивный метод. Чтобы создать учетные данные без участия пользователя, сначала создайте защищенную строку с паролем. Затем передайте защищенную строку и имя пользователя в метод `System.Management.Automation.PSCredential()`.

Используйте следующую команду, чтобы создать защищенную строку с паролем:

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

Параметры **AsPlainText** и **Force** являются обязательными. Без этих параметров вы получите предупреждение о том, что вам не следует передавать обычный текст в защищенную строку. PowerShell возвращает это предупреждение, так как пароль в формате обычного текста будет записан в разные журналы. После создания защищенной строки вам нужно передать ее в метод `PSCredential()` для создания объекта учетных данных. В следующем примере переменная `$password` содержит защищенную строку `$Cred` с объектом учетных данных.

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

Теперь, когда вы знаете, как создать объект учетных данных, вы можете добавить параметры учетных данных в свои функции PowerShell.

## <a name="adding-a-credential-parameter"></a>Добавление параметра учетных данных

Как и с любым другим параметром, начните с его добавления в блок `param` своей функции.
Рекомендуется присвоить параметру имя `$Credential`, так как это имя используется существующими командлетами PowerShell. Параметр должен иметь тип `[System.Management.Automation.PSCredential]`.

В следующем примере демонстрируется блок параметра для функции с именем `Get-Something`. Она имеет два параметра: `$Name` и `$Credential`.

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

Кода в этом примере достаточно для создания работающего параметра учетных данных, но вы можете добавить несколько элементов, чтобы сделать его более надежным.

- Добавьте атрибут проверки `[ValidateNotNull()]`, чтобы проверить значение, передаваемое параметру **Credential**. Если параметр имеет значение NULL, этот атрибут предотвратит выполнение функции с недопустимыми учетными данными.

- Добавьте `[System.Management.Automation.Credential()]`. Это позволяет передать имя пользователя в формате строки и запросить пароль через интерактивный ввод.

- Задайте для параметра `$Credential` значение по умолчанию `[System.Management.Automation.PSCredential]::Empty`. В вашей функции вы можете передать этот объект `$Credential` существующим командлетам PowerShell. Указание значения NULL для командлета, вызываемого в вашей функции, приведет к ошибке. Указание пустого объекта учетных данных позволяет избежать этой ошибки.

> [!TIP]
> Некоторые командлеты, которые принимают параметр учетных данных, не поддерживают `[System.Management.Automation.PSCredential]::Empty`. Временное решение см. в разделе [Работа с устаревшими командлетами](#dealing-with-legacy-cmdlets).

## <a name="using-credential-parameters"></a>Использование параметров учетных данных

В следующем примере кода показано, как использовать параметры учетных данных. В этом примере демонстрируется функция с именем `Set-RemoteRegistryValue`, которая приведена в книге [The Pester Book][]. Эта функция определяет параметр учетных данных с помощью техник, описанных в предыдущем разделе. Функция вызывает `Invoke-Command` с помощью переменной `$Credential`, создаваемой функцией. Это позволяет вам изменить пользователя, выполняющего `Invoke-Command`. Так как для значения `$Credential` по умолчанию используются пустые учетные данные, функцию можно выполнять без предоставления учетных данных.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

В следующих разделах приведены различные методы по предоставлению учетных данных функции `Set-RemoteRegistryValue`.

### <a name="prompting-for-credentials"></a>Запрос учетных данных

Использование командлета `Get-Credential` в скобках `()` во время выполнения приводит к тому, что командлет `Get-credential` выполняется первым. Появится запрос на ввод имени пользователя и пароль. Вы можете использовать параметр **Credential** или **UserName** командлета `Get-credential`, чтобы указать имя пользователя и домен. В следующем примере используется техника, называемая сплаттинг, для передачи параметров функции `Set-RemoteRegistryValue`. Дополнительные сведения о сплаттинге см. в [этой статье][].

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Получение учетных данных во время выполнения](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

Использование `(Get-Credential)` может сделать код громоздким. Обычно при использовании параметра **Credential** только с именем пользователя командлет автоматически запрашивает пароль. Такое поведение обеспечивается атрибутом `[System.Management.Automation.Credential()]`.

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Запрос учетных данных](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> При задании показанного значения реестра в этих примерах предполагается, что у вас установлены функции **веб-сервера** Windows. Выполните `Install-WindowsFeature Web-Server` и `Install-WindowsFeature web-mgmt-tools` при необходимости.

### <a name="provide-credentials-in-a-variable"></a>Указание учетных данных в переменной

Вы также можете предварительно указать переменную учетных данных и передать ее параметру **Credential** функции `Set-RemoteRegistryValue`. Используйте этот метод с инструментами непрерывной интеграции и непрерывного развертывания (CI/CD), такими как Jenkins, TeamCity и Octopus Deploy. Пример использования Jenkins можно найти в записи блога Hodge [Автоматизация с помощью Jenkins и PowerShell в Windows — часть 2][].

В этом примере используется метод .NET для создания объекта учетных данных и защищенной строки для передачи в пароле.

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

Для этого примера защищенная строка создается с использованием пароля в формате открытого текста. Все упомянутые ранее инструменты CI/CD предоставляют защищенный метод для указания пароля во время выполнения. При использовании таких инструментов замените пароль в формате обычного текста переменной, определенной в используемом инструменте CI/CD.

### <a name="run-without-credentials"></a>Выполнение без учетных данных

Так как по умолчанию переменная `$Credential` принимает значение пустого объекта учетных данных, вы можете выполнять команду без учетных данных, как показано в этом примере:

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a>Работа с устаревшими командлетами

Не все командлеты поддерживают объекты учетных данных или позволяют использовать пустые учетные данные. Для них требуется указать имя пользователя и пароль в формате строк. Существует несколько способов обойти такое ограничение.

### <a name="using-if-else-to-handle-empty-credentials"></a>Использование оператора if-else для обработки пустых учетных данных

В этом сценарии командлет, который вы хотите выполнить, не принимает пустой объект учетных данных. В этом примере параметр **Credential** добавляется к командлету `Invoke-Command`, только если он не пустой. В противном случае командлет `Invoke-Command` выполняется без параметра **Credential**.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a>Использование сплаттинга для обработки пустых учетных данных

В этом примере используется сплаттинг параметра для вызова устаревшего командлета. Объект `$Credential` добавляется условно в хэш-таблицу для сплаттинга и позволяет избежать повторения блока скрипта `Invoke-Command`. Подробные сведения о сплаттинге в функциях см. в записи блога [Сплаттинг параметров в расширенные функции][].

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a>Работа со строковыми паролями

Командлет `Invoke-Sqlcmd` является примером командлета, который принимает пароль в формате строки.
Командлет `Invoke-Sqlcmd` позволяет вам выполнять простые инструкции SQL для вставки, обновления и удаления. Командлет `Invoke-Sqlcmd` требует указания имени пользователя и пароля в формате открытого текста, а не более защищенного объекта учетных данных. В этом примере показано, как извлечь имя пользователя и пароль из объекта учетных данных.

Функция `Get-AllSQLDatabases` в этом примере вызывает командлет `Invoke-Sqlcmd` для отправки серверу SQL запроса по всем его базам данных. Функция определяет параметр **Credential** с теми же атрибутами, которые были использованы в предыдущих примерах. Так как имя пользователя и пароль существуют в переменной `$Credential`, вы можете извлечь эти значения для использования с командлетом `Invoke-Sqlcmd`.

Имя пользователя доступно из свойства **UserName** переменной `$Credential`. Чтобы получить пароль, используйте метод `GetNetworkCredential()` объекта `$Credential`. Значения извлекаются в переменные, которые добавляются в хэш-таблицу, используемую для сплаттинга параметров в командлет `Invoke-Sqlcmd`.

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a>Дополнительные сведения об управлении командлетами

Создание и хранение объектов учетных данных с соблюдением требований безопасности может быть сложной задачей. Приведенные ниже ресурсы помогут вам в работе с командлетами PowerShell.

- [BetterCredentials][]
- [Хранилище ключей Azure][]
- [Проект Vault][]
- [Модуль SecretManagement][]

<!-- link references -->
[Оригинал]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Хранилище ключей Azure]: https://azure.microsoft.com/services/key-vault/
[Проект Vault]: https://www.vaultproject.io/
[Сплаттинг параметров в расширенные функции]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Автоматизация с помощью Jenkins и PowerShell в Windows — часть 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Модуль SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
