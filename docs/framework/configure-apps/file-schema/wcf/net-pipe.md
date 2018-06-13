---
title: '&lt;net.pipe&gt;'
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 71291b1163ffb4e5fe13ff18d88d47f7d2193497
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359366"
---
# <a name="ltnetpipegt"></a><span data-ttu-id="6629c-102">&lt;net.pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="6629c-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="6629c-103">명명된 파이프 연결의 수명을 관리하고 명명된 파이프을 통해 수신되는 활성화 요청을 처리하는 Named Pipe Activation Service의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="6629c-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="6629c-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="6629c-105">\<net.pipe ></span><span class="sxs-lookup"><span data-stu-id="6629c-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6629c-106">구문</span><span class="sxs-lookup"><span data-stu-id="6629c-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="6629c-107">형식</span><span class="sxs-lookup"><span data-stu-id="6629c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6629c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6629c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6629c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6629c-110">특성</span><span class="sxs-lookup"><span data-stu-id="6629c-110">Attributes</span></span>  
  
|<span data-ttu-id="6629c-111">특성</span><span class="sxs-lookup"><span data-stu-id="6629c-111">Attribute</span></span>|<span data-ttu-id="6629c-112">설명</span><span class="sxs-lookup"><span data-stu-id="6629c-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="6629c-113">공유 서비스에 대한 수신 끝점에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="6629c-114">기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="6629c-115">디스패치를 대기할 수 있는 최대 연결 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="6629c-116">기본값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="6629c-117">프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 `TimeSpan`입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="6629c-118">기본값은 "00:00:10"입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6629c-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6629c-119">Child Elements</span></span>  
  
|<span data-ttu-id="6629c-120">요소</span><span class="sxs-lookup"><span data-stu-id="6629c-120">Element</span></span>|<span data-ttu-id="6629c-121">설명</span><span class="sxs-lookup"><span data-stu-id="6629c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6629c-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="6629c-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="6629c-123">포함 하는 구성 요소의 컬렉션을 `securityIdentifier` 는 WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스가 부여 된 프로세스에 대 한 사용자 계정을 지정 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6629c-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6629c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6629c-125">요소</span><span class="sxs-lookup"><span data-stu-id="6629c-125">Element</span></span>|<span data-ttu-id="6629c-126">설명</span><span class="sxs-lookup"><span data-stu-id="6629c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6629c-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="6629c-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="6629c-128">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6629c-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6629c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6629c-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
