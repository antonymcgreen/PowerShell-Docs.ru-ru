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
# <span data-ttu-id="0a24b-102">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="0a24b-102">New-WSManSessionOption</span></span>

## <span data-ttu-id="0a24b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0a24b-103">SYNOPSIS</span></span>
<span data-ttu-id="0a24b-104">Создает хэш-таблицу параметра сеанса для использования в качестве входных параметров для командлетов WS-Management.</span><span class="sxs-lookup"><span data-stu-id="0a24b-104">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="0a24b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0a24b-105">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="0a24b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0a24b-106">DESCRIPTION</span></span>
<span data-ttu-id="0a24b-107">Командлет **New-WSManSessionOption** создает хэш-таблицу параметра сеанса WSMan, которую можно передать в командлеты WSMan:</span><span class="sxs-lookup"><span data-stu-id="0a24b-107">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="0a24b-108">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-108">Get-WSManInstance</span></span>
- <span data-ttu-id="0a24b-109">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-109">Set-WSManInstance</span></span>
- <span data-ttu-id="0a24b-110">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0a24b-110">Invoke-WSManAction</span></span>
- <span data-ttu-id="0a24b-111">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0a24b-111">Connect-WSMan</span></span>

## <span data-ttu-id="0a24b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="0a24b-112">EXAMPLES</span></span>

### <span data-ttu-id="0a24b-113">Пример 1. Создание соединения, использующего параметры соединения</span><span class="sxs-lookup"><span data-stu-id="0a24b-113">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="0a24b-114">В этом примере создается подключение к удаленному компьютеру Server01 с помощью параметров соединения, определенных параметром **New-WSManSessionOption**.</span><span class="sxs-lookup"><span data-stu-id="0a24b-114">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption**.</span></span>

<span data-ttu-id="0a24b-115">Первая команда использует **New-WSManSessionOption** для хранения набора параметров подключения в переменной $a.</span><span class="sxs-lookup"><span data-stu-id="0a24b-115">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="0a24b-116">В этом случае для параметров сеанса задано время ожидания подключения в размере 30 секунд (30 000 миллисекунд).</span><span class="sxs-lookup"><span data-stu-id="0a24b-116">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="0a24b-117">Вторая команда использует параметр *SessionOption* для передачи учетных данных, хранящихся в переменной $a, в **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="0a24b-117">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="0a24b-118">Затем **Connect-WSMan** подключается к удаленному компьютеру Server01, используя указанные параметры сеанса.</span><span class="sxs-lookup"><span data-stu-id="0a24b-118">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="0a24b-119">**Connect-WSMan** обычно используется в контексте поставщика WSMan для подключения к удаленному компьютеру (в данном случае это компьютер Server01).</span><span class="sxs-lookup"><span data-stu-id="0a24b-119">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="0a24b-120">Однако этот командлет можно использовать для установки соединения с удаленными компьютерами перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="0a24b-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="0a24b-121">Эти подключения отображаются в списке **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="0a24b-121">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="0a24b-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0a24b-122">PARAMETERS</span></span>

### <span data-ttu-id="0a24b-123">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="0a24b-123">-NoEncryption</span></span>
<span data-ttu-id="0a24b-124">Указывает, что соединение не использует шифрование для удаленных операций по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="0a24b-124">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="0a24b-125">По умолчанию незашифрованный трафик не включен.</span><span class="sxs-lookup"><span data-stu-id="0a24b-125">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="0a24b-126">Она должна быть включена в локальной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a24b-126">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="0a24b-127">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="0a24b-127">-OperationTimeout</span></span>
<span data-ttu-id="0a24b-128">Указывает время ожидания для операции WS-Management в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="0a24b-128">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

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

### <span data-ttu-id="0a24b-129">-Проксякцесстипе</span><span class="sxs-lookup"><span data-stu-id="0a24b-129">-ProxyAccessType</span></span>
<span data-ttu-id="0a24b-130">Задает механизм определения расположения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="0a24b-130">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="0a24b-131">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0a24b-131">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0a24b-132">Проксиеконфиг.</span><span class="sxs-lookup"><span data-stu-id="0a24b-132">ProxyIEConfig.</span></span>
<span data-ttu-id="0a24b-133">Используйте конфигурацию прокси-сервера Internet Explorer для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a24b-133">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="0a24b-134">Проксивинхттпконфиг.</span><span class="sxs-lookup"><span data-stu-id="0a24b-134">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="0a24b-135">Клиент WSMan использует параметры прокси-сервера, настроенные для WinHTTP, с помощью служебной программы ProxyCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="0a24b-135">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="0a24b-136">Проксяутодетект.</span><span class="sxs-lookup"><span data-stu-id="0a24b-136">ProxyAutoDetect.</span></span>
<span data-ttu-id="0a24b-137">Принудительное автоматическое обнаружение прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="0a24b-137">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="0a24b-138">Проксинопроксисервер.</span><span class="sxs-lookup"><span data-stu-id="0a24b-138">ProxyNoProxyServer.</span></span>
<span data-ttu-id="0a24b-139">Не используйте прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="0a24b-139">Do not use a proxy server.</span></span>
<span data-ttu-id="0a24b-140">Разрешите все имена узлов локально.</span><span class="sxs-lookup"><span data-stu-id="0a24b-140">Resolve all host names locally.</span></span>

<span data-ttu-id="0a24b-141">Значение по умолчанию — Проксиеконфиг.</span><span class="sxs-lookup"><span data-stu-id="0a24b-141">The default value is ProxyIEConfig.</span></span>

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

### <span data-ttu-id="0a24b-142">-Проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="0a24b-142">-ProxyAuthentication</span></span>
<span data-ttu-id="0a24b-143">Задает метод аутентификации, используемый на прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="0a24b-143">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="0a24b-144">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0a24b-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0a24b-145">Обычные.</span><span class="sxs-lookup"><span data-stu-id="0a24b-145">Basic.</span></span>
<span data-ttu-id="0a24b-146">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="0a24b-146">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="0a24b-147">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="0a24b-147">Digest.</span></span>
<span data-ttu-id="0a24b-148">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="0a24b-148">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="0a24b-149">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="0a24b-149">Negotiate.</span></span>
<span data-ttu-id="0a24b-150">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="0a24b-150">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="0a24b-151">Примерами являются протокол Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="0a24b-151">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="0a24b-152">Значение по умолчанию — Negotiate.</span><span class="sxs-lookup"><span data-stu-id="0a24b-152">The default value is Negotiate.</span></span>

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

### <span data-ttu-id="0a24b-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="0a24b-153">-ProxyCredential</span></span>
<span data-ttu-id="0a24b-154">Указывает учетную запись пользователя, имеющую разрешение на получение доступа через промежуточный веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="0a24b-154">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="0a24b-155">-Скипкачекк</span><span class="sxs-lookup"><span data-stu-id="0a24b-155">-SkipCACheck</span></span>
<span data-ttu-id="0a24b-156">Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0a24b-156">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="0a24b-157">Используйте этот параметр только в том случае, если удаленный компьютер является доверенным другим способом, например, если удаленный компьютер является частью сети, которая физически защищена и изолирована, либо удаленный компьютер указан как доверенный узел в конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="0a24b-157">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="0a24b-158">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="0a24b-158">-SkipCNCheck</span></span>
<span data-ttu-id="0a24b-159">Указывает, что общее имя сертификата (CN) сервера не обязательно должен совпадать с именем узла сервера.</span><span class="sxs-lookup"><span data-stu-id="0a24b-159">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="0a24b-160">Применяется только в удаленных операциях с использованием HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0a24b-160">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="0a24b-161">Этот параметр следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0a24b-161">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="0a24b-162">-Скипревокатиончекк</span><span class="sxs-lookup"><span data-stu-id="0a24b-162">-SkipRevocationCheck</span></span>
<span data-ttu-id="0a24b-163">Указывает, что соединение не проверяет состояние отзыва на сертификате сервера.</span><span class="sxs-lookup"><span data-stu-id="0a24b-163">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="0a24b-164">-Спнпорт</span><span class="sxs-lookup"><span data-stu-id="0a24b-164">-SPNPort</span></span>
<span data-ttu-id="0a24b-165">Указывает номер порта, добавляемый к имени участника-службы (SPN) удаленного сервера.</span><span class="sxs-lookup"><span data-stu-id="0a24b-165">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="0a24b-166">Имя субъекта-службы используется, когда выбран механизм аутентификации Kerberos или Negotiate.</span><span class="sxs-lookup"><span data-stu-id="0a24b-166">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="0a24b-167">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="0a24b-167">-UseUTF16</span></span>
<span data-ttu-id="0a24b-168">Указывает, что соединение кодирует запрос в формате UTF16, а не в формате UTF8.</span><span class="sxs-lookup"><span data-stu-id="0a24b-168">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="0a24b-169">По умолчанию используется кодирование UTF8.</span><span class="sxs-lookup"><span data-stu-id="0a24b-169">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="0a24b-170">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0a24b-170">CommonParameters</span></span>
<span data-ttu-id="0a24b-171">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0a24b-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0a24b-172">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0a24b-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0a24b-173">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0a24b-173">INPUTS</span></span>

## <span data-ttu-id="0a24b-174">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0a24b-174">OUTPUTS</span></span>

### <span data-ttu-id="0a24b-175">SessionOption</span><span class="sxs-lookup"><span data-stu-id="0a24b-175">SessionOption</span></span>

## <span data-ttu-id="0a24b-176">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0a24b-176">NOTES</span></span>

## <span data-ttu-id="0a24b-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0a24b-177">RELATED LINKS</span></span>

[<span data-ttu-id="0a24b-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0a24b-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="0a24b-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0a24b-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="0a24b-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0a24b-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="0a24b-181">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0a24b-181">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="0a24b-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0a24b-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="0a24b-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="0a24b-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0a24b-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="0a24b-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="0a24b-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="0a24b-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0a24b-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="0a24b-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="0a24b-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="0a24b-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="0a24b-189">Test-WSMan</span></span>](Test-WSMan.md)

