---
description: Описание ускорителей типов, доступных для классов .NET Framework
keywords: powershell,командлет
Locale: en-US
ms.date: 05/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_accelerators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Accelerators
ms.openlocfilehash: 6f73aa590b64cda5739a2a118b2b4c5a6c103a67
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231146"
---
# <a name="about-type-accelerators"></a>О ускорителях типов

## <a name="short-desription"></a>КОРОТКИЙ ОПИСАНИЕ
Описание ускорителей типов, доступных для классов .NET Framework

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Ускорители типов являются псевдонимами для классов .NET Framework. Они позволяют обращаться к конкретным классам .NET Framework без явного ввода полного имени класса. Например, можно сократить класс **алиасаттрибуте** с `[System.Management.Automation.AliasAttribute]` на `[Alias]` .

> [!NOTE]
> Все ускорители типов по-прежнему должны быть заключены в квадратные скобки ( `[]` ).

## <a name="available-type-accelerators"></a>Доступные ускорители типов

|        Accelerator          |                           Полное имя класса                           |
|---------------------------- | ------------------------------------------------------------------- |
|ADSI                         | System. DirectoryServices. DirectoryEntry                             |
|адсисеарчер                 | System. DirectoryServices. DirectorySearcher                          |
|Псевдоним                        | System. Management. Automation. Алиасаттрибуте                         |
|алловемптиколлектион         | System. Management. Automation. Алловемптиколлектионаттрибуте          |
|алловемптистринг             | System. Management. Automation. Алловемптистрингаттрибуте              |
|AllowNull                    | System. Management. Automation. Алловнуллаттрибуте                     |
|аргументкомплетер            | System. Management. Automation. Аргументкомплетераттрибуте             |
|аргументкомплетионс          | System. Management. Automation. Аргументкомплетионсаттрибуте           |
|массиве                        | System.Array                                                        |
|bigint                       | System. Numerics. BigInteger                                          |
|bool                         | System.Boolean                                                      |
|byte                         | System.Byte                                                         |
|char                         | System.Char                                                         |
|Цимкласс                     | Microsoft. Management. Infrastructure. Цимкласс                        |
|Цимконвертер                 | Microsoft. Management. Infrastructure. Цимконвертер                    |
|ciminstance                  | Microsoft.Management.Infrastructure.CimInstance                     |
|CimSession                   | Microsoft.Management.Infrastructure.CimSession                      |
|Цимтипе                      | Microsoft. Management. Infrastructure. Цимтипе                         |
|CmdletBinding                | System. Management. Automation. Кмдлетбиндингаттрибуте                 |
|регионов                  | System. Globalization. CultureInfo                                    |
|DATETIME                     | System.DateTime                                                     |
|Decimal                      | System.Decimal                                                      |
|double                       | System.Double                                                       |
|DscLocalConfigurationManager | System. Management. Automation. Дсклокалконфигуратионманажераттрибуте  |
|DscProperty                  | System. Management. Automation. Дскпропертяттрибуте                   |
|DscResource                  | System. Management. Automation. Дскресаурцеаттрибуте                   |
|експериментактион             | System. Management. Automation. Експериментактион                       |
|Экспериментальный                 | System. Management. Automation. Експерименталаттрибуте                  |
|експерименталфеатуре          | System. Management. Automation. Експерименталфеатуре                    |
|float                        | System.Single                                                       |
|guid                         | System.Guid                                                         |
|хеш                    | System.Collections.Hashtable                                        |
|initialsessionstate          | System.Management.Automation.Runspaces.IniТиалсессионстате          |
|INT                          | System.Int32                                                        |
|int16                        | System.Int16                                                        |
|int32                        | System.Int32                                                        |
|int64                        | System.Int64                                                        |
|IP                    | System .NET. IPAddress                                                |
|IPEndpoint                   | System .NET. IPEndPoint                                               |
|long                         | System.Int64                                                        |
|MailAddress                  | System .NET. mail. MailAddress                                         |
|нуллстринг                   | System. Management. Automation. Language. Нуллстринг                    |
|обжектсекурити               | System. Security. AccessControl. Обжектсекурити                        |
|OutputType                   | System. Management. Automation. Аутпуттипеаттрибуте                    |
|Параметр                    | System. Management. Automation. Параметераттрибуте                     |
|PhysicalAddress              | System .NET. NetworkInformation. PhysicalAddress                       |
|powershell                   | System. Management. Automation. PowerShell                             |
|псалиаспроперти              | System. Management. Automation. Псалиаспроперти                        |
|pscredential                 | System.Management.Automation.PSCredential                           |
|PCSCustomObject               | System.Management.Automation.PSObject                               |
|псдефаултвалуе               | System.Management.Automation.PSDЕфаултвалуеаттрибуте                |
|пслистмодифиер               | System. Management. Automation. Пслистмодифиер                         |
|PSModuleInfo                 | System.Management.Automation.PSModuleInfo                           |
|пснотепроперти               | System. Management. Automation. Пснотепроперти                         |
|PSObject                     | System.Management.Automation.PSObject                               |
|пспримитиведиктионари        | System. Management. Automation. Пспримитиведиктионари                  |
|пспропертекспрессион         | Microsoft. PowerShell. Commands. Пспропертекспрессион                  |
|псскриптмесод               | System. Management. Automation. Псскриптмесод                         |
|псскриптпроперти             | System. Management. Automation. Псскриптпроперти                       |
|пстипенамеаттрибуте          | System. Management. Automation. Пстипенамеаттрибуте                    |
|psvariable                   | System. Management. Automation. PSVariable                             |
|псвариаблепроперти           | System. Management. Automation. Псвариаблепроперти                     |
|ref                          | System. Management. Automation. Псреференце                            |
|regex                        | System.Text.RegularExpressions.Regex                                |
|пространство выполнения                     | System. Management. Automation. пространства выполнения                     |
|рунспацефактори              | System. Management. Automation. пространства выполнения. Рунспацефактори              |
|sbyte                        | System.SByte                                                        |
|ScriptBlock                  | System. Management. Automation. ScriptBlock                            |
|SecureString                 | System.Security.SecureString                                        |
|semver                       | System. Management. Automation. Семантикверсион                        |
|short                        | System.Int16                                                        |
|single                       | System.Single                                                       |
|строка                       | System.String                                                       |
|суппортсвилдкардс            | System. Management. Automation. Суппортсвилдкардсаттрибуте             |
|switch                       | System.Management.Automation.SwitchParameter                        |
|Интервал времени                     | System.TimeSpan                                                     |
|тип                         | System.Type                                                         |
|uint                         | System.UInt32                                                       |
|uint16                       | System.UInt16                                                       |
|uint32                       | System.UInt32                                                       |
|uint64                       | System.UInt64                                                       |
|ulong                        | System.UInt64                                                       |
|uri                          | System.Uri                                                          |
|ushort                       | System.UInt16                                                       |
|валидатекаунт                | System. Management. Automation. Валидатекаунтаттрибуте                 |
|валидатедриве                | System. Management. Automation. Валидатедривеаттрибуте                 |
|валидателенгс               | System. Management. Automation. Валидателенгсаттрибуте                |
|валидатенотнулл              | System. Management. Automation. Валидатенотнуллаттрибуте               |
|валидатенотнуллоремпти       | System. Management. Automation. Валидатенотнуллоремптяттрибуте        |
|ValidatePattern              | System. Management. Automation. Валидатепаттернаттрибуте               |
|валидатеранже                | System. Management. Automation. Валидатеранжеаттрибуте                 |
|валидатескрипт               | System. Management. Automation. Валидатескриптаттрибуте                |
|ValidateSet                  | System. Management. Automation. Валидатесетаттрибуте                   |
|валидатетрустеддата          | System. Management. Automation. Валидатетрустеддатааттрибуте           |
|валидатеусердриве            | System. Management. Automation. Валидатеусердривеаттрибуте             |
|version                      | System.Version                                                      |
|void                         | System.Void                                                         |
|вилдкардпаттерн              | System. Management. Automation. Вилдкардпаттерн                        |
|интерфейса                          | System. Management. ManagementObject                                  |
|WMICLASS                     | System. Management. Манажементкласс                                   |
|вмисеарчер                  | System. Management. Манажементобжектсеарчер                          |
|X500DistinguishedName        | System. Security. Cryptography. X509Certificates. X500DistinguishedName |
|X509Certificate              | System. Security. Cryptography. X509Certificates. X509Certificate       |
|xml                          | System.Xml.Xmlдокумент                                              |
