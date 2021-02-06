---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: e7d7f132eb82dc1a709a88cbdef525aa83d867e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600888"
---
# New-WSManSessionOption

## Краткий обзор
Создает хэш-таблицу параметра сеанса для использования в качестве входных параметров для командлетов WS-Management.

## SYNTAX

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## DESCRIPTION
Командлет **New-WSManSessionOption** создает хэш-таблицу параметра сеанса WSMan, которую можно передать в командлеты WSMan:

- Get-WSManInstance
- Set-WSManInstance
- Invoke-WSManAction
- Connect-WSMan

## Примеры

### Пример 1. Создание соединения, использующего параметры соединения

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

В этом примере создается подключение к удаленному компьютеру Server01 с помощью параметров соединения, определенных параметром **New-WSManSessionOption**.

Первая команда использует **New-WSManSessionOption** для хранения набора параметров подключения в переменной $a.
В этом случае для параметров сеанса задано время ожидания подключения в размере 30 секунд (30 000 миллисекунд).

Вторая команда использует параметр *SessionOption* для передачи учетных данных, хранящихся в переменной $a, в **Connect-WSMan**.
Затем **Connect-WSMan** подключается к удаленному компьютеру Server01, используя указанные параметры сеанса.

**Connect-WSMan** обычно используется в контексте поставщика WSMan для подключения к удаленному компьютеру (в данном случае это компьютер Server01).
Однако этот командлет можно использовать для установки соединения с удаленными компьютерами перед изменением поставщика WSMan.
Эти подключения отображаются в списке **ComputerName** .

## PARAMETERS

### -NoEncryption
Указывает, что соединение не использует шифрование для удаленных операций по протоколу HTTP.

По умолчанию незашифрованный трафик не включен.
Она должна быть включена в локальной конфигурации.

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

### -OperationTimeout
Указывает время ожидания для операции WS-Management в миллисекундах.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Проксякцесстипе
Задает механизм определения расположения прокси-сервера.
Допустимые значения для этого параметра:

- Проксиеконфиг.
Используйте конфигурацию прокси-сервера Internet Explorer для текущего пользователя.
- Проксивинхттпконфиг.
Клиент WSMan использует параметры прокси-сервера, настроенные для WinHTTP, с помощью служебной программы ProxyCfg.exe.
- Проксяутодетект.
Принудительное автоматическое обнаружение прокси-сервера.
- Проксинопроксисервер.
Не используйте прокси-сервер.
Разрешите все имена узлов локально.

Значение по умолчанию — Проксиеконфиг.

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Проксяусентикатион
Задает метод аутентификации, используемый на прокси-сервере.
Допустимые значения для этого параметра:

- Обычные.
схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.
- Дайджест.
это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.
- Negotiate —
это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.
Примерами являются протокол Kerberos и NTLM.

Значение по умолчанию — Negotiate.

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential
Указывает учетную запись пользователя, имеющую разрешение на получение доступа через промежуточный веб-прокси.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипкачекк
Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).
Используйте этот параметр только в том случае, если удаленный компьютер является доверенным другим способом, например, если удаленный компьютер является частью сети, которая физически защищена и изолирована, либо удаленный компьютер указан как доверенный узел в конфигурации WS-Management.

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

### -SkipCNCheck
Указывает, что общее имя сертификата (CN) сервера не обязательно должен совпадать с именем узла сервера.
Применяется только в удаленных операциях с использованием HTTPS.
Этот параметр следует использовать только для доверенных компьютеров.

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

### -Скипревокатиончекк
Указывает, что соединение не проверяет состояние отзыва на сертификате сервера.

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

### -Спнпорт
Указывает номер порта, добавляемый к имени участника-службы (SPN) удаленного сервера.
Имя субъекта-службы используется, когда выбран механизм аутентификации Kerberos или Negotiate.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseUTF16
Указывает, что соединение кодирует запрос в формате UTF16, а не в формате UTF8.
По умолчанию используется кодирование UTF8.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### SessionOption

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

