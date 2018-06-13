---
title: 프록시 구성
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 41e1dcee90531de605b6bddc1eedc1c44235d8eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397535"
---
# <a name="proxy-configuration"></a><span data-ttu-id="9e27c-102">프록시 구성</span><span class="sxs-lookup"><span data-stu-id="9e27c-102">Proxy Configuration</span></span>
<span data-ttu-id="9e27c-103">프록시 서버는 리소스에 대한 클라이언트 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="9e27c-104">프록시는 해당 캐시에서 요청한 리소스를 반환하거나 리소스가 있는 서버로 요청을 전달할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="9e27c-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="9e27c-105">원격 서버로 전송되는 요청 수를 줄여 네트워크 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="9e27c-106">프록시를 사용하여 리소스에 대한 액세스를 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="9e27c-107">적응 프록시</span><span class="sxs-lookup"><span data-stu-id="9e27c-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="9e27c-108">.NET Framework에서 프록시는 적응 및 정적의 두 가지 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="9e27c-109">적응 프록시는 네트워크 구성이 변경되면 설정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="9e27c-110">예를 들어 랩톱 사용자가 전화 접속 네트워크 연결을 시작하면 적응 프록시가 해당 변경을 인식하여 새 구성 스크립트를 검색 및 실행하고 설정을 적절하게 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="9e27c-111">구성 스크립트를 통해 적응 프록시를 구성합니다([자동 프록시 검색](../../../docs/framework/network-programming/automatic-proxy-detection.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="9e27c-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="9e27c-112">스크립트는 응용 프로그램 프로토콜 집합과 각 프로토콜용 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="9e27c-113">구성 스크립트 실행 방식은 여러 옵션으로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="9e27c-114">다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="9e27c-115">구성 스크립트 다운로드 및 실행 빈도</span><span class="sxs-lookup"><span data-stu-id="9e27c-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="9e27c-116">스크립트가 다운로드를 대기할 시간</span><span class="sxs-lookup"><span data-stu-id="9e27c-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="9e27c-117">시스템에서 프록시에 액세스하는 데 사용해야 하는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="9e27c-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="9e27c-118">시스템에서 구성 스크립트를 다운로드하는 데 사용해야 하는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="9e27c-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="9e27c-119">네트워크 환경이 변경되는 경우에는 시스템에서 새 프록시 집합을 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="9e27c-120">네트워크 연결이 다운되거나 새 네트워크 연결이 초기화되면 시스템은 새 환경에서 적절한 구성 스크립트 소스를 찾아 새 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="9e27c-121">다음 테이블에는 적응 프록시의 구성 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="9e27c-122">특성, 속성 또는 구성 파일 설정</span><span class="sxs-lookup"><span data-stu-id="9e27c-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="9e27c-123">설명</span><span class="sxs-lookup"><span data-stu-id="9e27c-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="9e27c-124">스크립트 다운로드 간에 경과된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="9e27c-125">스크립트 다운로드를 대기할 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="9e27c-126">`useDefaultCredentials` 또는 <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="9e27c-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="9e27c-127">시스템이 기본 네트워크 자격 증명을 사용하여 프록시에 액세스하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="9e27c-128">시스템이 기본 네트워크 자격 증명을 사용하여 구성 스크립트를 다운로드하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="9e27c-129">정적 프록시 설정(프록시 주소, 바이패스 목록, 로컬에서 바이패스)을 사용자의 Internet Explorer 프록시 설정에서 읽어야 하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="9e27c-130">이 값을 "true"로 설정하면 Internet Explorer의 정적 프록시 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="9e27c-131">이 값을 "false"로 설정하거나 설정하지 않으면 구성에서 정적 프록시 설정을 지정할 수 있으며 Internet Explorer 프록시 설정은 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="9e27c-132">적응 프록시를 사용하도록 설정하려는 경우에도 이 값을 "false"로 설정하거나 설정하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="9e27c-133">다음 예제에서는 일반적인 적응 프록시 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="9e27c-134">정적 프록시</span><span class="sxs-lookup"><span data-stu-id="9e27c-134">Static Proxies</span></span>  
 <span data-ttu-id="9e27c-135">정적 프록시는 보통 응용 프로그램에 의해 명시적으로 구성되거나 응용 프로그램 또는 시스템에서 구성 파일을 호출할 때 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="9e27c-136">정적 프록시는 회사 네트워크에 연결된 데스크톱 컴퓨터와 같이 토폴로지가 자주 변경되지 않는 네트워크에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="9e27c-137">정적 프록시 작동 방식은 여러 옵션으로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="9e27c-138">다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="9e27c-139">프록시의 주소</span><span class="sxs-lookup"><span data-stu-id="9e27c-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="9e27c-140">로컬 주소에 대해 프록시를 바이패스해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="9e27c-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="9e27c-141">주소 집합에 대해 프록시를 바이패스해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="9e27c-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="9e27c-142">다음 테이블에는 정적 프록시의 구성 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="9e27c-143">특성, 속성 또는 구성 파일 설정</span><span class="sxs-lookup"><span data-stu-id="9e27c-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="9e27c-144">설명</span><span class="sxs-lookup"><span data-stu-id="9e27c-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="9e27c-145">`proxyaddress` 또는 <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="9e27c-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="9e27c-146">사용할 프록시의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="9e27c-147">`bypassonlocal` 또는 <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="9e27c-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="9e27c-148">로컬 주소에 대해 프록시를 바이패스하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="9e27c-149">`bypasslist` 또는 <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="9e27c-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="9e27c-150">정규식을 사용하여 프록시를 바이패스하는 주소 집합을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="9e27c-151">정적 프록시 설정(프록시 주소, 바이패스 목록, 로컬에서 바이패스)을 사용자의 Internet Explorer 프록시 설정에서 읽어야 하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="9e27c-152">이 값을 "true"로 설정하면 Internet Explorer의 정적 프록시 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="9e27c-153">.NET Framework 2.0에서는 이 값을 "true"로 설정하면 Internet Explorer 프록시 설정이 구성 파일의 다른 프록시 설정으로 재정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="9e27c-154">.NET Framework 1.1에서는 구성 파일의 다른 프록시 설정으로 Internet Explorer 프록시 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="9e27c-155">이 값을 "false"로 설정하거나 설정하지 않으면 구성에서 정적 프록시 설정을 지정할 수 있으며 Internet Explorer 프록시 설정은 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="9e27c-156">적응 프록시를 사용하도록 설정하려는 경우에도 이 값을 "false"로 설정하거나 설정하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="9e27c-157">다음 예제에서는 일반적인 정적 프록시 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e27c-157">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e27c-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e27c-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="9e27c-159">자동 프록시 검색</span><span class="sxs-lookup"><span data-stu-id="9e27c-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
