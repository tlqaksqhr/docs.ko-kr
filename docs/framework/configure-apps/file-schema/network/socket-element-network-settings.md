---
title: "&lt;소켓&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fefb8e119d428d86501e1c8cdd5eec5ef0809cbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsocketgt-element-network-settings"></a><span data-ttu-id="44715-102">&lt;소켓&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="44715-102">&lt;socket&gt; Element (Network Settings)</span></span>
<span data-ttu-id="44715-103">소켓 작업 완료 포트를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="44715-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="44715-104">\<configuration></span></span>  
<span data-ttu-id="44715-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="44715-105">\<system.net></span></span>  
<span data-ttu-id="44715-106">\<설정 ></span><span class="sxs-lookup"><span data-stu-id="44715-106">\<settings></span></span>  
<span data-ttu-id="44715-107">\<소켓 ></span><span class="sxs-lookup"><span data-stu-id="44715-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44715-108">구문</span><span class="sxs-lookup"><span data-stu-id="44715-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44715-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44715-109">Attributes and Elements</span></span>  
 <span data-ttu-id="44715-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44715-111">특성</span><span class="sxs-lookup"><span data-stu-id="44715-111">Attributes</span></span>  
  
|<span data-ttu-id="44715-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="44715-112">**Attribute**</span></span>|<span data-ttu-id="44715-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="44715-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="44715-114">소켓 항상에 대 한 Accept 메서드 호출이 완료 포트를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44715-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="44715-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="44715-116">소켓 항상 Connect 메서드 호출에 대 한 완료 포트를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44715-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="44715-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="44715-118">기본 지정 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 소켓의 경우 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="44715-119">기본값의 Windows 버전에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="44715-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44715-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44715-120">Child Elements</span></span>  
 <span data-ttu-id="44715-121">없음</span><span class="sxs-lookup"><span data-stu-id="44715-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44715-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44715-122">Parent Elements</span></span>  
  
|<span data-ttu-id="44715-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="44715-123">**Element**</span></span>|<span data-ttu-id="44715-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="44715-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="44715-125">설정</span><span class="sxs-lookup"><span data-stu-id="44715-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="44715-126"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44715-127">설명</span><span class="sxs-lookup"><span data-stu-id="44715-127">Remarks</span></span>  
 <span data-ttu-id="44715-128">`alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성이 <xref:System.Net.Sockets?displayProperty=nameWithType> 네임스페이스에 있는 클래스에 의해 완료 포트의 사용과 관련된 기본 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44715-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="44715-129">완료 포트는 고성능 서버 응용 프로그램에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44715-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="44715-130">기본값은 `alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성을 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="44715-131"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> 의 현재 값을 가져오는 데 사용할 수는 `alwaysUseCompletionPortsForAccept` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="44715-132"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> 의 현재 값을 가져오는 데 사용할 수는 `alwaysUseCompletionPortsForConnect` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="44715-133">`ipProtectionLevel` 기본값을 지정 하는 특성 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 소켓의 경우 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="44715-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 주소 같은 링크 로컬 또는 사이트 로컬 접두사와 같은 속성에 지정된 된 범위에 IPv6 소켓에 대 한 제한 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="44715-135">이 옵션에는 응용 프로그램을 IPv6 소켓에 대 한 액세스 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="44715-136">이러한 제한을 사용하면 사설 LAN에서 실행되는 응용 프로그램을 간단하고 강력하게 외부 공격으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="44715-137">이 옵션은 확대 또는 적절 한 경우 공용 및 개인 사용자 하거나, 필요에 따라 같은 사이트로 액세스를 제한의 무제한 액세스를 사용할 수 있도록와 여 수신 소켓의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="44715-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="44715-138">이 `ipProtectionLevel` 특성 설정은 초기 들어오는 트래픽을 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44715-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="44715-139">TCP 소켓에서 들어오는 연결을 수신 대기 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="44715-140">UDP 소켓에서 패킷을 받는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="44715-141">이 구성 설정은 이미 설정 된 TCP 연결 (트래픽 모두에 무제한으로)에 영향을 주지 UDP 패킷을 보내는 응용 프로그램에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="44715-142">에 가능한 값은 고 `ipProtectionLevel` 특성 설정에 지정 된 정의 된 보호 수준이 해당는 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 다음과 같이 열거형:</span><span class="sxs-lookup"><span data-stu-id="44715-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="44715-143">**특성 값**</span><span class="sxs-lookup"><span data-stu-id="44715-143">**Attribute Value**</span></span>|<span data-ttu-id="44715-144">**설명**</span><span class="sxs-lookup"><span data-stu-id="44715-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="44715-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="44715-145">EdgeRestricted</span></span>|<span data-ttu-id="44715-146">IP 보호 수준은 가장자리 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="44715-147">이 값은 인터넷을 통해 작동 하도록 디자인 된 응용 프로그램에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44715-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="44715-148">이 설정은 Windows Teredo 구현을 사용 하 여 네트워크 주소 변환 (NAT) 통과 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="44715-149">열린 포트로 향하는 인터넷 공격 응용 프로그램을 확정 해야 하므로 이러한 응용 프로그램 IPv4 방화벽을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="44715-150">Windows Server 2003 및 Windows XP 소켓에서 IP 보호 수준에 대 한 기본 값은 가장자리 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="44715-151">제한</span><span class="sxs-lookup"><span data-stu-id="44715-151">Restricted</span></span>|<span data-ttu-id="44715-152">IP 보호 수준이 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-152">The IP protection level is restricted.</span></span> <span data-ttu-id="44715-153">이 값은 인터넷 시나리오를 구현 하지 않는 인트라넷 응용 프로그램에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44715-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="44715-154">이러한 응용 프로그램은 일반적으로 테스트 말거나 인터넷 유형의 공격에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="44715-155">이 설정은 트래픽이 받도록된 링크-로컬만 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44715-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="44715-156">제한 없음</span><span class="sxs-lookup"><span data-stu-id="44715-156">Unrestricted</span></span>|<span data-ttu-id="44715-157">IP 보호 수준이 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="44715-158">이 값은 기본 제공 되는 IPv6 NAT 통과 기능을 활용 하기 위해 응용 프로그램을 포함 하 여 인터넷을 통해 작동 하도록 설계 된 응용 프로그램에서 사용 될 windows (예: Teredo).</span><span class="sxs-lookup"><span data-stu-id="44715-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="44715-159">열린 포트로 향하는 인터넷 공격 응용 프로그램을 확정 해야 하므로 이러한 응용 프로그램 IPv4 방화벽을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="44715-160">Windows Server 2008 R2 및 Windows Vista에서 소켓 IP 보호 수준에 대 한 기본값 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="44715-161">지정되지 않음</span><span class="sxs-lookup"><span data-stu-id="44715-161">Unspecified</span></span>|<span data-ttu-id="44715-162">IP 보호 수준이 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="44715-163">Windows 7 및 Windows Server 2008 r 2에서 소켓에서 IP 보호 수준에 대 한 기본값 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="44715-164">기본값은 `ipProtectionLevel` 특성은 **Unspecified**합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="44715-165"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성의 현재 값을 가져오는 데 사용할 수는 `ipProtectionLevel` 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44715-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="44715-166">구성 파일</span><span class="sxs-lookup"><span data-stu-id="44715-166">Configuration Files</span></span>  
 <span data-ttu-id="44715-167">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44715-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44715-168">예</span><span class="sxs-lookup"><span data-stu-id="44715-168">Example</span></span>  
 <span data-ttu-id="44715-169">다음 예제에서는 완료 포트를 사용 해야 함을 지정 하는 방법을 지정 하 고 있는 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44715-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44715-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44715-170">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [<span data-ttu-id="44715-171">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="44715-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
