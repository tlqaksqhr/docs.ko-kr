---
title: '&lt;net.pipe&gt;'
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: c054cf0e4110051bb4a9ce49003fd0099b111c21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetpipegt"></a><span data-ttu-id="885de-102">&lt;net.pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="885de-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="885de-103">명명된 파이프 연결의 수명을 관리하고 명명된 파이프을 통해 수신되는 활성화 요청을 처리하는 Named Pipe Activation Service의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="885de-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="885de-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="885de-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="885de-105">\<net.pipe ></span><span class="sxs-lookup"><span data-stu-id="885de-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885de-106">구문</span><span class="sxs-lookup"><span data-stu-id="885de-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.pipe maxPendingAccepts="Integer"  
                    maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan">  
          <allowAccounts>  
             // LocalSystem account  
             <add securityIdentifier="S-1-5-18"/>  
             // LocalService account  
             <add securityIdentifier="S-1-5-19"/>  
             // Administrators account  
             <add securityIdentifier="S-1-5-20"/>  
             // Network Service account  
             <add securityIdentifier="S-1-5-32-544" />  
             // IIS_IUSRS account (Vista only)  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="885de-107">형식</span><span class="sxs-lookup"><span data-stu-id="885de-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="885de-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="885de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="885de-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="885de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="885de-110">특성</span><span class="sxs-lookup"><span data-stu-id="885de-110">Attributes</span></span>  
  
|<span data-ttu-id="885de-111">특성</span><span class="sxs-lookup"><span data-stu-id="885de-111">Attribute</span></span>|<span data-ttu-id="885de-112">설명</span><span class="sxs-lookup"><span data-stu-id="885de-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="885de-113">공유 서비스에 대한 수신 끝점에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="885de-114">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="885de-115">디스패치를 대기할 수 있는 최대 연결 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="885de-116">기본값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="885de-117">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 `TimeSpan`입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="885de-118">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="885de-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="885de-119">Child Elements</span></span>  
  
|<span data-ttu-id="885de-120">요소</span><span class="sxs-lookup"><span data-stu-id="885de-120">Element</span></span>|<span data-ttu-id="885de-121">설명</span><span class="sxs-lookup"><span data-stu-id="885de-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="885de-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="885de-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="885de-123">`securityIdentifier` 서비스를 호스트하고 공유 서비스에 대한 연결 액세스가 부여된 프로세스의 사용자 계정을 지정하기 위한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 특성이 포함된 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="885de-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="885de-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="885de-124">Parent Elements</span></span>  
  
|<span data-ttu-id="885de-125">요소</span><span class="sxs-lookup"><span data-stu-id="885de-125">Element</span></span>|<span data-ttu-id="885de-126">설명</span><span class="sxs-lookup"><span data-stu-id="885de-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="885de-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="885de-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="885de-128">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="885de-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="885de-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="885de-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
