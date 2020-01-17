---
ms.date: 08/23/2017
keywords: powershell,командлет
title: Устранение неполадок с доступом в Windows PowerShell Web Access
ms.openlocfilehash: 818beffaf7df55ae36a154b7b751f9201c5b4299
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870189"
---
# <a name="troubleshooting-access-problems-in-windows-powershell-web-access"></a>Устранение неполадок с доступом в Windows PowerShell Web Access

Обновлено: 24 июня 2013 г. (пересмотрено 23 августа 2017 г.)

Область применения: Windows Server 2012 R2, Windows Server 2012

В следующем разделе перечислены некоторые часто возникающие проблемы при попытке подключения к удаленному компьютеру с помощью Windows PowerShell Web Access и предложения по разрешению таких проблем.

## <a name="sign-in-failure"></a>Сбой при входе

Сбой может возникать по любой из следующих причин.

- Отсутствуют правило авторизации, которое позволяет пользователю получить доступ к компьютеру, или конкретная конфигурация сеанса на удаленном компьютере.

  Безопасность Windows PowerShell Web Access является ограничивающей. Пользователям необходимо явным образом предоставлять доступ к удаленным компьютерам с помощью правил авторизации.

  Дополнительные сведения о создании правил авторизации см. в разделе [Правила авторизации и средства безопасности Windows PowerShell Web Access](authorization-rules-and-security-features-of-windows-powershell-web-access.md).

- У пользователя отсутствует авторизованный доступ к целевому компьютеру. Это определяется списками управления доступом.

  Подробнее см. в статье [Вход в систему Windows PowerShell Web Access](use-the-web-based-windows-powershell-console.md#signing-in-to-windows-powershell-web-access) или в блоге группы разработчиков Windows PowerShell.

- Возможно, удаленное управление Windows PowerShell не включено на целевом компьютере.

  Убедитесь, что удаленное управление включено на компьютере, к которому пытается подключиться пользователь.

  Дополнительные сведения см. в разделе [Настройка удаленного управления компьютером](/powershell/module/microsoft.powershell.core/about/about_remote_requirements#how-to-configure-your-computer-for-remoting).

## <a name="internal-server-error"></a>Внутренняя ошибка сервера

При попытке войти в Windows PowerShell Web Access в окне Internet Explorer пользователи видят страницу **Внутренняя ошибка сервера** или *Internet Explorer* перестает реагировать на запросы.

Эта проблема специфична для Internet Explorer.

### <a name="possible-cause"></a>Возможная причина

Она может возникнуть, если пользователь вошел в систему с именем домена, содержащим китайские символы, или если такие символы встречаются в имени сервера шлюза.

#### <a name="workaround"></a>Обходной путь

1. Установите и запустите Internet Explorer 10
1. Измените **Режим документа** в Internet Explorer на *стандартный IE10*.
   1. Нажмите клавишу **F12**, чтобы открыть консоль "Средства разработчика".
   1. В Internet Explorer 10 щелкните **Режим браузера** и выберите *Internet Explorer 10*.
   1. Щелкните **Режим документа** и выберите *стандартный IE10*.
   1. Снова нажать клавишу **F12**, чтобы закрыть консоль "Средства разработчика".
1. Отключите автоматическую настройку прокси-сервера в Internet Explorer 10.
   1. В меню **Сервис** выберите пункт **Свойства браузера**.
   1. В диалоговом окне **Свойства браузера** на вкладке **Подключения** выберите  **Настройка сети**.
   1. Снять флажок **Автоматическое определение параметров**. Нажать кнопку **ОК**, а затем нажать кнопку **ОК** еще раз, чтобы закрыть диалоговое окно *Свойства браузера*.

## <a name="cannot-connect-to-a-remote-workgroup-computer"></a>Невозможно подключиться к удаленному компьютеру в рабочей группе

Если целевой компьютер является членом рабочей группы, используйте следующий синтаксис, чтобы указать имя пользователя и войти на компьютер: `<workgroup_name>\<user_name>`

## <a name="cannot-find-web-server-iis-management-tools-even-though-the-role-was-installed"></a>Невозможно найти инструменты управления веб-сервера (IIS), даже если роль была установлена

Если вы установили Windows PowerShell Web Access с помощью командлета `Install-WindowsFeature`, средства управления не установятся, если к командлету не добавить параметр **IncludeManagementTools**.

Например, см. раздел [Установка Windows PowerShell Web Access с помощью командлетов Windows PowerShell](install-and-use-windows-powershell-web-access.md#to-install-windows-powershell-web-access-by-using-windows-powershell-cmdlets).

Вы можете добавить консоль диспетчера служб IIS и другие нужные средства управления IIS, выбрав инструменты в сеансе **мастера добавления ролей и компонентов**, который нацелен на сервер шлюза. Мастер добавления ролей и функций открывается из диспетчера сервера.

## <a name="windows-powershell-web-access-website-is-not-accessible"></a>Веб-сайт Windows PowerShell Web Access недоступен

Если включена конфигурация повышенной безопасности в Internet Explorer (IE ESC), можно добавить веб-сайт Windows PowerShell Web Access в список надежных сайтов.

Менее предпочтительный способ (из-за угрозы безопасности) — отключить IE ESC. Отключить IE ESC можно с помощью плитки "Свойства" на странице "Локальный сервер" в диспетчере серверов.

## <a name="an-authorization-failure-occurred-verify-that-you-are-authorized-to-connect-to-the-destination-computer"></a>Произошел сбой авторизации. Убедитесь, что вы имеете права на подключение к конечному компьютеру.

Если сервер шлюза является конечным компьютером и в то же время входит в рабочую группу, при попытке подключения выводится указанное выше сообщение об ошибке.

Когда сервер шлюза также является конечным сервером и входит в рабочую группу, укажите имя пользователя, имя компьютера и имя группы пользователей. Не используйте точку (.) в качестве имени компьютера.

### <a name="scenarios-and-proper-values"></a>Ситуации и соответствующие значения

#### <a name="all-cases"></a>Все ситуации

  Параметр   |                                        Значение
------------- | -----------------------------------------------------------------------------------
UserName      | `Server_name\user_name`<br/>`Localhost\user_name`<br/>`.\user_name`
UserGroup     | `Server_name\user_group`<br/>`Localhost\user_group`<br/>`.\user_group`
ComputerGroup | `Server_name\computer_group`<br/>`Localhost\computer_group`<br/>`.\computer_group`

#### <a name="gateway-server-is-in-a-domain"></a>Сервер шлюза входит в домен

 Параметр   |                        Значение
------------ | ----------------------------------------------------
ИмяКомпьютера | Полное имя сервера шлюза или Localhost

#### <a name="gateway-server-is-in-a-workgroup"></a>Сервер шлюза входит в рабочую группу

 Параметр   |    Значение
------------ | -----------
ИмяКомпьютера | Имя сервера

### <a name="gateway-credentials"></a>Учетные данные шлюза

Войдите на сервер шлюза как на конечный компьютер, используя учетные данные в одном из следующих форматов.

- `Server_name\user_name`
- `Localhost\user_name`
- `.\user_name`

## <a name="a-security-identifier-sid-is-displayed-in-an-authorization-rule"></a>В правиле авторизации отображается идентификатор безопасности (SID)

Вместо синтаксиса `user_name/computer_name` в правиле авторизации отображается идентификатор безопасности (SID).

Либо правило больше не действительно, либо произошла ошибка запроса к доменным службам Active Directory. Правило авторизации недействительно обычно в том случае, если сервер шлюза когда-то входил в рабочую группу, но позднее был присоединен к домену.

## <a name="cannot-sign-in-with-rule-as-an-ipv6-address-with-a-domain"></a>Не удается войти с правилом, задающим IPv6-адрес в формате имени домена

Не удается войти на конечный компьютер, указанный в правилах авторизации под IPv6-адресом с доменом.

Правила авторизации не поддерживают IPv6-адреса в форме имени домена.

Чтобы указать конечный компьютер с помощью IPv6-адреса, используйте в правиле авторизации исходный IPv6-адрес (содержащий двоеточия). IPv6-адреса в форме имени домена и в числовой форме (с двоеточиями) поддерживаются в качестве имени конечного компьютера на странице входа в Windows PowerShell Web Access, но не в правилах авторизации.

Дополнительные сведения об IPv6-адресах см. в статье [Принцип работы IPv6](/previous-versions/windows/it-pro/windows-server-2003/cc781672(v=ws.10)).

## <a name="see-also"></a>См. также:

- [Правила авторизации и компоненты безопасности Windows PowerShell Web Access](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn282394(v=ws.11))
- [Использование веб-консоли Windows PowerShell](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831417(v=ws.11))
- [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)
