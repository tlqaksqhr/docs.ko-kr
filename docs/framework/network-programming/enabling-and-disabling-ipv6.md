---
title: "IPv6 사용 및 사용 안 함"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9304487963b3df4a3c2870399c474a431deb43b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="4b127-102">IPv6 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4b127-102">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="4b127-103">IPv6 프로토콜을 사용하려면 IPv6을 지원하는 운영 체제 버전을 실행 중인지 확인하고 운영 체제와 네트워킹 클래스가 제대로 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-103">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="4b127-104">구성 단계</span><span class="sxs-lookup"><span data-stu-id="4b127-104">Configuration Steps</span></span>  
 <span data-ttu-id="4b127-105">다음 표에는 다양한 구성이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-105">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="4b127-106">운영 체제 IPv6 사용?</span><span class="sxs-lookup"><span data-stu-id="4b127-106">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="4b127-107">네트워킹 클래스 IPv6 사용?</span><span class="sxs-lookup"><span data-stu-id="4b127-107">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="4b127-108">설명</span><span class="sxs-lookup"><span data-stu-id="4b127-108">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="4b127-109">아니요</span><span class="sxs-lookup"><span data-stu-id="4b127-109">No</span></span>|<span data-ttu-id="4b127-110">아니요</span><span class="sxs-lookup"><span data-stu-id="4b127-110">No</span></span>|<span data-ttu-id="4b127-111">IPv6 주소를 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-111">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="4b127-112">아니요</span><span class="sxs-lookup"><span data-stu-id="4b127-112">No</span></span>|<span data-ttu-id="4b127-113">예</span><span class="sxs-lookup"><span data-stu-id="4b127-113">Yes</span></span>|<span data-ttu-id="4b127-114">IPv6 주소를 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-114">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="4b127-115">예</span><span class="sxs-lookup"><span data-stu-id="4b127-115">Yes</span></span>|<span data-ttu-id="4b127-116">아니요</span><span class="sxs-lookup"><span data-stu-id="4b127-116">No</span></span>|<span data-ttu-id="4b127-117">IPv6 주소를 구문 분석하고 사용되지 않음으로 표시된 이름 확인 메서드로 IPv6 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-117">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="4b127-118">예</span><span class="sxs-lookup"><span data-stu-id="4b127-118">Yes</span></span>|<span data-ttu-id="4b127-119">예</span><span class="sxs-lookup"><span data-stu-id="4b127-119">Yes</span></span>|<span data-ttu-id="4b127-120">사용되지 않음으로 표시된 항목이 포함된 모든 메서드를 사용하여 IPv6 주소를 구문 분석 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-120">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="4b127-121">System.Net 네임스페이스의 모든 클래스에 대한 IPv6 지원을 사용하도록 설정하려면 컴퓨터 구성 파일 또는 응용 프로그램 구성 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-121">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="4b127-122">응용 프로그램 구성 파일이 컴퓨터 구성 파일보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-122">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="4b127-123">컴퓨터 구성 파일 *machine.config*를 수정하여 IPv6 지원을 사용하는 방법의 예제는 [방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b127-123">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="4b127-124">또한 운영 체제에 대한 IPv6 지원이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-124">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="4b127-125">.NET Framework의 경우 구성 파일에 구성 스위치가 다음과 같이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-125">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 <span data-ttu-id="4b127-126">.NET Framework 버전 1.1 이하의 경우 **ipv6 enabled** 구성 스위치 값은 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버가 IPv6 주소를 반환하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-126">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="4b127-127">.NET Framework 버전 2.0 이상의 경우 Windows에서 IPv6을 지원하면 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버(예: <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> 메서드)는 한 가지 제한과 함께 IPv6 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-127">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="4b127-128">DNS <xref:System.Net.Dns?displayProperty=nameWithType>의 사용되지 않는 멤버(예: <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> 메서드)는 구성 파일에서 ipv6 enabled 설정에 대한 값을 읽고 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="4b127-128">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b127-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b127-129">See Also</span></span>  
 [<span data-ttu-id="4b127-130">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="4b127-130">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="4b127-131">소켓</span><span class="sxs-lookup"><span data-stu-id="4b127-131">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)  
 [<span data-ttu-id="4b127-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4b127-132">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="4b127-133">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4b127-133">\<ipv6> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
