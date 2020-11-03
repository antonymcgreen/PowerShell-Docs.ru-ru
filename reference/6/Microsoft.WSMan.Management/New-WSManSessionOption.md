---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: 8996c550147ab7e0857d97b0a47baf92fac514d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226926"
---
# <span data-ttu-id="52de3-103">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="52de3-103">New-WSManSessionOption</span></span>

## <span data-ttu-id="52de3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52de3-104">SYNOPSIS</span></span>
<span data-ttu-id="52de3-105">Создает хэш-таблицу параметра сеанса для использования в качестве входных параметров для командлетов WS-Management.</span><span class="sxs-lookup"><span data-stu-id="52de3-105">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="52de3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52de3-106">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="52de3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52de3-107">DESCRIPTION</span></span>
<span data-ttu-id="52de3-108">Командлет **New-WSManSessionOption** создает хэш-таблицу параметра сеанса WSMan, которую можно передать в командлеты WSMan:</span><span class="sxs-lookup"><span data-stu-id="52de3-108">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="52de3-109">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-109">Get-WSManInstance</span></span>
- <span data-ttu-id="52de3-110">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-110">Set-WSManInstance</span></span>
- <span data-ttu-id="52de3-111">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="52de3-111">Invoke-WSManAction</span></span>
- <span data-ttu-id="52de3-112">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="52de3-112">Connect-WSMan</span></span>

## <span data-ttu-id="52de3-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="52de3-113">EXAMPLES</span></span>

### <span data-ttu-id="52de3-114">Пример 1. Создание соединения, использующего параметры соединения</span><span class="sxs-lookup"><span data-stu-id="52de3-114">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="52de3-115">В этом примере создается подключение к удаленному компьютеру Server01 с помощью параметров соединения, определенных параметром **New-WSManSessionOption**.</span><span class="sxs-lookup"><span data-stu-id="52de3-115">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption**.</span></span>

<span data-ttu-id="52de3-116">Первая команда использует **New-WSManSessionOption** для хранения набора параметров подключения в переменной $a.</span><span class="sxs-lookup"><span data-stu-id="52de3-116">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="52de3-117">В этом случае для параметров сеанса задано время ожидания подключения в размере 30 секунд (30 000 миллисекунд).</span><span class="sxs-lookup"><span data-stu-id="52de3-117">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="52de3-118">Вторая команда использует параметр *SessionOption* для передачи учетных данных, хранящихся в переменной $a, в **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="52de3-118">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="52de3-119">Затем **Connect-WSMan** подключается к удаленному компьютеру Server01, используя указанные параметры сеанса.</span><span class="sxs-lookup"><span data-stu-id="52de3-119">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="52de3-120">**Connect-WSMan** обычно используется в контексте поставщика WSMan для подключения к удаленному компьютеру (в данном случае это компьютер Server01).</span><span class="sxs-lookup"><span data-stu-id="52de3-120">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="52de3-121">Однако этот командлет можно использовать для установки соединения с удаленными компьютерами перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="52de3-121">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="52de3-122">Эти подключения отображаются в списке **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="52de3-122">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="52de3-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52de3-123">PARAMETERS</span></span>

### <span data-ttu-id="52de3-124">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="52de3-124">-NoEncryption</span></span>
<span data-ttu-id="52de3-125">Указывает, что соединение не использует шифрование для удаленных операций по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="52de3-125">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="52de3-126">По умолчанию незашифрованный трафик не включен.</span><span class="sxs-lookup"><span data-stu-id="52de3-126">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="52de3-127">Она должна быть включена в локальной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="52de3-127">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="52de3-128">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="52de3-128">-OperationTimeout</span></span>
<span data-ttu-id="52de3-129">Указывает время ожидания для операции WS-Management в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="52de3-129">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

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

### <span data-ttu-id="52de3-130">-Проксякцесстипе</span><span class="sxs-lookup"><span data-stu-id="52de3-130">-ProxyAccessType</span></span>
<span data-ttu-id="52de3-131">Задает механизм определения расположения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="52de3-131">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="52de3-132">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="52de3-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="52de3-133">Проксиеконфиг.</span><span class="sxs-lookup"><span data-stu-id="52de3-133">ProxyIEConfig.</span></span>
<span data-ttu-id="52de3-134">Используйте конфигурацию прокси-сервера Internet Explorer для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="52de3-134">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="52de3-135">Проксивинхттпконфиг.</span><span class="sxs-lookup"><span data-stu-id="52de3-135">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="52de3-136">Клиент WSMan использует параметры прокси-сервера, настроенные для WinHTTP, с помощью служебной программы ProxyCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="52de3-136">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="52de3-137">Проксяутодетект.</span><span class="sxs-lookup"><span data-stu-id="52de3-137">ProxyAutoDetect.</span></span>
<span data-ttu-id="52de3-138">Принудительное автоматическое обнаружение прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="52de3-138">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="52de3-139">Проксинопроксисервер.</span><span class="sxs-lookup"><span data-stu-id="52de3-139">ProxyNoProxyServer.</span></span>
<span data-ttu-id="52de3-140">Не используйте прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="52de3-140">Do not use a proxy server.</span></span>
<span data-ttu-id="52de3-141">Разрешите все имена узлов локально.</span><span class="sxs-lookup"><span data-stu-id="52de3-141">Resolve all host names locally.</span></span>

<span data-ttu-id="52de3-142">Значение по умолчанию — Проксиеконфиг.</span><span class="sxs-lookup"><span data-stu-id="52de3-142">The default value is ProxyIEConfig.</span></span>

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

### <span data-ttu-id="52de3-143">-Проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="52de3-143">-ProxyAuthentication</span></span>
<span data-ttu-id="52de3-144">Задает метод аутентификации, используемый на прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="52de3-144">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="52de3-145">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="52de3-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="52de3-146">Обычные.</span><span class="sxs-lookup"><span data-stu-id="52de3-146">Basic.</span></span>
<span data-ttu-id="52de3-147">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="52de3-147">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="52de3-148">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="52de3-148">Digest.</span></span>
<span data-ttu-id="52de3-149">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="52de3-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="52de3-150">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="52de3-150">Negotiate.</span></span>
<span data-ttu-id="52de3-151">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="52de3-151">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="52de3-152">Примерами являются протокол Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="52de3-152">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="52de3-153">Значение по умолчанию — Negotiate.</span><span class="sxs-lookup"><span data-stu-id="52de3-153">The default value is Negotiate.</span></span>

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

### <span data-ttu-id="52de3-154">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="52de3-154">-ProxyCredential</span></span>
<span data-ttu-id="52de3-155">Указывает учетную запись пользователя, имеющую разрешение на получение доступа через промежуточный веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="52de3-155">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="52de3-156">-Скипкачекк</span><span class="sxs-lookup"><span data-stu-id="52de3-156">-SkipCACheck</span></span>
<span data-ttu-id="52de3-157">Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="52de3-157">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="52de3-158">Используйте этот параметр только в том случае, если удаленный компьютер является доверенным другим способом, например, если удаленный компьютер является частью сети, которая физически защищена и изолирована, либо удаленный компьютер указан как доверенный узел в конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="52de3-158">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="52de3-159">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="52de3-159">-SkipCNCheck</span></span>
<span data-ttu-id="52de3-160">Указывает, что общее имя сертификата (CN) сервера не обязательно должен совпадать с именем узла сервера.</span><span class="sxs-lookup"><span data-stu-id="52de3-160">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="52de3-161">Применяется только в удаленных операциях с использованием HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52de3-161">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="52de3-162">Этот параметр следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="52de3-162">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="52de3-163">-Скипревокатиончекк</span><span class="sxs-lookup"><span data-stu-id="52de3-163">-SkipRevocationCheck</span></span>
<span data-ttu-id="52de3-164">Указывает, что соединение не проверяет состояние отзыва на сертификате сервера.</span><span class="sxs-lookup"><span data-stu-id="52de3-164">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="52de3-165">-Спнпорт</span><span class="sxs-lookup"><span data-stu-id="52de3-165">-SPNPort</span></span>
<span data-ttu-id="52de3-166">Указывает номер порта, добавляемый к имени участника-службы (SPN) удаленного сервера.</span><span class="sxs-lookup"><span data-stu-id="52de3-166">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="52de3-167">Имя субъекта-службы используется, когда выбран механизм аутентификации Kerberos или Negotiate.</span><span class="sxs-lookup"><span data-stu-id="52de3-167">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="52de3-168">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="52de3-168">-UseUTF16</span></span>
<span data-ttu-id="52de3-169">Указывает, что соединение кодирует запрос в формате UTF16, а не в формате UTF8.</span><span class="sxs-lookup"><span data-stu-id="52de3-169">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="52de3-170">По умолчанию используется кодирование UTF8.</span><span class="sxs-lookup"><span data-stu-id="52de3-170">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="52de3-171">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="52de3-171">CommonParameters</span></span>
<span data-ttu-id="52de3-172">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="52de3-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52de3-173">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="52de3-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52de3-174">Входные данные</span><span class="sxs-lookup"><span data-stu-id="52de3-174">INPUTS</span></span>

## <span data-ttu-id="52de3-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="52de3-175">OUTPUTS</span></span>

### <span data-ttu-id="52de3-176">SessionOption</span><span class="sxs-lookup"><span data-stu-id="52de3-176">SessionOption</span></span>

## <span data-ttu-id="52de3-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="52de3-177">NOTES</span></span>

## <span data-ttu-id="52de3-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="52de3-178">RELATED LINKS</span></span>

[<span data-ttu-id="52de3-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="52de3-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="52de3-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="52de3-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="52de3-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="52de3-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="52de3-182">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="52de3-182">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="52de3-183">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="52de3-183">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="52de3-184">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-184">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="52de3-185">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="52de3-185">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="52de3-186">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-186">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="52de3-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="52de3-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="52de3-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="52de3-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="52de3-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="52de3-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="52de3-190">Test-WSMan</span></span>](Test-WSMan.md)
