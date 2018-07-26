---
title: '&lt;네트워크&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e6cf78b06d5afe950dd97381e99ba9eb77f818ca
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874561"
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="296c8-102">&lt;네트워크&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="296c8-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="296c8-103">외부 전송 프로토콜 SMTP (Simple Mail) 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="296c8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="296c8-104">\<configuration></span></span>  
<span data-ttu-id="296c8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="296c8-105">\<system.net></span></span>  
<span data-ttu-id="296c8-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="296c8-106">\<mailSettings></span></span>  
<span data-ttu-id="296c8-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="296c8-107">\<smtp></span></span>  
<span data-ttu-id="296c8-108">\<network></span><span class="sxs-lookup"><span data-stu-id="296c8-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="296c8-109">구문</span><span class="sxs-lookup"><span data-stu-id="296c8-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="296c8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="296c8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="296c8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="296c8-112">특성</span><span class="sxs-lookup"><span data-stu-id="296c8-112">Attributes</span></span>  
  
|<span data-ttu-id="296c8-113">특성</span><span class="sxs-lookup"><span data-stu-id="296c8-113">Attribute</span></span>|<span data-ttu-id="296c8-114">설명</span><span class="sxs-lookup"><span data-stu-id="296c8-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="296c8-115">SMTP 메일 서버에 연결할 초기 SMTP 프로토콜 요청에 사용 하는 클라이언트 도메인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="296c8-116">기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="296c8-117">SMTP 트랜잭션에 대 한 SMTP 메일 서버에 액세스 하려면 기본 사용자 자격 증명을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="296c8-118">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="296c8-119">SMTP 메일 서버에 액세스 하려면 SSL 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="296c8-120">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="296c8-121">SMTP 트랜잭션에 사용할 SMTP 메일 서버의 호스트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="296c8-122">이 특성에 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="296c8-123">SMTP 메일 서버에 인증 하는 데 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="296c8-124">이 특성에 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="296c8-125">SMTP 메일 서버에 연결 하는 데 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="296c8-126">기본값은 25입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="296c8-127">SMTP 트랜잭션에 대 한 확장 된 보호를 사용 하는 경우 인증에 사용할 서비스 공급자 이름 (SPN)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="296c8-128">이 특성에 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="296c8-129">SMTP 메일 서버에 인증에 사용할 사용자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="296c8-130">이 특성에 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="296c8-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="296c8-131">Child Elements</span></span>  
 <span data-ttu-id="296c8-132">없음</span><span class="sxs-lookup"><span data-stu-id="296c8-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="296c8-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="296c8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="296c8-134">요소</span><span class="sxs-lookup"><span data-stu-id="296c8-134">Element</span></span>|<span data-ttu-id="296c8-135">설명</span><span class="sxs-lookup"><span data-stu-id="296c8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="296c8-136">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="296c8-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="296c8-137">단순 메일 전송 프로토콜 (SMTP) 메일 보내기 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="296c8-138">설명</span><span class="sxs-lookup"><span data-stu-id="296c8-138">Remarks</span></span>  
 <span data-ttu-id="296c8-139">일부 SMTP 서버에서 직접 인증을 사용 하기 전에 서버에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="296c8-140">기본 네트워크 자격 증명을 사용 하 여 호스트에서 직접 인증을 설정 하려는 경우는 `defaultCredentials` 특성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="296c8-141">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `defaultCredentials` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="296c8-142">또한 기본 인증 (한 사용자 이름 및 암호) SMTP 서버에 직접 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="296c8-143">이 옵션을 사용 하려면 유효한 사용자 이름 및 지정된 된 SMTP 서버에 대 한 암호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="296c8-144">기본 인증은 보냅니다 합니다 `userName` 및 `password` 암호화 되지 않은 서버에는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="296c8-145">네트워크 트래픽을 모니터링 하는 모든 자격 증명을 확인 하 고 하는 서버에 연결 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="296c8-146">Kerberos 또는 NTLM (NT LAN Manager입니다.)와 같은 더 안전한 인증 메커니즘을 사용 하는 것이 좋습니다. 하는 경우 `defaultCredentials` 는 `true`, Kerberos 또는 NTLM을 사용할지 서버에서 이러한 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="296c8-147">기본 인증 및 기본 네트워크 자격 증명 옵션은 함께 사용할 수 없습니다. 설정 하는 경우 `defaultCredentials` 에 `true` 및 사용자 이름 및 암호를 지정, 기본 네트워크 자격 증명 사용 되며, 기본 인증 데이터는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="296c8-148">지정 하는 경우 기본 인증에 대 한는 `userName`에 지정 해야는 `password` 인증 메일 서버에 직접.</span><span class="sxs-lookup"><span data-stu-id="296c8-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="296c8-149">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `userName` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="296c8-150">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `password` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="296c8-151">`password` 은 특성 일반적으로 보안상의 이유로 구성 파일에 입력 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="296c8-152">`clientDomain` 특성에는 SMTP 서버에 초기 SMTP 프로토콜 요청에 사용 되는 클라이언트 도메인 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="296c8-153">`clientDomain` 기본적으로 사용 되는 로컬 호스트 이름이 아닌 로컬 컴퓨터의 정규화 된 도메인 이름 특성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="296c8-154">이 큰 SMTP 프로토콜 표준 준수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="296c8-155">기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="296c8-156">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `clientDomain` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="296c8-157">`targetName` 특성은 확장 된 보호를 사용 하는 경우 인증에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="296c8-158">폼의 기본값은 "SMTPSVC /\<호스트 >" 여기서 \<호스트 > SMTP 메일 서버의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="296c8-159">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `targetName` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="296c8-160">`enableSsl` 특성 SMTP 메일 서버에 액세스 하려면 SSL을 사용할지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="296c8-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> 클래스 SMTP 서비스 확장에 대해만 지원 SMTP 보안 전송 계층 보안을 통해 3207 RFC에에서 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="296c8-162">이 모드에서는 SMTP 세션이 시작 된 암호화 되지 않은 채널에 다음 STARTTLS 명령을 실행 하는 SSL을 사용 하 여 보안 통신을 전환 하려면 서버에 클라이언트에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="296c8-163">RFC 3207 게시 하 여는 Task Force IETF (Internet Engineering)에 대 한 자세한 내용은 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="296c8-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="296c8-164">대체 연결 메서드 명령을 보내는 모든 프로토콜 하기 전에 SSL 세션을 선불 하 게 설정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="296c8-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="296c8-165">이 연결 방법을 SMTPS 라고 하 고 기본적으로 포트 465를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="296c8-166">이 대체 연결 방법은 SSL을 사용 하 여 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="296c8-167">합니다 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `enableSsl` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="296c8-168">예</span><span class="sxs-lookup"><span data-stu-id="296c8-168">Example</span></span>  
 <span data-ttu-id="296c8-169">다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보내는 해당 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="296c8-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="296c8-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="296c8-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="296c8-171">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="296c8-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
