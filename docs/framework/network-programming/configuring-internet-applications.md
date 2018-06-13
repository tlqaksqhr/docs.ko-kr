---
title: 인터넷 응용 프로그램 구성
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7c4755e13202f60df5704f6faefb3b279a30ce58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395062"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="f2ff0-102">인터넷 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="f2ff0-102">Configuring Internet Applications</span></span>
<span data-ttu-id="f2ff0-103">[\<system.Net> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 구성 요소에는 응용 프로그램에 대한 네트워크 구성 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-103">The [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="f2ff0-104">[\<system.Net> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 구성 요소를 사용하여 프록시 서버를 설정하고, 연결 관리 매개 변수를 설정하고, 응용 프로그램에 사용자 지정 인증 및 요청 모듈을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-104">Using the [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="f2ff0-105">[\<defaultProxy> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 구성 요소는 `GlobalProxySelection` 클래스에서 반환된 프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-105">The [\<defaultProxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="f2ff0-106">자체적인 <xref:System.Net.HttpWebRequest.Proxy%2A> 속성이 특정 값으로 설정되지 않은 <xref:System.Net.HttpWebRequest>는 기본 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-106">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="f2ff0-107">프록시 주소를 설정하는 것 이외에 프록시를 사용하지 않을 서버 주소 목록을 만들고 로컬 주소에 프록시를 사용하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-107">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="f2ff0-108">Microsoft Internet Explorer 설정은 구성 설정과 결합되고 구성 설정이 우선 적용된다는 점을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-108">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="f2ff0-109">다음 예제에서는 기본 프록시 서버 주소를 http://proxyserver로 설정하고, 로컬 주소에 프록시를 사용하지 않도록 지정하고, contoso.com 도메인에 있는 서버에 대한 모든 요청이 프록시를 바이패스하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-109">The following example sets the default proxy server address to http://proxyserver, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f2ff0-110">[\<connectionManagement> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) 구성 요소를 사용하여 특정 서버 또는 모든 기타 서버에 대해 설정할 수 있는 영구 연결 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-110">Use the [\<connectionManagement> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="f2ff0-111">다음 예제에서는 응용 프로그램에서 www.contoso.com에 대한 영구 연결 2개, IP 주소 192.168.1.2를 사용한 서버에 대한 영구 연결 4개, 모든 기타 서버에 대한 영구 연결 1개를 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-111">The following example configures the application to use two persistent connections to the server www.contoso.com, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f2ff0-112">사용자 지정 인증 모듈은 [\<authenticationModules> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) 구성 요소를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-112">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="f2ff0-113">사용자 지정 인증 모듈은 <xref:System.Net.IAuthenticationModule> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-113">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="f2ff0-114">다음 예제에서는 사용자 지정 인증 모듈을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-114">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f2ff0-115">[\<webRequestModules> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) 구성 요소를 사용하여 응용 프로그램에서 프로토콜별 모듈을 통해 인터넷 리소스의 정보를 요청하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-115">You can use the [\<webRequestModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="f2ff0-116">지정된 모듈은 <xref:System.Net.IWebRequestCreate> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-116">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="f2ff0-117">다음 예제와 같이 구성 파일에서 사용자 지정 모듈을 지정하여 기본 HTTP, HTTPS 및 파일 요청 모듈을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ff0-117">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2ff0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ff0-118">See Also</span></span>  
 [<span data-ttu-id="f2ff0-119">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f2ff0-119">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="f2ff0-120">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f2ff0-120">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="f2ff0-121">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="f2ff0-121">\<system.Net> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
