---
title: '&lt;net.tcp&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9312d5f7544a794f036f0a623df0d537eb96d145
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltnettcpgt"></a><span data-ttu-id="c10f7-102">&lt;net.tcp&gt;</span><span class="sxs-lookup"><span data-stu-id="c10f7-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="c10f7-103">여러 프로세스에서 동일한 TCP 포트를 공유할 수 있도록 하는 NET.TCP Port Sharing Service에 대한 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="c10f7-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c10f7-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="c10f7-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="c10f7-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c10f7-106">구문</span><span class="sxs-lookup"><span data-stu-id="c10f7-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="c10f7-107">형식</span><span class="sxs-lookup"><span data-stu-id="c10f7-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c10f7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c10f7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c10f7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c10f7-110">특성</span><span class="sxs-lookup"><span data-stu-id="c10f7-110">Attributes</span></span>  
  
|<span data-ttu-id="c10f7-111">특성</span><span class="sxs-lookup"><span data-stu-id="c10f7-111">Attribute</span></span>|<span data-ttu-id="c10f7-112">설명</span><span class="sxs-lookup"><span data-stu-id="c10f7-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="c10f7-113">공유 연결 로부터 허용 되는 Windows Communication Foundation (WCF) 서비스 아직 디스패치되는 활성 연결의 최대를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="c10f7-114">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="c10f7-115">공유 서비스에 대한 수신 끝점에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="c10f7-116">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="c10f7-117">응용 프로그램에서 수락할 때까지 수신기에서 기다릴 수 있는 최대 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="c10f7-118">이 할당량 값을 초과하면 새 들어 오는 연결은 수락될 때까지 기다리지 않고 연결이 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="c10f7-119">메시지 보안과 같은 연결 기능을 통해 클라이언트가 둘 이상의 연결을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="c10f7-120">서비스 관리자는 이 할당량 값을 설정할 때 이러한 추가 연결을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="c10f7-121">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c10f7-122">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 `TimeSpan`입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="c10f7-123">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="c10f7-124">포트 공유 서비스가 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 대신 Microsoft Teredo 서비스를 사용하여 TCP 포트에서 수신하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="c10f7-125">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c10f7-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c10f7-126">Child Elements</span></span>  
  
|<span data-ttu-id="c10f7-127">요소</span><span class="sxs-lookup"><span data-stu-id="c10f7-127">Element</span></span>|<span data-ttu-id="c10f7-128">설명</span><span class="sxs-lookup"><span data-stu-id="c10f7-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c10f7-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="c10f7-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="c10f7-130">`securityIdentifier` 서비스를 호스트하고 공유 서비스에 대한 연결 액세스가 부여된 프로세스의 사용자 계정을 지정하기 위한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 특성이 포함된 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c10f7-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c10f7-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c10f7-132">요소</span><span class="sxs-lookup"><span data-stu-id="c10f7-132">Element</span></span>|<span data-ttu-id="c10f7-133">설명</span><span class="sxs-lookup"><span data-stu-id="c10f7-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c10f7-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c10f7-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="c10f7-135">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c10f7-136">설명</span><span class="sxs-lookup"><span data-stu-id="c10f7-136">Remarks</span></span>  
 <span data-ttu-id="c10f7-137">포트 공유에 대 한 자세한 내용은 참조 하십시오. [Net.TCP 포트 공유](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="c10f7-138">포트 공유 서비스를 구성 하는 방법을 알아보려면 참조 [Net.TCP Port Sharing Service 구성](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)합니다.</span><span class="sxs-lookup"><span data-stu-id="c10f7-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10f7-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c10f7-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="c10f7-140">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="c10f7-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="c10f7-141">Net.TCP Port Sharing Service 구성</span><span class="sxs-lookup"><span data-stu-id="c10f7-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
