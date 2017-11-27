---
title: "자동 프록시 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8eec6ff84978cdbd31dd4be307d0eb9560edde19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="07290-102">자동 프록시 검색</span><span class="sxs-lookup"><span data-stu-id="07290-102">Automatic Proxy Detection</span></span>
<span data-ttu-id="07290-103">자동 프록시 검색은 웹 프록시 서버가 시스템에 의해 식별되고 클라이언트 대신 요청을 보내는 데 사용되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="07290-103">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="07290-104">이 기능을 WPAD(웹 프록시 자동 검색)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-104">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="07290-105">자동 프록시 검색을 사용하면 시스템이 요청에 사용할 수 있는 프록시 집합을 반환하는 프록시 구성 스크립트를 찾으려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-105">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="07290-106">프록시 구성 스크립트가 발견되면 <xref:System.Net.WebProxy> 인스턴스를 사용하는 요청에 대한 프록시 정보, 요청 스트림 또는 응답이 확보될 때 로컬 컴퓨터에서 스크립트가 다운로드, 컴파일 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-106">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="07290-107">자동 프록시 검색은 <xref:System.Net.WebProxy> 클래스에 의해 수행되며 요청 수준 설정, 구성 파일의 설정 및 Internet Explorer **LAN(Local Area Network)** 대화 상자를 사용하여 지정된 설정을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-107">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07290-108">Internet Explorer 주 메뉴에서 **도구**를 선택한 다음 **인터넷 옵션**을 선택하면 Internet Explorer **LAN(Local Area Network) 설정** 대화 상자를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-108">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="07290-109">다음으로, **연결** 탭을 선택하고 **LAN 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-109">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="07290-110">자동 프록시 검색을 사용하면 <xref:System.Net.WebProxy> 클래스가 다음과 같이 프록시 구성 스크립트를 찾으려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-110">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1.  <span data-ttu-id="07290-111">WinINet `InternetQueryOption` 함수는 Internet Explorer에서 가장 최근에 검색된 프록시 구성 스크립트를 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-111">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="07290-112">스크립트를 찾을 수 없는 경우 <xref:System.Net.WebProxy> 클래스는 DHCP(Dynamic Host Configuration Protocol)를 사용하여 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-112">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="07290-113">DHCP 서버는 스크립트의 위치(호스트 이름) 또는 스크립트에 대한 전체 URL로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-113">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3.  <span data-ttu-id="07290-114">DHCP가 WPAD 호스트를 식별하지 않는 경우 WPAD를 해당 이름 또는 별칭으로 사용하여 DNS에서 호스트를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-114">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4.  <span data-ttu-id="07290-115">호스트가 확인되지 않고 프록시 구성 스크립트의 위치가 Internet Explorer LAN 설정 또는 구성 파일에서 지정된 경우 이 위치가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-115">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07290-116">NT 서비스 또는 ASP.NET의 일부로 실행 중인 응용 프로그램은 호출하는 사용자의 Internet Explorer 프록시 서버 설정(사용 가능한 경우)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-116">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="07290-117">일부 서비스 응용 프로그램에는 이러한 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-117">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="07290-118">프록시는 전화 접속 아이콘별로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-118">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="07290-119">전화 접속 아이콘은 네트워크 연결 대화 상자에 있는 항목이며, 실제 네트워크 장치(모뎀 또는 이더넷 카드) 또는 가상 인터페이스(예: 네트워크 장치를 통해 실행되는 VPN 연결)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-119">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="07290-120">전화 접속 아이콘이 변경되면(예: 무선 연결이 액세스 지점을 변경하거나 VPN이 사용되는 경우) 프록시 검색 알고리즘이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-120">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="07290-121">기본적으로 Internet Explorer 프록시 설정이 프록시를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07290-121">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="07290-122">응용 프로그램이 비대화형 계정으로 실행되는 경우(IE 프록시 설정을 구성하는 편리한 방법 없이) 또는 IE 설정과 다른 프록시 설정을 사용하려는 경우 [\<defaultProxy> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 및 [\<proxy> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md) 요소가 정의된 구성 파일을 만들어 프록시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-122">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="07290-123">직접 만든 요청의 경우 다음 코드 예제와 같이 요청과 함께 null <xref:System.Net.WebRequest.Proxy%2A>를 사용하여 요청 수준에서 프록시 자동 검색을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07290-123">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub   
```  
  
 <span data-ttu-id="07290-124">프록시가 없는 요청은 <xref:System.Net.WebRequest.DefaultWebProxy%2A> 속성에서 사용할 수 있는 응용 프로그램 도메인의 기본 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07290-124">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07290-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07290-125">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="07290-126">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="07290-126">\<system.Net> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
